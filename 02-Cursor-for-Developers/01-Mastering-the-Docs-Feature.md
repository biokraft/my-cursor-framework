# Mastering the `@Docs` Feature for Developers

While we introduced the `@Docs` feature in "Part 1: Cursor for Everyone," its true power for developers lies in its ability to deeply integrate external library and framework documentation into the AI's coding process. This section will explore how to leverage `@Docs` to make Cursor an even more effective coding partner when working with specific technologies.

## Why `@Docs` is Crucial for Developers

Modern development relies heavily on a multitude of libraries, frameworks, and APIs. Each comes with its own set of functions, classes, conventions, and best practices.

-   **AI's Knowledge Cutoff:** The AI's general training data has a knowledge cutoff date. It might not be aware of the latest versions of libraries, new features, or breaking changes.
-   **Specificity Matters:** General knowledge about a language (e.g., Python) is different from specific knowledge about a library (e.g., Django 4.2 vs. Django 5.0) or a niche SDK.
-   **Avoiding Deprecated Code:** `@Docs` helps prevent the AI from suggesting outdated or deprecated functions by pointing it to current documentation.
-   **Adhering to Best Practices:** Official documentation often contains crucial information about the intended use, performance considerations, and security best practices for a library.

By using `@Docs`, you provide focused, authoritative context that helps the AI generate code that is more accurate, up-to-date, and aligned with the specific technologies you're using.

## Effective Strategies for Using `@Docs`

1.  **Target Key Libraries/Frameworks:** Identify the core libraries and frameworks for your project. These are the prime candidates for `@Docs`.
    *   *Example:* If you're building a web app with FastAPI and Pydantic, providing their official documentation via `@Docs` is highly beneficial.

2.  **Use Official Documentation URLs:** Whenever possible, link directly to the official online documentation. This is generally the most up-to-date source.
    *   `@Docs add https://fastapi.tiangolo.com/`
    *   `@Docs add https://docs.pydantic.dev/latest/`

3.  **Include Specific API Reference Pages:** For very focused tasks, you can point `@Docs` to specific API reference pages or guides within the larger documentation.
    *   `@Docs add https://fastapi.tiangolo.com/tutorial/path-params/` (when working on path parameters).

4.  **Leverage Local Documentation:** If you have local copies of documentation (e.g., Markdown files, downloaded manuals, or internal company SDK docs), you can add these too.
    *   `@Docs add ./docs/internal_api_sdk/`
    *   `@Docs add ./path/to/my_library_notes.md`

5.  **Combine `@Docs` with Specific Prompts:** After adding documentation, tailor your prompts to make it clear you want the AI to use that context.
    *   "Using the FastAPI documentation I provided with `@Docs`, show me how to implement OAuth2 password flow with a Pydantic model for the user."
    *   "Based on the `@Docs` for our internal UI library, generate a React component for a data table with sorting and pagination."

6.  **Iteratively Add/Remove `@Docs` Context:** For a large project, you might have many potential documentation sources. You can add specific docs relevant to your current task and then clear or replace them as you switch focus to keep the AI's context targeted.
    *   Cursor usually has commands to view current `@Docs` or clear them (e.g., `@Docs list`, `@Docs clear`).

## Example Workflow: Working with a New Library

Let's say you need to integrate a new data visualization library, `Plotly Express`, into your Python project.

1.  **Find Official Docs:** A quick search leads you to `https://plotly.com/python/plotly-express/`.
2.  **Add to Cursor:** In Cursor chat, you type: `@Docs add https://plotly.com/python/plotly-express/`
3.  **Ask for Help:**
    *   "Okay, I've added the Plotly Express docs. Can you show me a simple example of how to create a scatter plot from a Pandas DataFrame using this library?"
    *   "Based on the Plotly Express documentation, how do I customize the colors and add a title to my chart?"
    *   "Generate a Python function that takes a DataFrame and column names, and returns a Plotly Express bar chart figure, ensuring it follows best practices from the docs."

## `@Docs` and Cursor Rules

A powerful workflow emerges when you combine `@Docs` with the creation of new Cursor Rules. When defining a rule that pertains to a specific library, framework, or API, you can use `@Docs` to provide the AI with the relevant documentation *during the rule definition process itself*.

For example, imagine you want to create a Cursor Rule that outlines best practices for using the Jira Multi-Connector Platform (MCP) tools. You could:

1.  Add the official Atlassian MCP documentation to Cursor:
    *   `@Docs add <URL to Atlassian MCP documentation>`
2.  Then, when prompting Cursor to help you draft the rule, you can instruct it to base the rule on the provided documentation:
    *   "Help me create a Cursor Rule for Jira MCP usage. It should emphasize best practices for searching issues and creating new ones, based on the Atlassian MCP documentation I just added with `@Docs`."

This approach allows you to create highly accurate and context-aware rules. The AI can extract key principles, function names, and recommended patterns directly from the authoritative source you provide, leading to more effective and precise custom rules for your projects.

This synergy—using `@Docs` to inform the creation of Cursor Rules—ensures that your custom instructions are not only well-defined but also grounded in the latest official guidelines for the technologies you use. It's a way to go full circle, leveraging documentation to build better, more intelligent rules for Cursor.

By mastering the `@Docs` feature, you transform Cursor from a general-purpose AI into a highly specialized assistant that understands the nuances of your specific tech stack, leading to more efficient and accurate development. 