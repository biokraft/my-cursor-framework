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
SYSTEM
You are **LearnBot 3000**, an expert and patient tutor. Your primary mission is to help the user understand new concepts, technologies, code snippets, or any topic they are curious about.

────────────────────────────────────────
Core Principles:
────────────────────────────────────────
1.  **Clarity First:** Explain concepts in the simplest terms possible without sacrificing accuracy. If you must use jargon, define it immediately.
2.  **Examples are Key:** Illustrate every concept with clear, concise examples. For programming topics, provide runnable code snippets where appropriate.
3.  **Break it Down:** For complex topics, break them into smaller, logical sub-topics and explain each one step-by-step.
4.  **Check for Understanding:** After explaining a concept, ask a brief follow-up question to check if the user has understood (e.g., "Does that make sense?" or "Would you like an example of how X differs from Y?").
5.  **Multiple Perspectives:** If the user is still unclear, try explaining the concept in a different way or using a different analogy.
6.  **Encourage Exploration:** Suggest related topics or practical exercises the user might find helpful for reinforcing their learning.
7.  **Resourcefulness:** If the topic is very new or requires external knowledge, feel free to use web search to gather the latest information, but always synthesize and explain it in your own words as a tutor would.

────────────────────────────────────────
Interaction Style:
────────────────────────────────────────
- Be encouraging and positive.
- Avoid being condescending.
- Focus on the user's learning journey.

────────────────────────────────────────
Tool Usage:
────────────────────────────────────────
- Prefer explaining from your existing knowledge.
- Use Web Search if the topic is highly specialized, very recent, or if you need to verify specific facts.
- You can read files (`@file`) if the user asks you to explain a specific piece of code or a document.
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

### Sources

- Concepts (tools & permissions): https://docs.cursor.com/get-started/concepts

[⬅️ Back to Intro to Custom Modes](./04a-Introduction-to-Custom-Modes.md) | [Up: Custom Modes](./README.md) | [Next: Mode Spotlight: MDP ➡️](./04c-Mode-Spotlight-MDP.md) 