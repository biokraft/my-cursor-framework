# 📄 Quick Look: The @Docs Feature

> **🔑 Key Takeaways:**
> 
> - **Provide Authoritative Sources:** The `@Docs` feature lets you point the AI to specific external documentation (like a library's official website or your company's style guide).
> - **Improves Accuracy:** This ensures the AI uses up-to-date and correct information from a source you trust, rather than just its general training data.
> - **Two-Step Process:** 1) Add the documentation URL in Cursor's settings. 2) Reference it in chat by typing `@Docs` and selecting the name you gave it.
> - **More for Developers:** While useful for anyone, this feature is explored in much greater detail in the "Cursor for Developers" section.

---

The `@Docs` feature is a powerful way to ground the AI's knowledge in authoritative sources you provide. It tells Cursor: "When helping me, pay special attention to *this specific documentation*."

## 🤔 What is it for?

You use `@Docs` to point the AI to a specific URL, like an official library's API documentation or your company's internal wiki. This makes the AI's responses more accurate and specific to your needs.

### How to Use It (The Gist)

Using `@Docs` is a simple two-step process:

1.  **Add Your Source:** In Cursor's settings, go to the "Docs" section and add a new documentation source. You'll give it a memorable name and provide the URL.  
    ![Add Docs Source UI](../assets/add_docs_sources_ui.png)

2.  **Reference it in Chat:** In the chat box, type `@Docs`, press space, and select the source you just added by its name.

Now, for the rest of that chat session, the AI will prioritize the information from that source.

## A Teaser for Developers

This feature is a game-changer for developers. We will dive much deeper into this topic in **Part 2: Cursor for Developers**, in the "[Mastering the @Docs Feature](../02-Cursor-for-Developers/01-Mastering-the-Docs-Feature.md)" section.

---

### Sources

- Concepts (@Docs, context): https://docs.cursor.com/get-started/concepts
- Changelog (PDF parsing/@link & chat rendering): https://cursor.com/changelog

[⬅️ Back to MCP](./06-The-Model-Context-Protocol-MCP/README.md) | [Up: Cursor for Everyone](../README.md) | [Next: Markdown-Driven Planning ➡️](./08-Markdown-Driven-Planning.md) 