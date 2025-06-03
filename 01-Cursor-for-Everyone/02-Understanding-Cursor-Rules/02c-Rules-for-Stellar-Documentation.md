# Using Rules for Stellar Documentation

Cursor Rules aren't just for code; they are incredibly effective for maintaining high-quality, consistent documentation. This is particularly valuable for Product Managers, technical writers, and development teams who want to ensure their project documentation is always clear, up-to-date, and follows established standards.

All documentation rules should be `.mdc` files and include appropriate frontmatter.

## Why Use Rules for Documentation?

-   **Consistency in Style & Tone:** Enforce a uniform writing style, tone of voice, terminology, and formatting across all documentation.
-   **Standardized Structure:** Ensure all documents (e.g., API docs, user guides, READMEs) follow a predefined structure or template.
-   **Version Control & Accuracy:** Help manage documentation versions and remind the AI (and users) to update related documentation when code changes.
-   **Completeness:** Prompt for essential sections like use cases, troubleshooting tips, or examples.
-   **Accessibility:** Include guidelines for writing accessible documentation (e.g., alt text for images, clear language).

## Examples of Documentation Rules

Here are some ideas for rules you can implement to improve your documentation process. Remember to save these with `.mdc` extensions (e.g., `docs-style-guide.mdc`).

### 1. Rule: `docs-style-guide.mdc`

```markdown
---
description: Documentation style guide: Enforces consistent style, tone, formatting, and terminology in project documentation.
globs: **/*.md, **/*.mdx # Apply to common documentation file types
alwaysApply: false
---
# Documentation Style Guide

## General Tone
- Maintain a professional yet approachable tone.
- Avoid jargon where possible; if used, define it clearly.
- Use active voice primarily.

## Formatting
- Headings should use Title Case (H1 for main title, H2 for major sections, H3 for subsections).
- Use bullet points for lists and numbered lists for sequential steps.
- Code examples should be in fenced code blocks with language identifiers.
- Key terms or UI elements should be **bolded** on first mention.

## Terminology
- Always refer to "User" (capitalized) when discussing end-users.
- The product name is "Project Phoenix," not "Phoenix Project" or "PP."
```

### 2. Rule: `docs-readme-template.mdc`

```markdown
---
description: README.md structure template: Ensures all project README files include standard sections.
globs: **/README.md, **/README.mdx
alwaysApply: false
---
# README.md Structure

All project README.md files must include the following sections in this order:

1.  **Project Title (H1)**
2.  **Overview (Brief summary of the project)**
3.  **Features**
4.  **Getting Started**
    *   Prerequisites
    *   Installation
    *   Running the project
5.  **Usage**
6.  **Contributing**
7.  **License**

Ensure all sections are populated appropriately. If a section is not applicable, state "N/A" with a brief explanation.
```

### 3. Rule: `docs-versioning-reminder.mdc`

```markdown
---
description: Documentation versioning reminder: Prompts to update docs when code changes and outlines versioning scheme.
globs: 
alwaysApply: false # Or true, if it should always be a reminder
---
# Documentation Versioning and Updates

## Reminder: Keep Docs in Sync

When making changes to code, especially API endpoints, core features, or user-facing functionality, always remember to update the corresponding documentation.

- Check `docs/api/`, `docs/user-guide/`, and relevant READMEs.
- If you are unsure which documents to update, please ask.

## Versioning Scheme

- Documentation versions should align with software release versions.
- Clearly indicate the version of the software the documentation pertains to at the beginning of each major document.
```

## How to Use These Rules

-   **Generating New Docs:** When asking Cursor to draft new documentation (e.g., "Draft a README for the new reporting module, following our `docs-readme-template.mdc`"), it will automatically try to follow these rules if they are correctly configured and picked up by Cursor (via globs, `alwaysApply`, or description matching).
-   **Updating Existing Docs:** If you're asking Cursor to update a section, it will adhere to the established style and structure if the relevant rules are active.
-   **Reviewing Docs:** You can even ask Cursor to review existing documentation against these rules: "@docs/my_document.md Does this document adhere to the guidelines in `@.cursor/rules/docs-style-guide.mdc` and `@.cursor/rules/docs-readme-template.mdc`? Suggest improvements."

By implementing documentation-specific `.mdc` rules with proper frontmatter, you empower Cursor to be a more effective assistant in creating and maintaining a clear, consistent, and valuable knowledge base for your project.

---

[⬅️ Back to Main README](../../../README.md) 