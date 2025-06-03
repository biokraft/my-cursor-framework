# MCP in Action: Jira and Confluence Integration

Now that we understand the general concept of the Model Context Protocol (MCP), let's look at how it works with two common and powerful Atlassian tools: Jira for project and issue tracking, and Confluence for documentation and knowledge sharing.

## Connecting to Jira

Jira is a staple for many teams to manage tasks, bugs, and sprints. Integrating Jira with Cursor via MCP allows you to seamlessly pull issue information into your AI workflows, and sometimes even update issues.

**Common Use Cases:**

-   **Get Issue Details:** Quickly fetch the summary, description, status, assignee, and comments for a specific Jira ticket.
-   **Search for Issues:** Find issues based on JQL (Jira Query Language) queries.
-   **Context for Coding:** When working on a feature or bug, pull the relevant Jira ticket details directly into Cursor to give the AI (and yourself) full context.
-   **Add Comments (if enabled/permitted):** After drafting a solution or having a discussion in Cursor, ask it to add a summary comment back to the Jira ticket.

**Example Interactions** (Conceptual - exact commands may vary):

*   **Using Natural Language:**
    *   "What are the details for Jira ticket PROJ-123?"
    *   "Search Jira for open bugs assigned to me in the 'Phoenix' project."
    *   "Find Jira issues related to 'user authentication flow' updated in the last week."
    *   (If action-enabled) "Add a comment to PROJ-123 saying 'Investigating the proposed solution.'"

*   **Using Specific Tool Commands (Examples based on available tools):**
    *   To get details of an issue: `mcp_mcp-atlassian_jira_get_issue(issue_key='PROJ-123')`
    *   To search for issues using JQL: `mcp_mcp-atlassian_jira_search(jql='project = PROJ AND status = "In Progress" AND assignee = currentUser()')`
    *   To add a comment: `mcp_mcp-atlassian_jira_add_comment(issue_key='PROJ-123', comment='Solution implemented and tested.')`

## Connecting to Confluence

Confluence is widely used for team collaboration, project documentation, knowledge bases, and more. MCP integration allows Cursor to tap into this wealth of information.

**Common Use Cases:**

-   **Search Confluence Pages:** Find relevant documentation, meeting notes, or technical specs within specific Confluence spaces.
-   **Get Page Content:** Retrieve the content of a Confluence page to use as context for the AI.
-   **Answer Questions Based on Docs:** Ask Cursor questions that can be answered by information within your Confluence instance.
-   **Draft New Pages (if enabled/permitted):** Start drafting a new Confluence page based on discussions or code developed in Cursor.

**Example Interactions** (Conceptual - exact commands may vary):

*   **Using Natural Language:**
    *   "Find the Confluence page about our deployment process in the 'DEVOPS' space."
    *   "Summarize the Confluence page with ID 123456789."
    *   "What does our Confluence say about setting up a new development environment?"
    *   (If action-enabled) "Create a new Confluence page in the 'PROJECTX' space titled 'New Feature Brainstorm' with the following content..."

*   **Using Specific Tool Commands (Examples based on available tools):**
    *   To search Confluence: `mcp_mcp-atlassian_confluence_search(query='type=page AND space=DEV AND title~"Release Process"')`
    *   To get page content: `mcp_mcp-atlassian_confluence_get_page(page_id='123456789', convert_to_markdown=True)`
    *   To create a page: `mcp_mcp-atlassian_confluence_create_page(space_key='DEV', title='My New Page', content='# Heading\\nThis is my page content in Markdown.')`

## Benefits for Everyone

-   **Product Managers:** Can quickly pull up Jira epics or user stories, or search Confluence for existing research when discussing new features with Cursor.
-   **Developers:** Can get immediate context from Jira tickets when starting work, or reference technical documentation from Confluence without leaving their IDE.
-   **Technical Writers:** Can search Confluence for related articles or verify information before updating documentation.

By integrating these tools, MCP makes Cursor a much more powerful and contextually aware assistant, deeply embedded in your team's existing workflows.

### Detailed Setup Guide for Atlassian MCP Integration (Jira & Confluence)

