# 📜 Cursor Rules: What, Why, and How?

> **🔑 Key Takeaways:**
> 
> - **Persistent Instructions:** Rules are `.mdc` files in your `.cursor/rules` directory that give the AI standing instructions for your project.
> - **Enforce Consistency:** Use rules to enforce coding styles, architectural patterns, and documentation standards automatically.
> - **Frontmatter is Key:** The `---` block at the top of a rule file (`description`, `globs`, `alwaysApply`) controls when and how the rule is used.
> - **Natural Language:** Write rules in clear, natural Markdown. The AI is trained to understand them.

---

Cursor Rules are a powerful feature for providing persistent, project-specific instructions to the AI. Think of them as a "style guide" that Cursor consults to ensure its responses align with your project's conventions and requirements.

## 🤔 What Are Cursor Rules?

-   **Persistent Instructions:** Unlike one-off prompts, rules are stored in `.cursor/rules/` and are automatically considered by the AI.
-   **Markdown Custom (MDC) Files:** Rules are written in `.mdc` files, which combine human-readable Markdown with a machine-readable configuration block (frontmatter).
-   **Contextual Guidance:** They provide crucial context about your coding style, preferred libraries, and documentation standards.

## ✨ Why Use Cursor Rules?

-   **Consistency:** Enforce consistent coding styles and patterns.
-   **Accuracy:** Help the AI generate more accurate and relevant code by giving it project-specific knowledge.
-   **Efficiency:** Reduce the need to repeat common instructions in every prompt. Define it once in a rule.
-   **Knowledge Sharing:** Codify team best practices, making it easier for new members (and the AI) to get up to speed.

## ⚙️ How Do They Work?

1.  **Create a `.cursor/rules/` Directory:** Add this folder to your project's root.
2.  **Write Rules in `.mdc` Files:** Each `.mdc` file is a rule. It must start with a YAML-like frontmatter section enclosed in `---`. The rest of the file is standard Markdown.
3.  **Automatic Context:** Cursor automatically loads rules from this directory based on their frontmatter and your current context.

### Understanding MDC Frontmatter

The frontmatter block at the top of every `.mdc` file is critical for configuring how a rule is applied.

```yaml
---
description: A brief, agent-friendly explanation of the rule's purpose.
globs: '**/.*.py,src/**/*.js' # Optional: Comma-separated file patterns.
alwaysApply: false # Optional: Set to true for global rules.
---
```

**Key Properties:**

-   **`description` (Required):**
    *   A concise explanation of the rule. This is heavily used by the AI to decide when to apply the rule.
    *   Include trigger keywords if the rule should be auto-suggested for specific topics (e.g., "Dependency management with UV: Attaches when dealing with dependencies").

-   **`globs` (Optional):**
    *   A comma-separated string of file patterns (e.g., `**/*.py,**/*.mdc`) that trigger the rule when a matching file is active. Be as specific as possible.
    *   If a rule is not file-specific, leave `globs` empty. The AI may still apply it based on the `description`.

-   **`alwaysApply` (Optional):**
    *   Set to `true` to make a rule global. Use this sparingly for truly universal guidelines (e.g., a master rule about how to write other rules).
    *   If `globs` is empty and `alwaysApply` is `false`, the rule will only be attached when the AI determines the `description` is relevant to the user's query.

### 👤 User Rules vs. Project Rules: Global vs. Local

As of a recent update, Cursor introduced **User Rules**, which are distinct from the project-specific rules described above. Think of them as your personal, global instructions for the AI that apply across *all* your projects. They ensure the AI always respects your personal workflow and tool preferences.

| Feature         | **Project Rules (`.cursor/rules`)**                                | **User Rules (In Settings)**                                            |
|-----------------|--------------------------------------------------------------------|-------------------------------------------------------------------------|
| **Scope**       | ✅ Scoped to a single project/repository.                          | 🌍 Global, applies across all your projects.                            |
| **Location**    | `.mdc` files inside the `.cursor/rules` folder.                    | Configured directly in the Cursor application's settings UI.            |
| **Collaboration** | 🤝 Shared with your team via version control (Git).              | 👤 Private to you. Not shared with the project.                         |
| **Use Case**    | Enforcing team styles, project dependencies, and architecture.     | Defining your personal CLI commands, tool preferences, or universal coding habits. |

**When should you use User Rules?**

Use User Rules for instructions that apply to *you* and *your* workflow, no matter the project. Because they are configured in the settings, they are perfect for defining personal preferences that aren't necessarily part of a specific project's official conventions.

For example:
-   "Always use `uv` for Python package management."
-   "When running tests, use the command `pytest -q --tb=short`."
-   "I prefer to use pydantic v2 for data models."

You can configure them by navigating to `File` > `Settings` > `Rules` in the Cursor application.

> **Note:** For a complete guide on writing project rules, including detailed frontmatter instructions, see my foundational rules in the [`.cursor/rules`](../../../.cursor/rules) directory of this repository.

---

[⬅️ Back to Rules Overview](./README.md) | [Up: Understanding Rules](../README.md) | [Next: Interactive Development ➡️](./02b-Interactive-Rule-Development.md) 