# MCP in Action: Jira and Confluence Integration

Now that we understand the general concept of the Multi-Connector Platform (MCP), let's look at how it works with two common and powerful Atlassian tools: Jira for project and issue tracking, and Confluence for documentation and knowledge sharing.

## Connecting to Jira

Jira is a staple for many teams to manage tasks, bugs, and sprints. Integrating Jira with Cursor via MCP allows you to seamlessly pull issue information into your AI workflows, and sometimes even update issues.

**Common Use Cases:**

-   **Get Issue Details:** Quickly fetch the summary, description, status, assignee, and comments for a specific Jira ticket.
-   **Search for Issues:** Find issues based on JQL (Jira Query Language) queries.
-   **Context for Coding:** When working on a feature or bug, pull the relevant Jira ticket details directly into Cursor to give the AI (and yourself) full context.
-   **Add Comments (if enabled/permitted):** After drafting a solution or having a discussion in Cursor, ask it to add a summary comment back to the Jira ticket.

**Example Interactions (Conceptual - exact commands may vary):

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

**Example Interactions (Conceptual - exact commands may vary):

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