# 🤝 Interactive Rule Development

> **🔑 Key Takeaways:**
> 
> - **Learn, Correct, Codify:** Observe the AI, correct its behavior in chat, and then immediately turn that correction into a permanent rule.
> - **Use AI to Build Rules:** Ask Cursor to help you write `.mdc` rule files based on your recent interactions.
> - **Reference Master Rules:** When generating a new rule, `@` mention your foundational rules (like `01-mdc-guidelines.mdc`) to ensure the new rule is formatted correctly.
> - **Use the `/Generate` Command:** The `/Generate Cursor Rules` command can be a helpful shortcut to kickstart the rule creation process.

---

One of the most effective ways to build a robust ruleset is to do it *interactively*. Instead of trying to write a perfect set of rules upfront, you can create and refine them in real-time as you work.

## 🔁 The "Learn, Correct, Codify" Workflow

This simple, iterative process turns every interaction into an opportunity to make Cursor a smarter assistant for your project.

1.  **Observe:** Pay attention to how Cursor responds to your prompts.
2.  **Identify Gaps:** Notice when the AI generates code that isn't quite right or misses a project-specific convention.
3.  **Correct in Chat:** Guide the AI with corrective feedback until it produces the desired output.
4.  **Codify into a Rule:** Immediately ask Cursor to help you create a new `.mdc` rule that captures the instruction permanently.

## 💡 A Practical Example

Imagine Cursor uses a deprecated function. After correcting it in the chat, you could prompt:

> "Okay, that's correct. Please help me create a new rule named `python-avoid-deprecated-funcs.mdc`. It should state that the function `old_function()` is deprecated and `new_function()` should always be used instead. Make sure its frontmatter is correct by referencing `@.cursor/rules/01-mdc-guidelines.mdc`."

Cursor will then draft the rule file for you to review and save.

## 🛠️ Built-in Tools for Rule Generation

### The `/Generate Cursor Rules` Command

Cursor provides a built-in command to accelerate this process.

-   Type `/Generate Cursor Rules` in the chat.
-   Cursor will analyze your recent interactions or ask questions to draft a relevant rule.

![Generate Cursor Rules Command](../../assets/generate_cursor_rules_command.png)

This is a great starting point, which you can then refine.

### The Importance of Master Rules

To ensure your rules themselves are consistent, always reference your "master rules" (like `00-cursor-rules.mdc` and `01-mdc-guidelines.mdc`) when asking the AI to generate new ones. This teaches the AI how to create well-formatted and maintainable rules.

---

### Sources

- Cursor Rules: https://docs.cursor.com/context/rules

[⬅️ Back to What/Why/How](./02a-What-Why-How.md) | [Up: Understanding Rules](./README.md) | [Next: Rules for Documentation ➡️](./02c-Rules-for-Stellar-Documentation.md) 