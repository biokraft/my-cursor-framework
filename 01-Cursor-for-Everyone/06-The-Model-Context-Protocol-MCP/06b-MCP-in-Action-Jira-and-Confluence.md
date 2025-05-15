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
    *   To get details of an issue: `mcp_mcp-atlassian_Jira_Cloud_jira_get_issue(issue_key='PROJ-123')`
    *   To search for issues using JQL: `mcp_mcp-atlassian_Jira_Cloud_jira_search(jql='project = PROJ AND status = "In Progress" AND assignee = currentUser()')`
    *   To add a comment: `mcp_mcp-atlassian_Jira_Cloud_jira_add_comment(issue_key='PROJ-123', comment='Solution implemented and tested.')`

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
    *   To search Confluence: `mcp_mcp-atlassian_Jira_Cloud_confluence_search(query='type=page AND space=DEV AND title~"Release Process"')`
    *   To get page content: `mcp_mcp-atlassian_Jira_Cloud_confluence_get_page(page_id='123456789', convert_to_markdown=True)`
    *   To create a page: `mcp_mcp-atlassian_Jira_Cloud_confluence_create_page(space_key='DEV', title='My New Page', content='# Heading\nThis is my page content in Markdown.')`

## Benefits for Everyone

-   **Product Managers:** Can quickly pull up Jira epics or user stories, or search Confluence for existing research when discussing new features with Cursor.
-   **Developers:** Can get immediate context from Jira tickets when starting work, or reference technical documentation from Confluence without leaving their IDE.
-   **Technical Writers:** Can search Confluence for related articles or verify information before updating documentation.

By integrating these tools, MCP makes Cursor a much more powerful and contextually aware assistant, deeply embedded in your team's existing workflows.

### Detailed Setup Guide for Atlassian MCP Integration (Jira & Confluence)

This guide provides step-by-step instructions for integrating Jira Cloud and Confluence with Cursor AI using the Model Context Protocol (MCP). This setup allows you to leverage Jira and Confluence information directly within your Cursor AI chats.

**Prerequisites and General Information:**

