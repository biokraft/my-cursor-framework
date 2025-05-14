# Quick Look: The `@Docs` Feature

Cursor includes a powerful feature known as "`@Docs`" that allows you to bring external documentation directly into your AI's context. While particularly invaluable for developers working with specific libraries or frameworks, the basic concept is useful for anyone wanting to ground the AI's knowledge in authoritative sources.

## What is the `@Docs` Feature?

Essentially, the `@Docs` feature lets you tell Cursor: "Hey, when you're helping me with this, pay special attention to *this* specific documentation."

You can typically point `@Docs` to:

-   **Web URLs:** Links to online documentation pages (e.g., official library APIs, framework guides, standards specifications).
-   **Local Files/Folders:** Markdown files, text files, or even entire folders of documentation within your project or on your local system.

When you use `@Docs`, Cursor will prioritize the information from these specified sources when generating responses, code, or explanations related to your query.

## Why is it Useful (Even for Non-Developers)?

-   **Accuracy:** Ensures the AI refers to the correct and most up-to-date information, rather than relying solely on its general training data (which might be outdated or too generic).
-   **Specificity:** If you're discussing a company-internal process documented on a specific wiki page, or need to adhere to a particular style guide, `@Docs` can help the AI stay on track.
-   **Focused Research:** When used with a Research Mode, `@Docs` can provide a starting point or a key reference for the AI to explore.

**Example Scenario (General):**

A Product Manager is drafting a specification for a new feature and wants to ensure it aligns with the company's publicly stated accessibility guidelines. They could use `@Docs` to point Cursor to the URL of these guidelines and then ask: "Review this feature draft and suggest improvements based on the accessibility guidelines I've provided with `@Docs`."

## A Note for Developers

For developers, the `@Docs` feature is a game-changer. It allows you to:

-   Feed the AI with the specific API documentation for the libraries you are using.
-   Ensure code generation adheres to the patterns and best practices outlined in framework documentation.
-   Quickly get help with library-specific functions or configurations.

We will explore the `@Docs` feature in much greater depth in **Part 2: Cursor for Developers**, specifically in the "[Mastering the @Docs Feature](../02-Cursor-for-Developers/01-Mastering-the-Docs-Feature.md)" section.

## How to Use `@Docs` (Basic)

Typically, you invoke it directly in the chat, often with a command like:

```plaintext
@Docs add [URL or path to local file/folder]
```

Or, Cursor might have a dedicated UI element for adding documentation sources.

Once added, the AI will consider this documentation for subsequent queries in that chat session or until the `@Docs` context is cleared or changed.

This brief introduction should give you an idea of its potential. For now, just be aware that it's another powerful tool in Cursor's arsenal for providing critical context to the AI. 