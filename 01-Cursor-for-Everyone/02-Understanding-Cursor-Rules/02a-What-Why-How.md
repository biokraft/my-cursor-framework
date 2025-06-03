# Cursor Rules: What, Why, and How?

Cursor Rules are a powerful feature that allows you to provide persistent, project-specific instructions to the AI. Think of them as a set of guidelines or a "style guide" that Cursor consults to ensure its responses and actions align with your project's conventions, standards, and technical requirements.

## What are Cursor Rules?

-   **Persistent Instructions:** Unlike one-off prompts in the chat, rules are stored in your project (typically in a `.cursor/rules/` directory) and are automatically considered by the AI.
-   **Markdown Custom (MDC) Files:** Rules must be written in `.mdc` (Markdown Custom) files. This format allows for both human-readable Markdown instructions and machine-readable configuration via frontmatter.
-   **Contextual Guidance:** They provide crucial context about your coding style, architectural patterns, preferred libraries, documentation standards, and more.

## Why Use Cursor Rules?

-   **Consistency:** Enforce consistent coding styles, naming conventions, and architectural patterns across your project, even when multiple people (or AI) contribute.
-   **Accuracy:** Help the AI generate more accurate and relevant code or suggestions by providing it with specific knowledge about your project that it wouldn't otherwise have.
-   **Efficiency:** Reduce the need to repeat common instructions or corrections in every prompt. Define it once in a rule, and Cursor remembers.
-   **Knowledge Sharing:** Codify team best practices and project-specific knowledge, making it easier for new team members (and the AI) to get up to speed.
-   **Customization:** Tailor Cursor's behavior to the unique needs of your project or organization.

## How Do They Work?

1.  **Create a `.cursor/rules/` Directory:** In the root of your project, create this directory to store your rule files.
2.  **Write Rules in `.mdc` Files:** Create `.mdc` files within this directory. Each file represents a specific rule or a collection of related guidelines.
    *   All `.mdc` files **must** begin with a YAML-like frontmatter section enclosed in triple-dash lines (`---`).
    *   Following the frontmatter, use clear Markdown with headings, bullet points, and code blocks to structure your rules.
    *   The AI is trained to understand instructions written in natural language within these files.
3.  **Automatic Context:** Cursor automatically loads and considers rules from the `.cursor/rules/` directory based on their frontmatter configuration and your interaction.
4.  **Specificity and Overrides:** You can have general rules and more specific ones. The AI will try to apply the most relevant rules based on the context of your request and the rule's configuration.

## Understanding MDC Frontmatter

The frontmatter is a critical configuration block at the very beginning of every `.mdc` file, enclosed by triple-dash lines (`---`). It provides metadata that tells Cursor how and when to use the rule.

```yaml
---
# Configure your rule based on desired behavior:

description: Brief description of what the rule does
globs: # Optional: Comma-separated list, not an array
alwaysApply: false # Set to true for global rules
---
```

**Key Frontmatter Properties:**

-   **`description` (Required):**
    *   A brief, agent-friendly explanation of the rule's purpose and when it's relevant.
    *   Format as `<topic>: <details>` for clarity (e.g., "Python style guidelines: Apply when working with Python code").
    *   Include trigger keywords if the rule should be auto-suggested for specific topics (e.g., "Dependency management with UV: Attaches when dealing with dependencies").

-   **`globs` (Optional):**
    *   A comma-separated list of file patterns (e.g., `**/*.py, src/**/*.js`) that determine when this rule is automatically attached because a matching file is active or mentioned.
    *   **Important:** This is a simple comma-separated string, *not* a YAML list. Do **not** use brackets `[]` or quotes for the glob patterns themselves within the list, unless the pattern itself requires quotes (which is rare).
    *   Example: `globs: **/*.py, **/*.mdc`
    *   If a rule is only relevant in specific situations unrelated to file types, leave `globs` empty. The agent may still attach it based on the `description` and query context.
    *   If the only glob would match all files (like `**/*`), leave `globs` empty and set `alwaysApply: true` instead.
    *   Be as specific as possible with glob patterns to ensure rules are only applied with relevant files.

-   **`alwaysApply` (Optional, defaults to `false`):**
    *   Set to `true` to make a rule globally applied, meaning Cursor will consider it for nearly all interactions, regardless of open files or specific query context.
    *   Use `alwaysApply: true` sparingly, only for truly universal guidelines (e.g., a master rule about how to write other rules, or extremely fundamental project-wide principles).
    *   If `globs` is empty and `alwaysApply` is `false` (or omitted), the rule will be attached by the agent only when it determines the rule's `description` and content are relevant to the user's query.

**No other frontmatter properties are supported.**

## Essential Base Rules

It's highly recommended to include the following two foundational rules in any project, as also mentioned in the main [README.md](../README.md#my-standard-cursor-rules):

-   **[`00-cursor-rules.mdc`](../../.cursor/rules/00-cursor-rules.mdc):** This rule defines the general structure for *other* rules. It might specify how to name rules, version them, or general principles for writing effective rules.
-   **[`01-mdc-guidelines.mdc`](../../.cursor/rules/01-mdc-guidelines.mdc):** This file provides the definitive guidelines on the `.mdc` format itself, including frontmatter and Markdown content.

(You can find examples of these in the `.cursor/rules` directory of this framework repository.)

In the next sections, we'll explore how to develop rules interactively and use them for specific purposes like documentation.

---

[⬅️ Back to Main README](../../../README.md) 