*   **MCP Overview:** The Model Context Protocol (MCP) is an open protocol standardizing how applications provide context and tools to LLMs. It acts as a plugin system for Cursor, extending the Agent's capabilities by connecting it to various data sources and tools. For more details, see the [official MCP documentation](https://docs.cursor.com/context/model-context-protocol).
*   **Atlassian MCP Basis:** This integration utilizes the `mcp-atlassian` project available on [GitHub](https://github.com/sooperset/mcp-atlassian).

**Setup Steps:**

1.  **Cursor AI Installation:**
    *   **Important:** Ensure you have the ARM64 version of Cursor AI installed. The integration may not function correctly with other versions. (Refer to your internal "Cursor AI - Account Erstellung und Installation" guide for details).

2.  **Create Jira Cloud API Token:**
    *   Navigate to [Atlassian API Tokens](https://id.atlassian.com/manage-profile/security/api-tokens).
    *   Create a new API token.
    *   **Action:** Copy the generated token immediately and store it securely (e.g., in 1Password, KeePass, or your company's preferred password manager).
    *   **Label/Name:** Give it a descriptive name, for example, "Cursor AI".
    *   **Expiry:** Set an appropriate expiration date (e.g., six months in the future, like 01/10/2025).

3.  **Create Confluence Personal Access Token (PAT):**
    *   Go to your Confluence PAT settings: `https://confluence.[YOUR_COMPANY_DOMAIN].de/plugins/personalaccesstokens/usertokens.action` (Replace `confluence.[YOUR_COMPANY_DOMAIN].de` with your Confluence instance URL if different).
    *   Create a new token.
    *   **Action:** Copy the token and store it securely.
    *   **Token Name:** Use a clear name, such as "Cursor AI".
    *   **Expiry:** Choose "No expiry date" or set an expiry date (e.g., 180 days).

4.  **Install Homebrew (Package Manager for macOS):**
    *   1.  Open your Terminal application.
    *   2.  Execute the following command:
        ```bash
        /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
        ```
    *   3.  Verify the installation by running:
        ```bash
        brew -v
        ```
        You should see the Homebrew version output (e.g., `Homebrew 4.4.29`).

5.  **Install `uv` (Python Package Manager):**
    *   In your Terminal, run:
        ```bash
        brew install uv
        ```
    *   If you encounter an error (especially on ARM-based Macs), try:
        ```bash
        arch -arm64 brew install uv
        ```

6.  **Configure MCP for Jira Cloud and Confluence in Cursor AI:**
    *   1.  Open Cursor AI Settings.
    *   2.  Select "MCP" from the settings menu.
    *   3.  Click "Add new global MCP Server". This will open an `mcp.json` file.
    *   4.  Paste the following JSON configuration into the `mcp.json` file:

        ```json
        {
            "mcpServers": {
              "mcp-atlassian (Jira Cloud)": {
                "command": "uvx",
                "args": [
                  "mcp-atlassian",
                  "--verbose",
                  "--read-only",
                  "--jira-url=[YOUR JIRA INSTANCE]",
                  "--jira-username=[YOUR_EMAIL]@[YOUR_COMPANY_DOMAIN]",
                  "--jira-token=[YOUR JIRA ACCESS TOKEN]"
                ]
              },
              "mcp-atlassian (Confluence)": {
                "command": "uvx",
                "args": [
                  "mcp-atlassian",
                  "--verbose",
                  "--read-only",
                  "--confluence-url=https://[YOUR_CONFLUENCE_URL]/",
                  "--confluence-username=[YOUR_EMAIL]@[YOUR_COMPANY_DOMAIN]",
                  "--confluence-personal-token=[YOUR CONFLUENCE ACCESS TOKEN]"
                ]
              }
            }
          }
        ```
    *   5.  **Customize the placeholders** in the JSON (remove the square brackets):
        *   `[YOUR JIRA INSTANCE]`: Your Jira Cloud URL (e.g., `https://your-company.atlassian.net`, `https://another-project.atlassian.net`).
        *   `[YOUR_EMAIL]@[YOUR_COMPANY_DOMAIN]`: Your email address associated with your Jira/Confluence accounts.
        *   `[YOUR JIRA ACCESS TOKEN]`: The Jira API token you created in Step 2.
        *   `[YOUR CONFLUENCE ACCESS TOKEN]`: The Confluence PAT you created in Step 3.
        *   `[YOUR_CONFLUENCE_URL]`: Ensure this matches your Confluence instance URL if it's different (e.g., `your-company.atlassian.net/wiki`).
    *   6.  Save the `mcp.json` file (e.g., Cmd+S on macOS).
    *   7.  Return to the Cursor AI Settings (MCP Servers screen).
    *   8.  **Recommendation:** Keep `--read-only` enabled in the `args` for both configurations. Removing it would allow Cursor AI to potentially write to Jira and Confluence, which should only be done with caution and full understanding of the implications.
    *   9.  The MCP server entries should now appear in the list. A green status indicator means the connection is likely successful. A red indicator suggests a configuration error (double-check your URLs, email, and tokens).

7.  **Enable/Disable MCP Servers:**
    *   In the Cursor AI MCP settings, you can toggle the switches for "mcp-atlassian (Jira Cloud)" and "mcp-atlassian (Confluence)" to enable or disable the respective integrations as needed. Ensure they are enabled for use.

8.  **Test in Chat:**
    *   Activate "Agent" mode in Cursor AI chat.
    *   You can now use natural language queries or specific MCP commands to interact with your Jira and Confluence instances. Examples:
        *   "Get details for Jira ticket PROJ-123"
        *   "@jira search jql='assignee = currentUser() and status = Open'"
        *   "Find Confluence pages about 'API documentation' in the DEV space"
        *   "@confluence get_page page_id=123456789"

This detailed setup guide should provide comprehensive instructions for users to integrate their Atlassian tools with Cursor. 