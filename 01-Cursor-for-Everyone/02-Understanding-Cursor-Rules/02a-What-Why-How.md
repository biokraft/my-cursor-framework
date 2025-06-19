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

The frontmatter block is critical for configuring how a rule is applied.

```yaml
---
description: A brief, agent-friendly explanation of the rule's purpose.
globs: '**/.*.py,src/**/*.js' # Optional: Comma-separated file patterns.
alwaysApply: false # Optional: Set to true for global rules.
---
```

**Key Properties:**

-   **`description` (Required):** A concise explanation of the rule. This is heavily used by the AI to decide when to apply the rule.
-   **`globs` (Optional):** A comma-separated string of file patterns (e.g., `**/*.py,**/*.mdc`) that trigger the rule when a matching file is active.
-   **`alwaysApply` (Optional):** Set to `true` to make a rule global. Use this sparingly for truly universal guidelines.

> **Note:** For a complete guide on writing rules, including detailed frontmatter instructions, see my foundational rules in the [`.cursor/rules`](../../../.cursor/rules) directory of this repository.

---

[⬅️ Back to Rules Overview](./README.md) | [Up: Cursor for Everyone](../../README.md) | [Next: Interactive Development ➡️](./02b-Interactive-Rule-Development.md) 