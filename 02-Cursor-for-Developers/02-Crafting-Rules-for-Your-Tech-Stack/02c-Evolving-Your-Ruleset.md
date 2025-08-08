# 📈 Evolving Your Ruleset

> **🔑 Key Takeaways:**
> 
> - **Rules are Living Documents:** Your ruleset is not "set it and forget it." It must evolve as your libraries, frameworks, and project standards change.
> - **The Core Loop: Correct, then Codify:** The best way to evolve rules is through daily work. When you correct the AI, immediately ask it to help you update the relevant rule with that new information.
> - **Use Updates as a Trigger:** When a key library gets a major update, use that as a trigger to review your rules for it. Point `@Docs` to the new release notes and ask the AI to help you identify necessary changes.
> - **Keep Rules Focused:** If a rule becomes too large, break it down into smaller, more specific rules. This improves the AI's ability to apply them correctly.

---

Your ruleset should be a living document, continuously refined to stay effective. Here are practical strategies for keeping it up-to-date.

## A Checklist for Rule Maintenance

-   **✅ Interactive Refinement is #1:** This is the most important habit. When you correct the AI's behavior in chat, don't stop there. Immediately follow up with a prompt like:
    > "That's the right approach. Please help me update the `@.cursor/rules/my-api-rule.mdc` to include this new pattern."

-   **✅ Use Library Updates as a Trigger:** When your project's main framework (e.g., Django, Next.js) has a major release:
    1.  Add the new documentation URL to Cursor via the `Docs` setting.
    2.  Prompt the AI:
        > "@Docs Next.js-14-Docs. Please review my existing rule `@.cursor/rules/nextjs-conventions.mdc` and suggest updates to align it with the best practices for version 14, especially regarding the App Router."

-   **✅ Schedule Periodic Reviews:** During a regular team ceremony (like a sprint retrospective or a tech guild meeting), dedicate 15 minutes to discussing the AI's performance. Are there common corrections the team is making? This is a great source of ideas for new or updated rules.

-   **✅ Keep Rules Focused and Atomic:** If a rule file becomes too long or covers too many topics, the AI may struggle to apply it effectively. Don't be afraid to break a large `python-best-practices.mdc` into smaller, more focused files like `python-error-handling.mdc`, `python-class-design.mdc`, and `python-async-patterns.mdc`.

By treating your rules as a core part of your project's knowledge base, you ensure that Cursor's effectiveness grows alongside your project.

---

### Sources

- Concepts (@Docs, context): https://docs.cursor.com/get-started/concepts

[⬅️ Back to Auto-Generating Rules](./02b-Auto-Generating-Rules-from-Docs.md) | [Up: Cursor for Developers](../README.md) | [Next: SpecsForge Framework ➡️](../03-The-SpecsForge-Framework.md) 