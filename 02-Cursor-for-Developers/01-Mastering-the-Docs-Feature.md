# Mastering the `@Docs` Feature for Developers

While we introduced the `@Docs` feature in "Part 1: Cursor for Everyone," its true power for developers lies in its ability to deeply integrate external library and framework documentation into the AI's coding process. This section will explore how to leverage `@Docs` to make Cursor an even more effective coding partner when working with specific technologies.

## Why `@Docs` is Crucial for Developers

Modern development relies heavily on a multitude of libraries, frameworks, and APIs. Each comes with its own set of functions, classes, conventions, and best practices.

-   **AI's Knowledge Cutoff:** The AI's general training data has a knowledge cutoff date. It might not be aware of the latest versions of libraries, new features, or breaking changes.
-   **Specificity Matters:** General knowledge about a language (e.g., Python) is different from specific knowledge about a library (e.g., Django 4.2 vs. Django 5.0) or a niche SDK.
-   **Avoiding Deprecated Code:** `@Docs` helps prevent the AI from suggesting outdated or deprecated functions by pointing it to current documentation.
-   **Adhering to Best Practices:** Official documentation often contains crucial information about the intended use, performance considerations, and security best practices for a library.

By using `@Docs`, you provide focused, authoritative context that helps the AI generate code that is more accurate, up-to-date, and aligned with the specific technologies you're using.

To add a documentation source:
1. Go to Cursor's settings/preferences.
2. Locate the "Features" or "Docs" section.
3. Add a new documentation source by providing a descriptive **name** (e.g., "FastAPI Official", "Pydantic Latest") and the **URL** or local **path**.

To use an added documentation source in chat:
1. Type `@Docs` followed by a **space**.
2. Search for and select the **name** you assigned to the documentation source.

## Effective Strategies for Using `@Docs`

1.  **Target Key Libraries/Frameworks:** Identify the core libraries and frameworks for your project. Add their official documentation via Cursor settings, giving them memorable names.
    *   *Example:* If you're building a web app with FastAPI and Pydantic, add their official documentation in settings, perhaps named "FastAPI Official" and "Pydantic Docs".

2.  **Use Official Documentation URLs:** Whenever possible, link directly to the official online documentation when adding a source in settings. This is generally the most up-to-date source.
    *   In settings, add: Name: "FastAPI Official", URL: `https://fastapi.tiangolo.com/`
    *   In settings, add: Name: "Pydantic Latest", URL: `https://docs.pydantic.dev/latest/`

3.  **Include Specific API Reference Pages:** For very focused tasks, you can add documentation sources in settings that point to specific API reference pages or guides.
    *   In settings, add: Name: "FastAPI Path Params", URL: `https://fastapi.tiangolo.com/tutorial/path-params/` (when working on path parameters).

4.  **Leverage Local Documentation:** If you have local copies of documentation (e.g., Markdown files, downloaded manuals, or internal company SDK docs), you can add these as sources in settings using their file paths.
    *   In settings, add: Name: "Internal SDK", Path: `./docs/internal_api_sdk/`
    *   In settings, add: Name: "My Library Notes", Path: `./path/to/my_library_notes.md`

5.  **Combine `@Docs` with Specific Prompts:** After referencing a documentation source in chat using `@Docs [Name]`, tailor your prompts to make it clear you want the AI to use that context.
    *   First, in chat: `@Docs FastAPI Official`
    *   Then prompt: "Using the FastAPI documentation I provided, show me how to implement OAuth2 password flow with a Pydantic model for the user."
    *   First, in chat: `@Docs Internal UI Lib`
    *   Then prompt: "Based on the documentation for our internal UI library, generate a React component for a data table with sorting and pagination."

6.  **Iteratively Manage `@Docs` Context:** For a large project, you might have many documentation sources defined in settings. Reference the specific docs relevant to your current task using `@Docs [Name]`. Cursor typically allows you to see which `@Docs` are active and provides ways to clear the context if needed (e.g., a "Clear context" button or command if multiple docs are active).

## Example Workflow: Working with a New Library

Let's say you need to integrate a new data visualization library, `Plotly Express`, into your Python project.

1.  **Find Official Docs:** A quick search leads you to `https://plotly.com/python/plotly-express/`.
2.  **Add to Cursor Settings:**
    *   Go to Cursor settings -> Docs.
    *   Add new doc: Name: "Plotly Express", URL: `https://plotly.com/python/plotly-express/`
3.  **Ask for Help in Chat:**
    *   Type in chat: `@Docs Plotly Express`
    *   Then ask: "Okay, I've referenced the Plotly Express docs. Can you show me a simple example of how to create a scatter plot from a Pandas DataFrame using this library?"
    *   "Based on the Plotly Express documentation, how do I customize the colors and add a title to my chart?"
    *   "Generate a Python function that takes a DataFrame and column names, and returns a Plotly Express bar chart figure, ensuring it follows best practices from the docs."

## `@Docs` and Cursor Rules

A powerful workflow emerges when you combine `@Docs` with the creation of new Cursor Rules. When defining a rule that pertains to a specific library, framework, or API, you can use `@Docs` to provide the AI with the relevant documentation *during the rule definition process itself*.

For example, imagine you want to create a Cursor Rule that outlines best practices for using the Jira Multi-Connector Platform (MCP) tools. You could:

1.  Add the official Atlassian MCP documentation to Cursor settings:
    *   Name: "Atlassian MCP Docs", URL: `<URL to Atlassian MCP documentation>`
2.  Then, when prompting Cursor to help you draft the rule, reference it in chat:
    *   `@Docs Atlassian MCP Docs`
    *   Then prompt: "Help me create a Cursor Rule for Jira MCP usage. It should emphasize best practices for searching issues and creating new ones, based on the Atlassian MCP documentation I just referenced."

This approach allows you to create highly accurate and context-aware rules. The AI can extract key principles, function names, and recommended patterns directly from the authoritative source you provide, leading to more effective and precise custom rules for your projects.

This synergy—using `@Docs` to inform the creation of Cursor Rules—ensures that your custom instructions are not only well-defined but also grounded in the latest official guidelines for the technologies you use. It's a way to go full circle, leveraging documentation to build better, more intelligent rules for Cursor.

By mastering the `@Docs` feature, you transform Cursor from a general-purpose AI into a highly specialized assistant that understands the nuances of your specific tech stack, leading to more efficient and accurate development. 