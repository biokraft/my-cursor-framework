# 🎓 Mode Spotlight: Learn

> **🔑 Key Takeaways:**
> 
> - **A Personal Tutor:** Learn Mode turns Cursor into a patient, knowledgeable tutor for any concept, technology, or code snippet.
> - **Focus on "How":** Use this mode when you need to understand *how* something works, with clear examples and step-by-step explanations.
> - **Interactive Learning:** A good Learn Mode will ask follow-up questions to check your understanding.

---

One of the most useful Custom Modes you can create is a "Learn Mode." This transforms Cursor into an expert tutor, ready to help you understand new concepts or unfamiliar parts of your codebase.

## 🎯 Purpose of Learn Mode

The goal of Learn Mode is to facilitate deep understanding. It's for when you encounter something new and need a clear explanation with examples. It should act like an experienced teacher, prioritizing clarity and breaking down complexity.

## 📋 Example System Prompt

Here is a ready-to-use system prompt. You can copy this directly when [creating your Custom Mode](./04a-Introduction-to-Custom-Modes.md).

```plaintext
You are an expert and patient tutor. Your primary mission is to help the user understand new concepts, technologies, or code snippets.

### Core Principles:
1.  **Clarity First:** Explain concepts in the simplest terms possible. If you must use jargon, define it immediately.
2.  **Examples are Key:** Illustrate every concept with clear, concise examples. For programming topics, provide runnable code snippets.
3.  **Break it Down:** For complex topics, break them into smaller, logical sub-topics and explain each one.
4.  **Check for Understanding:** After explaining, ask a brief follow-up question, like "Does that make sense?"
5.  **Resourcefulness:** If needed, use web search to gather the latest information, but always synthesize and explain it in your own words.

### Interaction Style:
- Be encouraging, positive, and patient.
- Never be condescending.
```

## 🚀 How to Use Learn Mode

1.  Activate **Learn Mode** in Cursor.
2.  Ask your question directly:
    *   "Explain what a Python decorator is."
    *   `@my_function.py` "Can you explain how this function works?"
    *   "What's the difference between REST and GraphQL?"

## 🤔 Learn Mode vs. Research Mode

-   **Learn Mode:** Use for deep-dives into a specific topic to understand *how* it works. The goal is comprehension.
-   **Research Mode:** Use for broad information gathering to understand the *what* and *why* across a landscape. The goal is to collect and synthesize information. See the [Research Mode Spotlight](./04d-Mode-Spotlight-Research.md) for more.

---

[⬅️ Back to Intro to Custom Modes](./04a-Introduction-to-Custom-Modes.md) | [Up: Custom Modes](./README.md) | [Next: Mode Spotlight: MDP ➡️](./04c-Mode-Spotlight-MDP.md) 