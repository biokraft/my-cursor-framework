# Mode Spotlight: Research Mode

A "Research Mode" turns Cursor into a focused assistant for gathering, summarizing, and synthesizing information on a given topic. This is incredibly useful for Product Managers investigating new features, developers exploring new technologies, or anyone needing to quickly get up to speed on a particular subject.

## Purpose of Research Mode

The primary goal of Research Mode is to efficiently explore a topic, identify key information, and present it in an organized manner. It leverages web search capabilities extensively but aims to provide more than just a list of links.

## Key Characteristics & Behaviors

An effective Research Mode should:

-   **Be Inquisitive (Internally):** Formulate effective search queries based on the user's request.
-   **Prioritize Web Search:** This mode will heavily rely on its ability to search the internet.
-   **Synthesize Information:** Don't just regurgitate search results. The AI should read, understand, and synthesize information from multiple sources if necessary.
-   **Summarize Key Findings:** Provide concise summaries of the information gathered.
-   **Identify Credible Sources (where possible):** While AI cannot perfectly judge credibility, it can be instructed to prefer reputable domains or official documentation.
-   **Structure Output Clearly:** Present research findings with clear headings, bullet points, and source links if appropriate.
-   **Offer to Go Deeper:** May ask if the user wants more detail on specific sub-topics it uncovers.

## Example System Prompt for Research Mode

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

## How to Use Research Mode

1.  **Activate Research Mode** in Cursor.
2.  **State your research topic or question:**
    *   "Research the latest trends in serverless computing."
    *   "What are the pros and cons of using Microfrontends?"
    *   "Find information on the best practices for API security in 2024."
    *   "Investigate the company 'Acme Corp' and summarize their main products."

Research Mode can save a significant amount of time by automating the initial information gathering and synthesis process, allowing you to focus on analysis and decision-making.

## Recommended Usage Scenarios

Here are some situations where Research Mode excels:

*   **Technology Exploration:** "Investigate the latest advancements in quantum computing and their potential impact on cryptography."
*   **Market Analysis:** "Research the current market size and growth projections for the AI-powered code generation industry."
*   **Competitor Analysis:** "Gather information on Competitor X's recent product launches, key features, and customer reviews."
*   **Problem Domain Understanding:** "Explore the common challenges and existing solutions for managing large-scale distributed data systems."
*   **Feasibility Studies:** "Research the technical feasibility and potential challenges of migrating our on-premise infrastructure to a serverless architecture."
*   **Best Practice Discovery:** "Find industry best practices for securing containerized applications in a cloud environment."
*   **Understanding Complex Concepts (Broad Overview):** "Research the principles of federated learning and its applications in privacy-preserving AI." (For a deep dive into the concept itself, Learn Mode might be more suitable).

## When to Use Research Mode vs. Learn Mode

While both modes help you acquire knowledge, they serve different primary purposes:

*   **Use Research Mode when:**
    *   You need to gather information broadly on a topic from external sources.
    *   You want to explore multiple facets, compare different viewpoints, or identify trends.
    *   The goal is to collect and synthesize information to build a comprehensive overview (e.g., for a report, decision-making, or feature investigation).
    *   You need to understand the "what" and "why" across a landscape.

*   **Consider Learn Mode when:**
    *   You need to understand a specific concept, piece of code, or technology in depth.
    *   The goal is direct comprehension and skill acquisition.
    *   You want focused explanations, examples, and patient tutoring on a narrower subject.
    *   You need to understand the "how" of something specific.

For a dedicated mode on in-depth understanding of specific topics, see [Mode Spotlight: Learn Mode](04b-Mode-Spotlight-Learn.md).

---

[⬅️ Back to Main README](../../../README.md) 