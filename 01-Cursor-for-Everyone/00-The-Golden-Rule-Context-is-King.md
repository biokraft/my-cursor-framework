# The Golden Rule: Context is King

The single most important principle to remember when working with Large Language Models (LLMs) like the ones powering Cursor is: **Context is King**.

LLMs don't "know" anything in the human sense. They generate responses based on the patterns they've learned from vast amounts of text data AND, crucially, the specific information you provide them in your prompts. The more relevant, specific, and clear context you give, the better, more accurate, and more useful their output will be.

## Why Context Matters

-   **Reduces Ambiguity:** Clear context helps the AI understand precisely what you're asking for, avoiding generic or off-target responses.
-   **Improves Accuracy:** Providing relevant code snippets, documentation excerpts, or project details allows the AI to generate code or explanations that fit your specific situation.
-   **Increases Efficiency:** Good context means fewer follow-up questions and less time spent clarifying your requests. The AI can get it right (or closer to right) the first time.
-   **Unlocks Advanced Capabilities:** Features like Cursor Rules, the `@Docs` feature, and the Model Context Protocol (MCP) are all designed to help you feed the AI rich, high-quality context seamlessly.

## How to Provide Effective Context in Cursor

Throughout this guide, we'll explore various methods for providing context. Here are the key ways:

1.  **Explicitly in Your Prompts:**
    *   Be specific in your questions and instructions.
    *   Reference file names (`@file.py`) or symbols (`@my_function`) directly in the chat.
2.  **Using Cursor's Context Features:**
    *   **`@` Mentions:** Use `@` to reference files, symbols, or folders in your workspace. Cursor will automatically pull in relevant code or information.
    *   **`@folders`:** Include entire folders (or even your whole codebase) in the context. Enable "Full folder contents" in settings for this. A small icon will indicate if a folder is too large to be fully included.
    *   **The `@Docs` Feature:** Point Cursor to specific documentation (local files or web URLs) to ground its knowledge in your project's or library's specifics. (More on this later, especially for developers).
    *   **Model Context Protocol (MCP):** Integrate Cursor with external tools like Jira or Confluence to bring in context from issues, wikis, and other project management resources.
    *   **Search:** This is by default enabled in the agent mode and enables cursor to search the web if prompted to do so. Otherwise its also possible to paste in URLs straight from your browser and cursor will read those
3.  **Cursor Rules (`.cursor/rules`):**
    *   Define standing instructions, coding standards, and project-specific information that Cursor should always consider.

**Remember:** Always think about what information the AI needs to best help you. If you're getting subpar results, the first thing to check is whether you've provided enough (and the right kind of) context.

> **Pro Tip:** Always use chat sessions for one task and one task only. If your chat starts to do weird stuff, it's time to start a new chat. As Geoffrey Huntley put it:
>
> "My #1 recommendation for people these days is to use a context window for one task, and one task only. If your coding agent is misbehaving, it's time to create a new context window. If the bowling ball is in the gutter, there's no saving it. It's in the gutter."
>
> — [Geoffrey Huntley](https://ghuntley.com/gutter/)

---

[⬅️ Back](../README.md) | [Next: Welcome to Cursor ➡️](./01-Welcome-to-Cursor.md) 