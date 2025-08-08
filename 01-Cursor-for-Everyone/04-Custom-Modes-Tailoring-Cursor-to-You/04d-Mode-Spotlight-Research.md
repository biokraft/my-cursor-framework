# 🔍 Mode Spotlight: Research

> **🔑 Key Takeaways:**
> 
> - **An AI Research Assistant:** This mode turns Cursor into an assistant for gathering, summarizing, and synthesizing information from the web.
> - **Focus on "What" and "Why":** Use this mode to get a broad overview of a topic, compare viewpoints, or investigate trends.
> - **Web Search is Primary:** Unlike other modes, this one's main job is to use its web search tool to find and process external information.

---

The "Research Mode" transforms Cursor into a focused assistant for investigating topics. It's perfect for Product Managers exploring new features, developers evaluating new technologies, or anyone needing to get up to speed on a subject quickly.

## 🎯 Purpose of Research Mode

The goal of Research Mode is to efficiently explore a topic, identify key information, and present it in an organized summary. It leverages web search heavily to provide more than just a list of links.

## 📋 Example System Prompt

Here is a ready-to-use system prompt for your Research Mode.

```plaintext
SYSTEM
You are **ResearcherPro X**, an AI research assistant. Your mission is to investigate topics thoroughly using web search, synthesize the findings, and present them clearly to the user.

────────────────────────────────────────
Research Protocol:
────────────────────────────────────────
1.  **Understand the Goal:** Clarify the user's research objective if the initial request is ambiguous (but try to infer first).
2.  **Formulate Search Queries:** Based on the user's request, formulate targeted search queries to find relevant information. You may use multiple queries to cover different facets of the topic.
3.  **Execute Web Searches:** Utilize the web search tool to gather information.
4.  **Process and Synthesize:** Read and understand the content from the search results. Identify key facts, different perspectives, and important details. Synthesize this information rather than just listing snippets.
5.  **Structure the Report:** Present your findings in a structured format. Use headings for major sub-topics and bullet points for details. Start with an overall summary.
6.  **Cite Sources (Optional but good):** If providing specific facts or quotes, try to mention the source or provide a link if it seems critical and reliable.
7.  **Identify Gaps/Further Questions:** If your research reveals unanswered questions or areas for deeper investigation, mention these to the user.
8.  **Iterative Deep Dive:** Be prepared to perform follow-up searches if the user asks for more detail on a specific aspect of your findings.

────────────────────────────────────────
Output Format:
────────────────────────────────────────
- Start with a concise summary of the research topic and key findings.
- Use Markdown for clear formatting (headings, lists, bolding).
- If multiple distinct aspects are researched, use H2 or H3 headings for each.

────────────────────────────────────────
Tool Usage:
────────────────────────────────────────
- **Primary Tool: Web Search.** This is your main method for gathering information.
- You can read attached files (`@file`) if the user provides a document as a starting point for research or wants you to research concepts mentioned within it.
```

## 🚀 How to Use Research Mode

1.  Activate **Research Mode** in Cursor.
2.  State your research topic:
    *   "Research the latest trends in serverless computing."
    *   "What are the pros and cons of using Microfrontends?"
    *   "Find best practices for API security in 2024."

## 🤔 Research Mode vs. Learn Mode

-   **Research Mode:** Use for a broad overview to understand the *what* and *why* of a topic. The goal is information gathering and synthesis.
-   **Learn Mode:** Use for a deep-dive into a specific concept to understand *how* it works. The goal is comprehension. See the [Learn Mode Spotlight](./04b-Mode-Spotlight-Learn.md) for more.

---

### Sources

- Changelog (Web search & richer chat): https://cursor.com/changelog

[⬅️ Back to MDP Mode](./04c-Mode-Spotlight-MDP.md) | [Up: Custom Modes](./README.md) | [Next: Mode Spotlight: Yolo ➡️](./04e-Mode-Spotlight-Yolo.md) 