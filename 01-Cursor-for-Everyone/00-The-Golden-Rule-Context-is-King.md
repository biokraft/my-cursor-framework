# 📜 The Golden Rule: Context is King

> **🔑 Key Takeaways:**
> 
> - **Quality In, Quality Out:** The usefulness of the AI's response is directly proportional to the quality of the context you provide.
> - **Be Specific:** Use `@` mentions for files and symbols to give the AI precise information.
> - **Leverage Cursor's Tools:** Use features like `@Docs`, Rules, and the Model Context Protocol (MCP) to provide rich, standing context.
> - **One Task, One Chat:** Start a new chat for each new task to avoid context pollution and keep the AI focused.

---

The single most important principle for working effectively with Large Language Models (LLMs) like those in Cursor is: **Context is King**.

LLMs don't "know" things like humans do. They generate responses based on patterns learned from data and, most importantly, the specific information you provide in your prompts. The more relevant and clear your context, the better the AI's output.

## 🎯 Why Context Matters

-   **Reduces Ambiguity:** Clear context helps the AI understand your exact request, avoiding generic or off-target responses.
-   **Improves Accuracy:** Providing relevant code, documentation, or project details allows the AI to generate solutions that fit your specific situation.
-   **Increases Efficiency:** Good context means fewer follow-up questions and less time spent clarifying.
-   **Unlocks Advanced Features:** Tools like Rules and `@Docs` are designed to help you feed the AI high-quality context seamlessly.

## 🛠️ How to Provide Effective Context in Cursor

Here are the primary ways to provide context, which we will explore throughout this guide:

1.  **💬 Explicitly in Your Prompts:**
    *   Be specific in your questions.
    *   Reference files (`@file.py`) or symbols (`@my_function`) directly in the chat.

2.  **⚙️ Using Cursor's Built-in Features:**
    *   **`@ Mentions`:** Use `@` to pull in files, symbols, or entire folders.
    *   **`@Docs` Feature:** Point Cursor to specific documentation (local files or web URLs) to ground its knowledge.
    *   **Model Context Protocol (MCP):** Integrate with external tools like Jira or Confluence.
    *   **Web Search:** Allow the agent to search the web for information.

3.  **⚖️ Defining Cursor Rules (`.cursor/rules`):**
    *   Create standing instructions and coding standards that Cursor should always follow.

> **💡 Pro Tip: Isolate Your Tasks**
>
> Use a chat session for one task and one task only. If the AI starts giving strange responses, it's a sign that the context has become cluttered. Start a new chat.
>
> As Geoffrey Huntley advises: *"If the bowling ball is in the gutter, there's no saving it. It's in the gutter."*
> — [Geoffrey Huntley](https://ghuntley.com/gutter/)

---

[⬅️ Back to main README](../README.md) | [Up: Cursor for Everyone](../README.md) | [Next: Welcome to Cursor ➡️](./01-Welcome-to-Cursor.md) 