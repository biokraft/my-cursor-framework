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

4.  **Combine `@Docs` with Specific Prompts:** After referencing a documentation source in chat using `@Docs [Name]`, tailor your prompts to make it clear you want the AI to use that context.
    *   First, in chat: `@Docs FastAPI Official`
    *   Then prompt: "Using the FastAPI documentation I provided, show me how to implement OAuth2 password flow with a Pydantic model for the user."
    *   First, in chat: `@Docs Internal UI Lib`
    *   Then prompt: "Based on the documentation for our internal UI library, generate a React component for a data table with sorting and pagination."

5.  **Iteratively Manage `@Docs` Context:** For a large project, you might have many documentation sources defined in settings. Reference the specific docs relevant to your current task using `@Docs [Name]`. Cursor typically allows you to see which `@Docs` are active and provides ways to clear the context if needed (e.g., a "Clear context" button or command if multiple docs are active).

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

A powerful workflow emerges when you combine `@Docs` with the creation of new Cursor Rules. This involves using `@Docs` to provide the AI with relevant documentation *during the rule definition process itself*, helping to create highly accurate and context-aware rules.

For a detailed guide on how to leverage `@Docs` for auto-generating rules from documentation, please see [Auto-Generating Rules from @Docs](./02-Crafting-Rules-for-Your-Tech-Stack/02b-Auto-Generating-Rules-from-Docs.md).

By mastering the `@Docs` feature, you transform Cursor from a general-purpose AI into a highly specialized assistant that understands the nuances of your specific tech stack, leading to more efficient and accurate development.

---

[⬅️ Back](../../README.md) | [Next: Crafting Rules for Your Tech Stack ➡️](./02-Crafting-Rules-for-Your-Tech-Stack/README.md) 
