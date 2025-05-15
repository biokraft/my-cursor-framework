# MCP Spotlight: DBHub - Universal Database Access with Cursor

The Model Context Protocol (MCP) extends Cursor's capabilities by connecting it to various external tools and data sources. This guide focuses on `dbhub`, a universal database MCP server that allows Cursor to interact with a wide range of popular databases. This integration is invaluable for both Product Managers needing quick data insights and Developers working directly with databases.

[DBHub GitHub Repository](https://github.com/bytebase/dbhub)

## What is DBHub?

DBHub acts as a bridge between Cursor (or other MCP-compatible clients) and your databases. It supports:

-   MySQL
-   PostgreSQL
-   Oracle
-   SQL Server
-   MariaDB
-   SQLite

By connecting DBHub to Cursor, you can query these databases using natural language or by instructing Cursor to generate and execute SQL commands, all from within your chat interface.

## Key Features of DBHub

-   **Broad Database Support:** Connect to the most common relational databases.
-   **Demo Mode:** Instantly start with a sample SQLite database for testing and learning.
-   **Flexible DSN Configuration:** Provide database connection strings via command line, environment variables, or `.env` files.
-   **Transport Modes:**
    -   `stdio`: Ideal for direct integration with tools like Cursor in Agent mode.
    -   `sse` (Server-Sent Events): For browser and network clients.
-   **Read-only Mode:** Protect your production databases by restricting operations to read-only.
-   **SSL Connections:** Secure your database connections with configurable SSL modes (`disable`, `require`, or default certificate verification).

## Connecting DBHub to Cursor

Integrating DBHub allows Cursor's Agent mode to "talk" to your databases. This means you can ask Cursor to fetch data, describe table structures, or even help you formulate complex SQL queries.

**Common Use Cases:**

-   **For Product Managers:**
    -   Quickly query product databases (e.g., "How many users signed up last week?" from a PostgreSQL DB).
    -   Explore data in a demo environment to understand schema or test hypotheses.
    -   Verify data points for reports without needing direct database client access.
-   **For Developers:**
    -   Inspect table structures and data directly within Cursor.
    -   Test SQL queries or generate them with AI assistance.
    -   Connect to various development or testing databases without switching tools.
    -   Use read-only mode for safely querying staging or production environments.

**Example Interactions (Conceptual - relies on Cursor's MCP integration):**

*   **Using Natural Language (Agent Mode):**
    -   "Connect to the demo DBHub and show me all tables."
    -   "In the employees table from the demo DBHub, show me the first 5 employees."
    -   "Using the PostgreSQL DBHub connection, what's the schema for the 'users' table?"
    -   "Draft a SQL query for my SQL Server DBHub to find all orders placed in the last 24 hours."

*   **MCP Interaction (Conceptual):**
    Cursor's Agent mode would communicate with the DBHub server using the Model Context Protocol. You wouldn't typically type raw MCP commands, but rather interact naturally, and Cursor handles the MCP communication in the background.

## Benefits of DBHub with MCP and Cursor

-   **Unified Interface:** Access diverse databases through a single, familiar interface (Cursor chat).
-   **AI-Powered SQL:** Leverage Cursor's AI to help write, explain, and debug SQL queries.
-   **Simplified Access:** Reduces the need for multiple database client tools or complex connection setups for quick queries.
-   **Enhanced Context for AI:** Provide direct database schema and data as context to the AI for more accurate and relevant assistance.

## Detailed Setup Guide for DBHub MCP Integration

This guide provides step-by-step instructions for setting up DBHub and integrating it with Cursor AI via MCP.

**Prerequisites:**

*   **Cursor AI:** Ensure you have Cursor installed.
*   **Node.js and npx:** DBHub is easily run using `npx`, which comes with Node.js. If you don't have Node.js, install it from [nodejs.org](https://nodejs.org/).
*   **Database Access:** Credentials and connection details for the database(s) you want to connect to (unless using demo mode).

**Setup Steps:**

1.  **Choose your DBHub Mode:**

    *   **Demo Mode (Easiest Start):**
        This uses an in-memory SQLite database with a sample "employee" dataset. No DSN is needed.
        Open your terminal and run:
        ```bash
        npx @bytebase/dbhub --demo --transport stdio
        ```
        Keep this terminal window open. This starts DBHub in `stdio` mode, ready for Cursor.

    *   **Connecting to a Real Database:**
        You'll need a Database Source Name (DSN) string.
        **DSN Formats:**
        | Database   | DSN Format                                                         | Example                                                                 |
        | ---------- | ------------------------------------------------------------------ | ----------------------------------------------------------------------- |
        | MySQL      | `mysql://[user]:[password]@[host]:[port]/[database]`       | `mysql://user:pass@localhost:3306/mydb?sslmode=disable`             |
        | MariaDB    | `mariadb://[user]:[password]@[host]:[port]/[database]`     | `mariadb://user:pass@localhost:3306/mydb?sslmode=disable`           |
        | PostgreSQL | `postgres://[user]:[password]@[host]:[port]/[database]`    | `postgres://user:pass@localhost:5432/mydb?sslmode=disable`          |
        | SQL Server | `sqlserver://[user]:[password]@[host]:[port]/[database]`   | `sqlserver://user:pass@localhost:1433/mydb?sslmode=disable`         |
        | SQLite     | `sqlite:///path/to/file.db` or `sqlite::memory:`           | `sqlite:///data/my_app.db`                                              |
        | Oracle     | `oracle://[user]:[password]@[host]:[port]/[service_name]` | `oracle://user:pass@localhost:1521/ORCL?sslmode=disable`            |

        **Running DBHub with your DSN:**
        Replace `"YOUR_DSN_STRING_HERE"` with your actual DSN.
        ```bash
        npx @bytebase/dbhub --dsN "YOUR_DSN_STRING_HERE" --transport stdio
        ```
        *(Optional: Add `--readonly` for read-only access).*
        Keep this terminal window open.

        **Oracle Special Considerations (Thick Mode):**
        If you encounter errors like "NJS-138" with Oracle, you need Thick Mode:
        1.  Download and install Oracle Instant Client.
        2.  Set the `ORACLE_LIB_DIR` environment variable:
            ```bash
            export ORACLE_LIB_DIR=/path/to/your/instantclient
            ```
        3.  Then run DBHub with your Oracle DSN.
        For Docker, use the `bytebase/dbhub-oracle-thick` image.

2.  **Configure MCP in Cursor AI:**

    *   1.  Open Cursor AI Settings (Cmd+, or Ctrl+,).
    *   2.  Navigate to "MCP" in the sidebar.
    *   3.  Click "Add new global MCP Server". This will open an `mcp.json` file (or create one if it doesn't exist).
    *   4.  Add a configuration for DBHub. Here's an example for the demo mode:

        ```json
        {
          "mcpServers": {
            // ... any existing servers ...
            "dbhub (Demo)": {
              "command": "npx",
              "args": [
                "-y", // Assumes you want to auto-confirm npx execution
                "@bytebase/dbhub",
                "--demo",
                "--transport",
                "stdio"
              ],
              "enabled": true // Ensure this is true
            }
            // Add another entry for a specific database if needed:
            // "dbhub (My PostgreSQL)": {
            //   "command": "npx",
            //   "args": [
            //     "-y",
            //     "@bytebase/dbhub",
            //     "--dsn", "postgres://user:pass@host:port/dbname?sslmode=disable",
            //     "--transport", "stdio"
            //     // Optional: "--readonly"
            //   ],
            //   "enabled": true
            // }
          }
        }
        ```
        **Important:**
        *   If you are *not* running `npx @bytebase/dbhub --demo --transport stdio` manually in a separate terminal (as per step 1), Cursor will try to launch it using this configuration.
        *   If you *are* running it manually, you might not need this MCP server entry if Cursor's agent can pick up `stdio` tools automatically (behavior can vary). However, having the config ensures Cursor knows how to launch it if needed. For simplicity and explicit control, running DBHub manually in `stdio` mode and then telling Cursor about it via an MCP config that *matches* the manual command is a robust approach.
        *   Adjust the `args` for your specific DSN if not using demo mode.
        *   The `-y` flag for `npx` auto-confirms its execution. You might remove it if you prefer manual confirmation, but this could interfere with Cursor launching it automatically.

    *   5.  Save the `mcp.json` file.
    *   6.  Return to the Cursor AI Settings (MCP Servers screen). The "dbhub (Demo)" entry should appear. A green status indicator usually means Cursor can connect to or launch the server.

3.  **Test in Chat:**

    *   Open a new chat in Cursor.
    *   Ensure **Agent Mode** is selected.
    *   Try some queries:
        *   "What tables are in the dbhub demo database?"
        *   "Show me the first 3 records from the 'employees' table in the dbhub demo."
        *   If you configured a connection to your own database: "Using dbhub My PostgreSQL, list all tables."

    If Cursor struggles to find the DBHub instance, ensure the `npx` command (either run manually or via the MCP config) is active and outputting in `stdio` mode. Check the Cursor logs for MCP connection details.

## Troubleshooting

-   **Red Indicator in MCP Settings:** Double-check your `mcp.json` command and arguments. Ensure `npx` is in your system's PATH.
-   **Cursor Can't Connect:**
    -   If running DBHub manually: Is the terminal window with DBHub still open and running without errors? Is it set to `--transport stdio`?
    -   If relying on Cursor to launch: Check Cursor's output/logs for errors related to `npx` or `dbhub`.
-   **DSN Issues:** Test your DSN string with a standard database client first to ensure it's correct. Pay attention to URL encoding for special characters in passwords or database names.
-   **Oracle Thick Mode:** Ensure `ORACLE_LIB_DIR` is correctly set in the environment where `npx` (and thus DBHub) is running. If Cursor launches DBHub, this environment variable needs to be available to Cursor's process or set globally.

By following this guide, you can unlock powerful database interaction capabilities directly within Cursor, streamlining workflows for both technical and non-technical users. 