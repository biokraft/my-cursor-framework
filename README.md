# A Comprehensive Guide to 🚀 Cursor AI 🚀

[![Project Status: Archived](https://img.shields.io/badge/status-archived-red?style=for-the-badge)](https://github.com/biokraft/my-cursor-framework)
[![GitHub release (latest by date)](https://img.shields.io/github/v/release/biokraft/my-cursor-framework)](https://github.com/biokraft/my-cursor-framework/releases/latest)

> **⚠️ Archived — no longer maintained**
>
> This repository is **discontinued**. Cursor and agent workflows have changed significantly since this guide was written, and I am no longer updating it.
>
> The content may still be useful as historical reference or for ideas, but expect outdated terminology, UI, and workflows. For current Cursor documentation, see [docs.cursor.com](https://docs.cursor.com) and the [changelog](https://cursor.com/changelog).
>
> Issues and pull requests will not be reviewed. Fork freely if you want to maintain your own version.

> **🔑 Key Takeaways:**
>
> - **🎯 For Everyone:** Start with [Part 1](./01-Cursor-for-Everyone/) to master core concepts like Rules, Custom Modes, and the Model Context Protocol (MCP).
> - **💻 For Developers:** Dive into [Part 2](./02-Cursor-for-Developers/) for advanced workflows, including tech-specific rules and the `SpecsForge` framework for spec-driven development, followed by smart implementation choices.
> - **🚀 Core Philosophy:** This guide emphasizes that providing clear, relevant context is the "golden rule" for getting the most out of Cursor.
> - **⚡ Smart Workflow Decisions:** Learn when to use **TDV mode** for complex features vs **Stock Agent + "Make a todo list"** for rapid scaffolding and setup tasks.
> - **🛠️ Actionable Resources:** The repository includes a rich set of [reusable rules](./.cursor/rules/) and practical examples to accelerate your learning.

Welcome to this personal collection of best practices, rules, and workflows designed to maximize your productivity with Cursor. This framework aims to help everyone, from Product Managers to Developers, harness the full potential of AI-assisted coding and documentation.

**💡 Pro Tip for Everyone (Especially Non-Developers):** One of the most impactful ways to boost your productivity with Cursor is through [Markdown-Driven Planning & Brainstorming](./01-Cursor-for-Everyone/08-Markdown-Driven-Planning.md). It's a simple yet powerful technique to manage knowledge and projects, and you'll find it covered in Part 1.

This repository is structured to guide you through understanding core Cursor concepts and then diving into advanced development workflows.

> Note: Cursor evolves quickly. Recent platform capabilities include **Background Agent** (with a dedicated panel and Slack launch), **BugBot** for PR reviews, **Memories**, **Jupyter Notebook editing**, **richer chat rendering** (Mermaid, tables), and improvements across settings, indexing, and dashboards. See the official changelog for details.

Sources: `https://cursor.com/en/changelog/1-0`, `https://cursor.com/changelog`

---

## 🎯 How This Guide is Structured

This framework is divided into two main parts. Before diving in, check the `README.md` in each subdirectory for a table of contents.

### 🌟 Part 1: [Cursor for Everyone](./01-Cursor-for-Everyone/README.md)

This section is designed for *anyone* using Cursor, regardless of their technical role. It covers fundamental concepts, setup, and features that enhance productivity for tasks like documentation, research, and project management.

-   📜 [The Golden Rule: Context is King](./01-Cursor-for-Everyone/00-The-Golden-Rule-Context-is-King.md)
-   👋 [Welcome to Cursor](./01-Cursor-for-Everyone/01-Welcome-to-Cursor.md)
-   🧩 [Understanding Cursor Rules](./01-Cursor-for-Everyone/02-Understanding-Cursor-Rules/README.md)
-   🧠 [Choosing Your AI Model](./01-Cursor-for-Everyone/03-Choosing-Your-AI-Model.md)
-   🎨 [Custom Modes: Tailoring Cursor to You](./01-Cursor-for-Everyone/04-Custom-Modes-Tailoring-Cursor-to-You/README.md)
-   ⚙️ [Essential Cursor Settings](./01-Cursor-for-Everyone/05-Essential-Cursor-Settings.md)
-   🔗 [The Model Context Protocol (MCP)](./01-Cursor-for-Everyone/06-The-Model-Context-Protocol-MCP/README.md)
-   👀 [Quick Look: The @Docs Feature](./01-Cursor-for-Everyone/07-Quick-Look-The-Docs-Feature.md)
-   💡 [Markdown-Driven Planning & Brainstorming](./01-Cursor-for-Everyone/08-Markdown-Driven-Planning.md)
    > 💼 **Product Managers:** Check this out!

---

### 💻 Part 2: [Cursor for Developers](./02-Cursor-for-Developers/README.md)

This section delves into advanced techniques and workflows tailored for developers. It covers topics like building tech-stack specific rules, the `SpecsForge` framework for planning, the `TDV` mode for implementation, and efficient debugging strategies. While aimed at developers, Product Managers and technical leads might also find these insights valuable.

-   宣言 [The Vibe Programmer Manifesto](./02-Cursor-for-Developers/00-The-Vibe-Programmer-Manifesto.md)
-   📚 [Mastering the @Docs Feature](./02-Cursor-for-Developers/01-Mastering-the-Docs-Feature.md)
-   🛠️ [Crafting Rules for Your Tech Stack](./02-Cursor-for-Developers/02-Crafting-Rules-for-Your-Tech-Stack/README.md)
-   ⚡ [The SpecsForge Framework](./02-Cursor-for-Developers/03-The-SpecsForge-Framework.md) & [🧪 The TDV Mode](./02-Cursor-for-Developers/03a-Mode-Spotlight-TDV.md)
    > 🧑‍💻 **Listen up devs:** this is where the secret sauce is at! Plus learn when to use the simple "Make a todo list" technique with stock Agent mode.
-   ⚙️ [Leveraging Terminal Integration for Debugging](./02-Cursor-for-Developers/04-Leveraging-Terminal-Integration.md)
-   ⇄ [Working Across Repositories](./02-Cursor-for-Developers/05-Working-Across-Repositories.md)

---

## ✨ Featured Workflow in Action: The SpecsForge Framework & TDV Mode

See the `SpecsForge` framework and `TDV` mode in action! This video gives a practical look at how to turn a high-level idea into a detailed specification (`SpecsForge`) and then into well-tested code (`TDV`). The footage is from my open-source CLI tool, [`automake`](https://github.com/biokraft/auto-make), an AI-native shell that turns natural language into actions.

[![Watch the SpecsForge Workflow Demo](https://img.youtube.com/vi/3mSPPsbOkyU/hqdefault.jpg)](https://youtu.be/3mSPPsbOkyU)

> This is a core concept from [Part 2: Cursor for Developers](./02-Cursor-for-Developers/03-The-SpecsForge-Framework.md) and demonstrates a powerful, spec-driven development workflow that is followed up by test-driven implementation.

---

## 🏁 Getting Started

1.  Explore **Part 1** to build a solid foundation in Cursor's core functionalities.
2.  If you're a developer, proceed to **Part 2** to learn about my specific coding workflows, including the `SpecsForge` framework and `TDV` mode.
3.  Adapt and adopt what works for you! Treat this as a snapshot in time — verify anything important against current Cursor docs before relying on it.

---

**Hint:** Interested to see how to have fun with Cursor? Try the [Yolo mode](./01-Cursor-for-Everyone/04-Custom-Modes-Tailoring-Cursor-to-You/04e-Mode-Spotlight-Yolo.md)! Here is what this can result in: [Yolo README](./Yolo-README.md).

## 📜 My Standard Cursor Rules

I recommend always starting with these foundational rules in your `.cursor/rules` directory:

-   [`00-cursor-rules.md`](./.cursor/rules/00-cursor-rules.md): Defines the general structure and guidelines for your cursor rules.
-   [`01-mdc-guidelines.md`](./.cursor/rules/01-mdc-guidelines.md): Provides specific instructions for working with `.mdc` (Markdown Custom) rule files.

Dive into the `.cursor/rules` directory in this repository to find my collection of reusable rules. Feel free to pick and choose what you need!

---

## Star History

<a href="https://www.star-history.com/#biokraft/my-cursor-framework&Date">
 <picture>
   <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/svg?repos=biokraft/my-cursor-framework&type=Date&theme=dark" />
   <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/svg?repos=biokraft/my-cursor-framework&type=Date" />
   <img alt="Star History Chart" src="https://api.star-history.com/svg?repos=biokraft/my-cursor-framework&type=Date" />
 </picture>
</a>

---

## 🙏 Acknowledgements & Sources

-   [From Design doc to code: the Groundhog AI coding assistant (and new Cursor vibecoding meta)](https://ghuntley.com/specs/)
-   [Cursor Rules Documentation](https://docs.cursor.com/context/rules)
-   [Cursor Custom Modes Documentation](https://docs.cursor.com/chat/custom-modes)
-   [Cursor Concepts (context, indexing, @Docs, etc.)](https://docs.cursor.com/get-started/concepts)
-   [Cursor Changelog (latest updates)](https://cursor.com/changelog)
-   [Cursor 1.0 Feature Highlights](https://cursor.com/en/changelog/1-0)

---

