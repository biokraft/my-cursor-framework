# 🌐 Working Across Repositories

> **🔑 Key Takeaways:**
> 
> - **Use Multi-Root Workspaces:** The best way to work across multiple repositories in Cursor is to use the "File > Add Folder to Workspace..." feature. This gives the AI full context for all open projects.
> - **Git Submodules as an Alternative:** If you use Git submodules, ensure they are initialized locally (`git submodule update --init`). You can then `@` mention files within them using their relative path from the parent project.
> - **Be Explicit with Context:** Whether using multi-root workspaces or submodules, always be explicit. Use full relative paths in your `@` mentions to avoid ambiguity (e.g., `@my-shared-library/src/utils.ts`).
> - **Use Rules for Cross-Repo Interactions:** Define rules to govern how your primary project should interact with a shared library, such as only using its public API.

---

Modern projects often span multiple repositories (e.g., microservices, shared libraries). Here's how to give Cursor context across all of them.

## The Recommended Approach: Multi-Root Workspaces

The most effective and recommended method is to use **multi-root workspaces**.

1.  Open your primary repository in Cursor.
2.  Go to **File > Add Folder to Workspace...**
3.  Select the other repository (e.g., a shared library) you need to work with.

Now, both projects are open in the same window, and Cursor has full access to the files and context of both. You can `@` mention files from either repository, and the AI will understand the complete picture. This is the simplest and most powerful way to handle multi-repo projects.

## Alternative Approach: Git Submodules

If your project is structured using Git submodules, you can also make this work effectively.

### How Submodules Provide Context
When you initialize a submodule, its code is physically present in a subdirectory of your main project. This means:
-   **`@` Mentions Work:** You can reference files inside the submodule using their path from the parent project's root (e.g., `@my-submodule/src/index.js`).
-   **Local Context is Complete:** The AI can read and understand the submodule's code because it's available on your local disk.

### Workflow for Submodules
1.  **Ensure Submodules are Initialized:** Before you begin, run `git submodule update --init --recursive` in your parent repository to make sure all the submodule code is present.
2.  **Be Explicit with Paths:** When prompting, use clear, relative paths to files within the submodule to avoid any ambiguity.
    > "Review the function `doSomething` in `@my-submodule/src/utils.ts` and refactor it based on the requirements in the parent project's `@SPECS.md`."
3.  **Define Rules for Interaction:** Create a Cursor Rule to define the "contract" between your parent project and the submodule.
    > "When using the `my-submodule` library, only import from the `my-submodule/index.ts` entry point. Do not access files in its `internal` directory."

By providing clear, comprehensive context—preferably through multi-root workspaces—you can make Cursor a powerful assistant even in complex, multi-repository projects.

---

### Sources

- Concepts (workspaces, context, indexing): https://docs.cursor.com/get-started/concepts

[⬅️ Back to Terminal Integration](./04-Leveraging-Terminal-Integration.md) | [Up: Cursor for Developers](./README.md) 