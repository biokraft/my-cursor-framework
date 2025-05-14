# Cursor Rules: What, Why, and How?

Cursor Rules are a powerful feature that allows you to provide persistent, project-specific instructions to the AI. Think of them as a set of guidelines or a "style guide" that Cursor consults to ensure its responses and actions align with your project's conventions, standards, and technical requirements.

## What are Cursor Rules?

-   **Persistent Instructions:** Unlike one-off prompts in the chat, rules are stored in your project (typically in a `.cursor/rules/` directory) and are automatically considered by the AI.
-   **Markdown-Based:** Rules are written in Markdown (`.md` or `.mdc` for Markdown Custom), making them easy to create, read, and manage.
-   **Contextual Guidance:** They provide crucial context about your coding style, architectural patterns, preferred libraries, documentation standards, and more.

## Why Use Cursor Rules?

-   **Consistency:** Enforce consistent coding styles, naming conventions, and architectural patterns across your project, even when multiple people (or AI) contribute.
-   **Accuracy:** Help the AI generate more accurate and relevant code or suggestions by providing it with specific knowledge about your project that it wouldn't otherwise have.
-   **Efficiency:** Reduce the need to repeat common instructions or corrections in every prompt. Define it once in a rule, and Cursor remembers.
-   **Knowledge Sharing:** Codify team best practices and project-specific knowledge, making it easier for new team members (and the AI) to get up to speed.
-   **Customization:** Tailor Cursor's behavior to the unique needs of your project or organization.

## How Do They Work?

1.  **Create a `.cursor/rules/` Directory:** In the root of your project, create this directory to store your rule files.
2.  **Write Rules in Markdown:** Create `.md` or `.mdc` files within this directory. Each file can represent a specific rule or a collection of related guidelines.
    *   Use clear headings, bullet points, and code blocks to structure your rules.
    *   The AI is trained to understand instructions written in natural language within these files.
3.  **Automatic Context:** Cursor automatically loads and considers rules from the `.cursor/rules/` directory when you interact with the AI within that project.
4.  **Specificity and Overrides:** You can have general rules and more specific ones. The AI will try to apply the most relevant rules based on the context of your request.

## Essential Base Rules

It's highly recommended to include the following two foundational rules in any project, as also mentioned in the main [README.md](../README.md#my-standard-cursor-rules):

-   **[`00-cursor-rules.md`](../../.cursor/rules/00-cursor-rules.md):** This rule (which you should have in your project's `.cursor/rules` directory) typically defines the general structure for *other* rules. It might specify how to name rules, how to version them, or general principles for writing effective rules.
-   **[`01-mdc-guidelines.md`](../../.cursor/rules/01-mdc-guidelines.md):** If you plan to use `.mdc` (Markdown Custom) files for more structured or programmatic rules, this file provides guidelines on that format.

(You can find examples of these in the `.cursor/rules` directory of this framework repository.)

In the next sections, we'll explore how to develop rules interactively and use them for specific purposes like documentation. 