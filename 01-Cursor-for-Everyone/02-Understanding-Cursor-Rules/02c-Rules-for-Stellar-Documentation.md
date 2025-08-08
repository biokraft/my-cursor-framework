# ✍️ Rules for Stellar Documentation

> **🔑 Key Takeaways:**
> 
> - **Consistency is Key:** Use rules to enforce a consistent style, tone, terminology, and structure across all your project documentation.
> - **Create Templates:** Define rules that act as templates for common documents like `README.md` files or API guides.
> - **Automate Reminders:** A rule can remind the AI (and you) to update documentation whenever related code changes are made.
> - **Use Rules for Review:** Ask Cursor to review an existing document against a specific rule to check for compliance.

---

Cursor Rules are not just for code; they are incredibly effective for maintaining high-quality, consistent documentation. This is valuable for Product Managers, writers, and developers who want to ensure project documentation is always clear and follows established standards.

## ✨ Why Use Rules for Documentation?

-   **Consistent Style & Tone:** Enforce a uniform writing style and terminology.
-   **Standardized Structure:** Ensure all documents follow a predefined template.
-   **Accuracy & Versioning:** Help manage documentation versions and remind everyone to update docs when code changes.
-   **Completeness:** Prompt for essential sections like use cases or troubleshooting tips.

## 💡 Example Documentation Rules

Here are some ideas for rules you can implement. Remember to save these with a `.mdc` extension.

### Example 1: Style Guide Rule

A rule named `docs-style-guide.mdc` can enforce a consistent voice, tone, and formatting.

```markdown
---
description: Documentation style guide for Project Phoenix.
globs: '**/*.md,**/*.mdx'
---
# Documentation Style Guide

## General Tone
- Maintain a professional yet approachable tone.
- Use active voice primarily.

## Terminology
- Always refer to "User" (capitalized).
- The product name is "Project Phoenix."
```

### Example 2: README Template Rule

A rule named `docs-readme-template.mdc` can ensure all READMEs have the same structure.

```markdown
---
description: README.md structure template.
globs: '**/README.md'
---
# README.md Structure

All project READMEs must include:
1.  **Project Title**
2.  **Overview**
3.  **Features**
4.  **Getting Started** (Prerequisites, Installation)
5.  **Usage**
```

### Example 3: Doc Update Reminder Rule

A rule can remind the AI to update documentation when code changes.

```markdown
---
description: Documentation update reminder
globs: '**/*.py,**/*.js,**/*.ts' # Trigger when code files are edited
---
# Documentation Update Reminder

When making changes to code, especially API endpoints or core features, always remember to check if the corresponding documentation needs to be updated.

- Check `docs/api/` and relevant READMEs.
- If you are unsure which documents to update, please ask.
```

## 🛠️ How to Use These Rules

-   **Generating New Docs:** When asking Cursor to draft a new document, it will automatically follow any relevant rules.
-   **Updating Existing Docs:** As you edit, Cursor will adhere to the established style and structure.
-   **Reviewing Docs:** Ask Cursor to check for compliance directly:
    > "@docs/my_api.md Does this document adhere to the guidelines in `@.cursor/rules/docs-style-guide.mdc`? Suggest improvements."

By implementing documentation-specific rules, you empower Cursor to be a more effective co-author for your project's knowledge base.

---

### Sources

- Cursor Concepts (context, globs, indexing): https://docs.cursor.com/get-started/concepts

[⬅️ Back to Interactive Development](./02b-Interactive-Rule-Development.md) | [Up: Understanding Rules](./README.md) | [Next: Choosing Your AI Model ➡️](../03-Choosing-Your-AI-Model.md) 