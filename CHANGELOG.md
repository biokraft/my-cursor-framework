# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## Release v1.3.3 - Cursor Docs Sync (GPT-5 pass)

### 📚 Documentation

- Synced the entire guide with the latest Cursor docs & changelog. Added official sources throughout, removed outdated BETA labels, referenced new features (Background Agent, BugBot, Memories, Jupyter Notebook editing, richer chat rendering), and updated screenshots for the setup guide.
- Enhanced Essential Settings with `.gitignore` handling, `.cursorignore`, global ignore patterns, Background Agent panel shortcut (Cmd/Ctrl+E), and dashboard usage notes.
- Updated MCP docs (Inspector, one-click/OAuth notes) and validated Atlassian/DBHub guidance.
- Finalized developer docs sources and terminology alignment.
- Essential Settings refinements:
  - Project structure is now provided by default; removed the old toggle description and image.
  - Rewrote Auto-run Mode to match the new UI (mode selector + command allowlist) and added safety guidance.
  - Refreshed Web Search section and screenshot.
- @Docs quick-look: improved Sources block formatting for consistency.
- Assets refreshed:
  - Updated: `assets/web_search_tool.png`, `assets/add_docs_sources_ui.png`, `assets/custom_modes_setup_ui.png`, `assets/auto_run_mode.png`
  - Removed (deprecated toggle): `assets/include_project_structure.png`
  - Unchanged: `assets/add_custom_mode.png`

### 🔧 Maintenance

- Removed temporary checklist file `gpt5.md` now that all items are complete.

[v1.3.3]: https://github.com/biokraft/my-cursor-framework/compare/v1.3.2...v1.3.3

## Release v1.3.2 - The "Make a Todo List" Revolution & Cross-Platform Enhancement

### ✨ Features

-   **🎯 "Make a Todo List" Technique:** Introduced the extremely easy yet game-changing **"Make a todo list"** phrase that transforms scattered AI output into organized, actionable steps - perfect for rapid prototyping and project scaffolding.
-   **🚀 Cross-Platform Claude Code Integration:** Enhanced [SpecsForge Framework](./02-Cursor-for-Developers/03-The-SpecsForge-Framework.md) with [Claude Code](https://www.anthropic.com/claude-code) support, enabling seamless cross-platform AI development workflows.
-   **⚡ Smart Implementation Decision Guide:** Added comprehensive decision matrix for choosing between **TDV Mode** (complex features), **Stock Agent + "Make a todo list"** (rapid scaffolding), and **Claude Code** (cross-platform alternative).

### 📚 Documentation

-   **Enhanced SpecsForge Framework:** Expanded [SpecsForge documentation](./02-Cursor-for-Developers/03-The-SpecsForge-Framework.md) with multiple implementation paths, workflow decision points, and Claude Code integration patterns.
-   **Workshop Materials Enhancement:** Significantly improved [CLI Tool Workshop](./workshop/02-uc-cli-tool/README.md) with detailed guidance on the "Make a todo list" technique and when to use different approaches.
-   **Navigation Improvements:** Updated main [README](./README.md) to highlight smart workflow decisions and the new "Make a todo list" technique for broader accessibility.

### 🔧 Improvements

-   **Cross-Reference Integration:** Added proper linking between SpecsForge, TDV Mode, and the new rapid prototyping techniques for seamless workflow transitions.
-   **User Experience:** Clarified when to use each approach based on task complexity, making the framework more accessible to both beginners and advanced users.

[v1.3.2]: https://github.com/biokraft/my-cursor-framework/compare/v1.3.1...v1.3.2

## Release v1.3.1 - Rules & Guidelines Expansion

### ✨ Features

-   **Diagram & Build Rules:** Added Mermaid best practices for error-free diagrams and Makefile guidelines for reliable build automation.
-   **C++ Development Suite:** Introduced comprehensive 5-rule set covering architecture, resource management, modern idioms, and code style for new C++ features.  
-   **Ollama LLM Integration:** Added 4 specialized rules for Ollama setup, Docker containerization, smolagents integration, and production deployment.
-   **Docker Compose Expansion:** Enhanced Docker guidelines with security best practices and AWS local development patterns.

### 🔧 Maintenance

-   **Project Setup:** Updated .gitignore and improved overall project organization.

[v1.3.1]: https://github.com/biokraft/my-cursor-framework/compare/v1.3.0...v1.3.1

## Release v1.3.0 - Documentation Enhancements

### 📚 Documentation

-   **TDV Mode:** Added comprehensive documentation for Test-Driven Vibe (TDV) Mode, detailing its integration with the SpecsForge framework.
-   **README Updates:** Enhanced navigation and updated links across multiple documentation sections for better user experience.
-   **Formatting:** Fixed README formatting issues and improved overall documentation consistency.

[v1.3.0]: https://github.com/biokraft/my-cursor-framework/compare/v1.2.0...v1.3.0

## Release v1.2.0 - New Rules and Workshop Demos

### ✨ Features

-   **Workflow & Docs:** Added extensive new guidelines for README badges, JIRA formatting, and `uv` usage.
-   **Rules Engine:** Introduced new rule sets for `aiogram`, `smolagents`, and `Phaser 3` to enhance AI-assisted development.
-   **Use Cases:** Included new workshop demos and practical examples for using the framework.

### ♻️ Refactoring

-   **TDV Mode:** Refactored the Test-Driven Vibe (`TDV`) concept from a standalone framework to an integrated mode within Cursor, simplifying its application.

[v1.2.0]: https://github.com/biokraft/my-cursor-framework/compare/v1.1.0...v1.2.0 

 