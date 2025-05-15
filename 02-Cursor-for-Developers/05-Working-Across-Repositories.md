# Working Across Repositories with Cursor (e.g., Git Submodules)

**Alternative Approach:** Cursor now supports multi-root workspaces, allowing you to open multiple folders (repositories) in the same window. This provides a more integrated way to work across codebases compared to or alongside Git submodules. You can find more details in the [Cursor 0.50 changelog](https://www.cursor.com/changelog/0-50).

Modern software projects often span multiple repositories. This could be due to microservice architectures, shared libraries, or modular project structures. When working in such an environment, providing Cursor with the right context from all relevant repositories is key to its effectiveness. One common way to manage multi-repository projects locally is through **Git Submodules**.

## The Challenge of Multi-Repo Context

By default, Cursor's context (like `@` file mentions or codebase search) is usually scoped to the primary repository you have open. If your current task involves code or dependencies from another repository (e.g., a shared library), Cursor might not automatically "see" it.

## Git Submodules as a Solution

Git submodules allow you to embed other Git repositories as subdirectories within a parent repository. When you clone the parent repository with its submodules, you get a local working copy of all the necessary code.

**How this helps Cursor:**

-   **Local Context:** If you have a submodule checked out (e.g., `my_project/shared_libs/common_utils_lib`), that code is now locally present. Cursor can then be directed to files within that submodule using relative paths from your main project root.
-   **`@` Mentions Work:** You can use `@` mentions like `@shared_libs/common_utils_lib/src/helper.py` and Cursor should be able to find and use that file as context.
-   **Codebase Search (Potentially):** Depending on how Cursor's codebase search is configured, it might be able to index and search across the submodule directories as well, though this can vary.

## Strategies for Using Cursor with Git Submodules

1.  **Ensure Submodules are Initialized and Updated:**
    *   Before starting a Cursor session where submodule context is needed, make sure your submodules are properly cloned and up to date:
        ```bash
        git submodule update --init --recursive
        ```
    *   Regularly pull changes in your submodules if they are actively developed.

2.  **Explicitly Reference Submodule Paths:**
    *   When prompting Cursor, be explicit about paths if you need it to look at or modify code within a submodule.
    *   *Example:* "Please review the function `process_data` in `@shared_libs/data_processor/main.py` and suggest improvements based on the requirements in `@SPECS.md`."

3.  **Consider Cursor Rules for Submodule Interactions:**
    *   If there are specific ways your main project should interact with a submodule (e.g., only calling certain public APIs of the library), you can define these in a Cursor Rule.
    *   *Example Rule:* "When using the `common_utils_lib` submodule, only import and use functions from the `common_utils_lib.api` module. Do not directly access internal implementation details."

4.  **`@Docs` for Submodule APIs:**
    *   If the submodule is a library with its own documentation, use the `@Docs` feature to point Cursor to that documentation, even if it's local within the submodule's directory (e.g., `@Docs add shared_libs/common_utils_lib/docs`).

5.  **Opening the Submodule as a Separate Project (If Needed):**
    *   For very intensive work focused solely within a submodule, you *could* open that submodule's directory as a separate project in Cursor. This would give Cursor focused context on just that library. However, you'd then lose direct context from the parent project.
    *   Generally, working from the parent project and referencing submodule paths is preferable for tasks involving interaction between the parent and submodule.

## Broader Multi-Repo Considerations (Beyond Submodules)

Even if you're not using Git submodules, the principle of providing context remains:

-   **Local Copies:** If you have multiple related repositories cloned locally in a known directory structure (e.g., all under `~/projects/my_company/`), you can still try to use relative or absolute paths in `@` mentions if Cursor's file access allows.
-   **`@Docs` for External APIs:** If a related repository is not local but exposes an API, use `@Docs` to point to its API documentation.
-   **MCP for Remote Info:** If the other repository is on a platform like GitHub/GitLab and has issues or PRs relevant to your work, an MCP connector for that platform could bring in context.

## Key Takeaway

When your project spans multiple repositories, your primary goal is to make the relevant code and documentation from those other repositories accessible and known to Cursor. Git submodules are a convenient way to achieve this for locally dependent code. Always be explicit in your prompts and use `@` mentions with clear paths to guide Cursor effectively in a multi-repo setup. 