# Interactive Rule Development: Teaching Cursor on the Fly

One of the most powerful aspects of Cursor Rules is the ability to develop them *interactively* as you work. Instead of trying to anticipate every possible guideline upfront, you can create and refine rules in real-time, directly in response to the AI's behavior or your evolving project needs.

## The Philosophy: Learn, Correct, Codify

The core idea is simple:

1.  **Observe:** Pay attention to how Cursor responds to your prompts.
2.  **Identify Gaps:** Notice when the AI generates code that isn't quite right, misses a convention, or could benefit from specific project knowledge.
3.  **Correct & Instruct:** Guide the AI in the chat to achieve the desired outcome.
4.  **Codify into a Rule:** Once you've successfully guided the AI, immediately ask Cursor to help you create a new rule (or update an existing one) to capture that instruction permanently.

This iterative process turns every interaction into an opportunity to make Cursor a smarter, more tailored assistant for your specific project.

## Your Workflow for Interactive Rule Definition

Here's a practical approach to defining rules on the fly:

1.  **Encounter a Need:** You're working on a task, and Cursor produces output that needs adjustment (e.g., uses a deprecated function, formats a comment incorrectly, doesn't follow a specific architectural pattern).
2.  **Guide Cursor in Chat:** Provide corrective feedback and the desired changes directly in the chat interface until the AI produces the correct output.
3.  **Generate the Rule with Cursor:** Once satisfied, use a prompt like this:
    ```plaintext
    Okay, that's much better. Based on our last interaction, please help me create a new Cursor Rule (or update an existing one if more appropriate) to ensure you always follow [specific guideline/convention we just established].

    The rule should be stored in `.cursor/rules/` and should follow the conventions outlined in `@.cursor/rules/00-cursor-rules.md`.

    Let's name it something like `[project_area]-[brief_description].md` (e.g., `python-docstring-format.md` or `api-error-handling.md`).
    ```
4.  **Refine and Save:** Cursor will draft the rule. Review it, make any necessary adjustments, and save it to your `.cursor/rules/` directory.

## Leveraging the `/Generate Cursor Rules` Command

Cursor also provides a built-in command to assist with rule generation:

-   Type `/Generate Cursor Rules` in the chat.
-   Cursor will often look at your recent interactions or ask clarifying questions to help draft a relevant rule.

This can be a great starting point, which you can then refine using the interactive method described above.

## The Role of a "Master Rule" for Rule Creation

To ensure consistency *within your rules themselves*, it's beneficial to have a "master rule" that defines how other rules should be structured, named, and maintained. This is often the purpose of the `00-cursor-rules.md` file mentioned previously.

By referencing this master rule when asking Cursor to generate new rules (as shown in the example prompt), you guide the AI to create well-formatted and organized rules, making your entire ruleset easier to manage.

For example, your `00-cursor-rules.md` might specify:
-   Naming conventions for rule files (e.g., `domain-topic-version.md`).
-   Required sections within a rule file (e.g., Purpose, Scope, Examples, Version).
-   Guidelines on how to phrase instructions for clarity.

By actively teaching Cursor and codifying that knowledge into rules, you compound its effectiveness over time, creating a truly personalized AI partner. 