This guide provides step-by-step instructions for integrating Jira Cloud and Confluence with Cursor AI using the Model Context Protocol (MCP). This setup allows you to leverage Jira and Confluence information directly within your Cursor AI chats.

**Prerequisites and General Information:**

*   **MCP Overview:** The Model Context Protocol (MCP) is an open protocol standardizing how applications provide context and tools to LLMs. It acts as a plugin system for Cursor, extending the Agent's capabilities by connecting it to various data sources and tools. For more details, see the [official MCP documentation](https://docs.cursor.com/context/model-context-protocol).
*   **Atlassian MCP Basis:** This integration utilizes the `mcp-atlassian` project available on [GitHub](https://github.com/sooperset/mcp-atlassian). The setup has been updated to recommend running the MCP server via Docker.

**Setup Steps:**

1.  **Cursor AI Installation:**
    *   **Important:** Ensure you have the ARM64 version of Cursor AI installed. The integration may not function correctly with other versions. (Refer to your internal "Cursor AI - Account Erstellung und Installation" guide for details).

2.  **Create Jira Cloud API Token:**
    *   Navigate to [Atlassian API Tokens](https://id.atlassian.com/manage-profile/security/api-tokens).
    *   Create a new API token.
    *   **Action:** Copy the generated token immediately and store it securely (e.g., in 1Password, KeePass, or your company's preferred password manager).
    *   **Label/Name:** Give it a descriptive name, for example, "Cursor AI MCP".
    *   **Expiry:** Set an appropriate expiration date (e.g., six months in the future, like 01/10/2025).

3.  **Create Confluence Personal Access Token (PAT):**
    *   Go to your Confluence PAT settings: `https://confluence.[YOUR_COMPANY_DOMAIN].de/plugins/personalaccesstokens/usertokens.action` (Replace `confluence.[YOUR_COMPANY_DOMAIN].de` with your Confluence instance URL if different).
    *   Create a new token.
    *   **Action:** Copy the token and store it securely.
    *   **Token Name:** Use a clear name, such as "Cursor AI MCP".
    *   **Expiry:** Choose "No expiry date" or set an expiry date (e.g., 180 days).

4.  **Install Docker Desktop:**
    *   Download and install Docker Desktop for your operating system from the [official Docker website](https://www.docker.com/products/docker-desktop/). This will allow you to run the `mcp-atlassian` server in a container.

5.  **Configure MCP in Cursor AI for `mcp-atlassian` (Direct Docker Method):**
    *   This method configures Cursor to directly run the `mcp-atlassian` Docker container, managing its lifecycle and environment variables from within `mcp.json`.
    *   1.  Open Cursor AI Settings.
    *   2.  Select "MCP" from the settings menu.
    *   3.  Click "Add new global MCP Server". This will open an `mcp.json` file.
    *   4.  Paste the following JSON configuration into the `mcp.json` file.

        ```json
        {
            "mcpServers": {
              "mcp-atlassian": {
                "command": "docker",
                "args": [
                  "run",
                  "-i", // Enables interactive mode, crucial for the MCP server
                  "--rm", // Automatically removes the container when it exits
                  // Pass environment variables from the 'env' block below
                  "-e", "CONFLUENCE_URL",
                  "-e", "CONFLUENCE_USERNAME",
                  "-e", "CONFLUENCE_API_TOKEN", // For older Confluence Server/DC if PAT doesn't work
                  "-e", "CONFLUENCE_PERSONAL_ACCESS_TOKEN", // Preferred for Confluence Cloud & newer Server/DC
                  "-e", "JIRA_URL",
                  "-e", "JIRA_USERNAME",
                  "-e", "JIRA_API_TOKEN",
                  "-e", "READ_ONLY_MODE=true", // Recommended for safety
                  // "-e", "LOG_LEVEL=DEBUG", // Optional: for more detailed logs
                  // "-e", "ENABLED_TOOLS=jira_get_issue,confluence_search", // Optional: comma-separated list
                  "ghcr.io/sooperset/mcp-atlassian:latest"
                  // Add server arguments after the image name if needed, e.g., "--port", "9001"
                  // By default, mcp-atlassian started this way listens on a unix socket.
                  // To use TCP, you would need to add: "--transport", "streamable-http", "--port", "9000"
                  // and then configure a separate MCP entry with "url": "http://localhost:9000/mcp"
                  // However, the direct `docker run` with stdin/stdout is often simpler.
                ],
                "env": {
                  "CONFLUENCE_URL": "https://[YOUR_CONFLUENCE_INSTANCE_URL]",
                  "CONFLUENCE_USERNAME": "[YOUR_EMAIL]@[YOUR_COMPANY_DOMAIN]",
                  "CONFLUENCE_API_TOKEN": "[YOUR_CONFLUENCE_API_TOKEN_IF_NEEDED]", // Usually for older Confluence Server/DC
                  "CONFLUENCE_PERSONAL_ACCESS_TOKEN": "[YOUR_CONFLUENCE_PAT]", // From Step 3
                  "JIRA_URL": "https://[YOUR_JIRA_INSTANCE_URL]",
                  "JIRA_USERNAME": "[YOUR_EMAIL]@[YOUR_COMPANY_DOMAIN]",
                  "JIRA_API_TOKEN": "[YOUR_JIRA_API_TOKEN]", // From Step 2
                  // You can also set READ_ONLY_MODE, LOG_LEVEL, ENABLED_TOOLS here
                  "READ_ONLY_MODE": "true"
                },
                "description": "Atlassian MCP Server (Jira & Confluence via direct Docker command)",
                "timeoutSeconds": 60 // Increased timeout for Docker startup
              }
            }
          }
        ```
    *   5.  **Customize the placeholders** in the `env` block of the JSON (remove the square brackets):
        *   `[YOUR_CONFLUENCE_INSTANCE_URL]`: Your Confluence URL (e.g., `your-company.atlassian.net/wiki`).
        *   `[YOUR_EMAIL]@[YOUR_COMPANY_DOMAIN]`: Your email address associated with your Atlassian accounts.
        *   `[YOUR_CONFLUENCE_API_TOKEN_IF_NEEDED]`: Your Confluence API Token (password for very old Server/DC instances). Most users will primarily use the PAT.
        *   `[YOUR_CONFLUENCE_PAT]`: The Confluence Personal Access Token you created in Step 3.
        *   `[YOUR_JIRA_INSTANCE_URL]`: Your Jira Cloud URL (e.g., `your-company.atlassian.net`).
        *   `[YOUR_JIRA_API_TOKEN]`: The Jira API token you created in Step 2.
        *   Ensure `READ_ONLY_MODE` is set to `"true"` for safety, unless you explicitly need write access.

    *   6.  **Note on Docker Image Version:** The configuration uses `ghcr.io/sooperset/mcp-atlassian:latest`. While `:latest` usually points to the most recent version, it can sometimes have an issue. If you encounter problems, you can try a specific version tag like `v0.11.0` or `v0.10.6` by changing `latest` to, for example, `v0.11.0` in the `"args"` array.

    *   7.  Save the `mcp.json` file (e.g., Cmd+S on macOS).
    *   8.  Return to the Cursor AI Settings (MCP Servers screen).
    *   9.  The "mcp-atlassian" server entry should now appear in the list. A green status indicator means Cursor is successfully managing the Docker container. A red indicator suggests a configuration error (double-check your credentials in `mcp.json` and ensure Docker Desktop is running).

6.  **Enable/Disable MCP Servers:**
    *   In the Cursor AI MCP settings, you can toggle the switch for "mcp-atlassian" to enable or disable the integration as needed. Ensure it is enabled for use.

7.  **Test in Chat:**
    *   Activate "Agent" mode in Cursor AI chat.
    *   You can now use natural language queries or specific MCP commands to interact with your Jira and Confluence instances. Examples:
        *   "Get details for Jira ticket PROJ-123"
        *   To use a specific tool: `mcp_mcp-atlassian_jira_search(jql='assignee = currentUser() and status = Open')`
        *   "Find Confluence pages about 'API documentation' in the DEV space"
        *   To use a specific tool: `mcp_mcp-atlassian_confluence_get_page(page_id='123456789')`

This detailed setup guide should provide comprehensive instructions for users to integrate their Atlassian tools with Cursor.

---

[⬅️ Back to Main README](../../../README.md) 