
# UseCase 2: Defining and Creating Jira Tickets with MCP

### 🎯 The Goal
To show how to use the **Model Context Protocol (MCP)** to interact with Jira directly from the editor, turning a project plan into a well-defined ticket without ever leaving Cursor.

### 💼 The Real-World Scenario
**The Problem:** A Team Lead needs to create a Jira ticket for the "Quarterly Sales Performance Dashboard" we just planned.

**The Pain Point:** This involves switching to the Jira web UI, copying and pasting information from the plan, manually filling in fields, and potentially forgetting key details, leading to poorly defined tickets and developer confusion.

### 🚀 The Cursor Framework Solution
Using the built-in **`@jira` MCP tool**, we can query for information, format it, and create a ticket in one seamless workflow. This ensures the ticket has all the necessary context from our plan.

### 🤖 Live Demo Script
1.  **Reference the plan:** Make sure you have the `sales-dashboard-plan.md` from the previous use case open.
2.  **Initial Prompt (Information Gathering):**
    > "Using the context from `@workshop/01-uc-project-planning-mdp/sales-dashboard-plan.md`, I need to create a Jira ticket. First, help me draft the ticket's summary and description. The description should be a markdown-formatted summary of the key features and goals."
3.  **Refine the Content:** The AI will generate the text. You can refine it.
    > "That looks good. For the summary, let's make it: 'Feat: Implement Quarterly Sales Performance Dashboard V1'."
4.  **Create the Ticket with MCP:** Now, use the Jira tool.
    > "Perfect. Now, create a new Jira issue with that summary and description.
    > - **Project Key:** `SALES` (use a real project key for the demo)
    > - **Issue Type:** `Story`
    > - **Assignee:** `user@example.com` (use a real assignee)
    > - **Components:** `Reporting, Dashboard`"
5.  **Show the Outcome:** The AI will call the `@jira create_issue` tool. The result will be a new Jira ticket, created with perfect context, without ever leaving the editor. Show the link to the newly created ticket. This demonstrates a massive reduction in context-switching and administrative overhead.

---
[⬅️ Back to Workshop Overview](../README.md) 