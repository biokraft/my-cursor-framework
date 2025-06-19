# 🤝 MCP in Action: Jira & Confluence

> **🔑 Key Takeaways:**
> 
> - **Bring Project Management to Your IDE:** Connect Cursor to Jira and Confluence to pull in issue details and documentation pages as context.
> - **Use Natural Language:** Interact by asking questions like "What are the details for ticket PROJ-123?" or "Find the Confluence page about our API."
> - **Setup Involves API Tokens:** You'll need to generate API tokens from your Atlassian account and add them to Cursor's MCP configuration.
> - **Run via Docker:** The easiest way to run the Atlassian MCP server is via Docker, managed directly by Cursor's MCP settings.

---

Let's see how the Model Context Protocol (MCP) works with two of the most common development tools: Jira and Confluence.

##  Jira Integration

Integrating Jira allows you to seamlessly pull issue information into your AI workflows.

### Common Use Cases
-   **Get Issue Details:** Quickly fetch the summary, description, and status of a ticket.
-   **Context for Coding:** Give the AI (and yourself) full context on a feature or bug by referencing the Jira ticket.
-   **Add Comments:** Ask Cursor to add a progress comment back to the ticket.

### Example Interactions
-   **Natural Language:**
    -   "What are the details for Jira ticket PROJ-123?"
    -   "Search Jira for open bugs assigned to me."
    -   "Add a comment to PROJ-123 saying 'I'm starting work on this now.'"
-   **Specific Tool Commands:**
    -   `@jira get_issue(issue_key='PROJ-123')`
    -   `@jira add_comment(issue_key='PROJ-123', comment='Done.')`

## 📚 Confluence Integration

Connecting to Confluence allows Cursor to tap into your team's knowledge base.

### Common Use Cases
-   **Search for Documentation:** Find relevant technical specs, meeting notes, or user guides.
-   **Get Page Content:** Retrieve the content of a specific page to use as context for the AI.
-   **Answer Questions:** Ask questions that can be answered by information stored in your Confluence space.

### Example Interactions
-   **Natural Language:**
    -   "Find the Confluence page about our deployment process."
    *   "Summarize the Confluence page with ID 123456789."
-   **Specific Tool Commands:**
    -   `@confluence search(query='title~"Release Process"')`
    -   `@confluence get_page(page_id='123456789')`

---

## 🛠️ Quick Setup Guide

Here's a simplified guide to get you started. This assumes you are running the `mcp-atlassian` server via Docker, which is the recommended method.

**1. Get Your Atlassian API Tokens:**
   - **Jira:** Go to `id.atlassian.com/manage-profile/security/api-tokens` and create a new API token. Save the token securely.
   - **Confluence:** The process is similar; you'll need to generate a Personal Access Token (PAT) from your Confluence settings.

**2. Install Docker Desktop:**
   - If you don't have it already, download and install [Docker Desktop](https://www.docker.com/products/docker-desktop/).

**3. Configure MCP in Cursor:**
   - In Cursor Settings, go to **MCP** and click **"Add new global MCP Server"**.
   - This opens an `mcp.json` file. Paste in the configuration below.
   - **Fill in the placeholders** in the `env` block with your actual URLs, username, and the tokens you just created.

```json
{
    "mcpServers": {
      "mcp-atlassian": {
        "command": "docker",
        "args": [
          "run", "-i", "--rm",
          "-e", "CONFLUENCE_URL",
          "-e", "CONFLUENCE_USERNAME",
          "-e", "CONFLUENCE_PERSONAL_ACCESS_TOKEN",
          "-e", "JIRA_URL",
          "-e", "JIRA_USERNAME",
          "-e", "JIRA_API_TOKEN",
          "-e", "READ_ONLY_MODE=true",
          "ghcr.io/sooperset/mcp-atlassian:latest"
        ],
        "env": {
          "CONFLUENCE_URL": "https://your-company.atlassian.net/wiki",
          "CONFLUENCE_USERNAME": "your.email@company.com",
          "CONFLUENCE_PERSONAL_ACCESS_TOKEN": "YOUR_CONFLUENCE_PAT_HERE",
          "JIRA_URL": "https://your-company.atlassian.net",
          "JIRA_USERNAME": "your.email@company.com",
          "JIRA_API_TOKEN": "YOUR_JIRA_API_TOKEN_HERE",
          "READ_ONLY_MODE": "true"
        },
        "description": "Atlassian MCP Server (Jira & Confluence)",
        "timeoutSeconds": 60
      }
    }
  }
```

**4. Save and Test:**
   - Save the `mcp.json` file.
   - The server entry should appear in your MCP settings with a green status indicator.
   - Test it in the chat: "Get details for Jira ticket PROJ-123".

---

-   **Analyze & Comment:** Ask Cursor to analyze the ticket and suggest a comment.

---

[⬅️ Back to MCP Overview](./06a-MCP-The-Big-Picture.md) | [Up: Cursor for Everyone](../README.md) | [Next: MCP Spotlight: DBHub ➡️](./06c-MCP-Spotlight-DBHub.md) 