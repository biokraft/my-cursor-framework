# 💾 MCP Spotlight: DBHub

> **🔑 Key Takeaways:**
> 
> - **Universal Database Connector:** DBHub acts as a bridge, allowing Cursor to connect to popular databases like PostgreSQL, MySQL, SQL Server, and more.
> - **Natural Language Queries:** Ask questions about your database in plain English (e.g., "How many users signed up last week?").
> - **AI-Powered SQL:** Get help from the AI to generate, explain, or debug complex SQL queries.
> - **Easy to Start:** Use the `--demo` flag to instantly start a sample database for testing, or provide a standard database connection string (DSN) to connect to your own.

---

`dbhub` is a universal database MCP server that connects Cursor to your databases. This is invaluable for anyone who needs to query data, from a developer debugging an issue to a product manager looking for quick insights.

[DBHub GitHub Repository](https://github.com/bytebase/dbhub)

## 🤔 What Does DBHub Do?

-   **Connects to Your Databases:** Supports MySQL, PostgreSQL, Oracle, SQL Server, and more.
-   **Enables Natural Language Querying:** Lets you ask questions of your database without writing SQL.
-   **Assists with SQL:** Helps you write, debug, and understand SQL with AI assistance.
-   **Provides a Safe Read-Only Mode:** Protect your production data by restricting operations to be read-only.

## 🚀 How to Use It

Once connected, you can interact with your database using natural language.

-   **For Product Managers:**
    -   "In the demo database, how many employees are there?"
    -   "Query our production DB (read-only) and tell me how many users signed up yesterday."
-   **For Developers:**
    -   "What's the schema for the `users` table in our PostgreSQL database?"
    -   "Draft a SQL query to find all products in the 'electronics' category."

---

## 🛠️ Quick Setup Guide

Here's a simplified guide to get you started. The easiest way to run DBHub is with `npx` in your terminal.

**1. Install Node.js:**
   - If you don't have it already, install Node.js from [nodejs.org](https://nodejs.org/), which includes `npx`.

**2. Run DBHub in Your Terminal:**
   - **For a quick demo:** This uses a sample in-memory database.
     ```bash
     npx @bytebase/dbhub --demo --transport stdio
     ```
   - **To connect to your own database:**
     You'll need a standard database connection string (DSN).
     ```bash
     # Example for PostgreSQL
     npx @bytebase/dbhub --dsn "postgres://user:pass@host:5432/mydb" --transport stdio --readonly
     ```
   - **Keep this terminal window open!** It's now serving your database to Cursor.

**3. Configure MCP in Cursor:**
   - In Cursor Settings, go to **MCP** and click **"Add new global MCP Server"**.
   - This opens an `mcp.json` file. Paste in the configuration that matches how you ran DBHub in the terminal.

   - **Configuration for the *demo* server:**
     ```json
     {
       "mcpServers": {
         "dbhub-demo": {
           "command": "npx",
           "args": ["-y", "@bytebase/dbhub", "--demo", "--transport", "stdio"],
           "description": "DBHub Demo Server"
         }
       }
     }
     ```
    - For your own database, simply replace the `args` with your command (e.g., `"--dsn"`, `"your_dsn_string"`, `"--transport"`, `"stdio"`).

**4. Save and Test:**
   - Save the `mcp.json` file. The server should get a green light in your MCP settings.
   - Test it in chat: "Using the dbhub-demo, what tables are available?"

---

This powerful combination allows the AI to understand your application's data layer, leading to more accurate and context-aware code generation.

---

[⬅️ Back to Jira/Confluence](./06b-MCP-in-Action-Jira-and-Confluence.md) | [Up: Cursor for Everyone](../README.md) | [Next: MCP Ecosystem ➡️](./06d-Exploring-the-MCP-Ecosystem.md) 