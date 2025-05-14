# From Specs to Code: AI-Assisted Implementation Strategies

Once the `SpecsForge` framework has helped you produce a comprehensive `SPECS.md` file, complete with a detailed implementation plan, the next stage is to bring that vision to life. This is where Cursor's coding assistance shines, guided by the precise specifications and technical rules you've established.

## The Foundation: `SPECS.md` and `.cursor/rules`

Before you ask Cursor to write any implementation code, ensure your context is primed:

1.  **`@SPECS.md` is Central:** This file is your primary brief for the AI. It contains not just *what* to build (functional and non-functional requirements for each domain) but also *how* to build it in a phased manner (the implementation plan table).
2.  **`@.cursor/rules` Provides Guardrails:** Your collection of Cursor Rules (general, tech-stack specific, documentation standards) provides the technical constraints, coding standards, and best practices the AI must adhere to.

## The Core Implementation Prompt Structure

A typical prompt structure for tackling a phase from your `SPECS.md` implementation plan looks like this:

```plaintext
Study @SPECS.md carefully, paying close attention to the overall project goals, the detailed specifications for [Specific Domain/Feature related to this Phase], and the currently targeted Phase [X] of the Implementation Plan.

Study all rules in @.cursor/rules/ to understand the technical requirements, coding standards, API design guidelines, and any other project-specific conventions.

Based on this understanding, please implement Phase [X]: [Name of Phase from SPECS.md].

The key deliverables for this phase are: [List key deliverables from SPECS.md for this phase].
The related spec files are: [List related spec files from SPECS.md, e.g., @specs/feature_A_domain.md, @specs/technical_architecture.md].

Proceed by:
1.  Outlining the files you plan to create or modify.
2.  Implementing the required functionality step-by-step.
3.  Ensuring all code adheres to the conventions in @.cursor/rules.
4.  Generating necessary tests for the implemented features.

If you have clarifying questions about the specs or rules before you begin, please ask now.
```

## Iterative Development within a Phase

Even within a single phase, development is often iterative:

-   **Initial Code Generation:** Cursor provides the first pass at the code for a specific part of the phase.
-   **Review and Refine:** As a "Vibe Programmer," you critically review the generated code.
    *   Does it meet the specs?
    *   Does it follow the rules?
    *   Is it clean, efficient, and maintainable?
-   **Corrective Prompts:** If necessary, provide feedback to Cursor:
    *   "This part of the code for `module_X` doesn't correctly handle the edge case defined in `@specs/feature_A_domain.md` under 'Error Conditions'. Please revise it."
    *   "The naming convention used in `new_function_Y` doesn't align with `@.cursor/rules/python-naming-conventions.md`. Please refactor."
    *   "Can you add more detailed comments to `complex_algorithm_Z.py` to explain its logic?"
-   **Testing is Key:** After code generation (or a significant chunk), move to test generation and execution.

## Generating and Running Tests

Testing is a non-negotiable part of the workflow.

-   **Prompting for Tests:**
    ```plaintext
    Now, create comprehensive tests for the functionality implemented in [file(s) X, Y, Z / feature A].
    Ensure the tests cover:
    - Normal success cases.
    - Edge cases as defined in the specs.
    - Error handling.
    Refer to `@.cursor/rules/python/testing/01-best-practices.md` (or your relevant testing rule) for our testing standards (e.g., preferred framework, test structure).
    ```
-   **Running and Evaluating Tests:**
    *   Execute the tests using your project's test runner (e.g., `pytest`, `jest`).
    *   If tests fail, feed the error messages and relevant code back to Cursor:
        ```plaintext
        The test `test_my_feature_abc` failed with the following error:
        [Paste error output]

        Here is the test code from `@tests/test_my_feature.py`:
        [Paste test_my_feature_abc]

        And here is the related application code from `@app/my_feature_module.py`:
        [Paste relevant function/class from my_feature_module.py]

        Please analyze the issue and suggest a fix, keeping the original specifications in @SPECS.md in mind.
        ```

## Post-Phase Completion: Quality Checks

Once a phase is functionally complete and tests are passing, it's good practice to perform final quality checks, often involving linters and formatters configured via `pre-commit` hooks (if your project uses them).

-   **Prompt for Cleanup:**
    ```plaintext
    Phase [X] is now complete and all tests are passing.

Please run pytest again to confirm.
Then, run pre-commit run --all-files and apply any necessary fixes for linting errors or formatting issues until it succeeds. Explain the changes you make.
    ```

By systematically working through the implementation plan from `SPECS.md`, leveraging Cursor for code and test generation, and maintaining a strong review and feedback loop, you can efficiently and reliably build out your project according to the predefined vision. 