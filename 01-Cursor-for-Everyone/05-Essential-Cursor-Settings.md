# ⚙️ Essential Cursor Settings

> **🔑 Key Takeaways:**
> 
> - **Enable `Include project structure`:** This is the most important setting. It gives the AI a file tree of your project, massively improving its context and accuracy.
> - **Enable `Web Search Tool`:** Allows the AI to access up-to-date information from the internet, crucial for research and current best practices.
> - **Enable `Auto-run mode` for Speed:** For advanced users, this allows the AI to execute commands and edits without confirmation, creating a faster workflow.
> - **Enable `Play sound on finish` for Feedback:** A simple but effective auditory cue that an AI task is complete.

---

To get the most out of Cursor, you should enable a few key settings. These options, especially the BETA features, will significantly enhance your productivity.

### 1. Include project structure (BETA)

**This is a game-changer. Enable it.** It gives the AI a simplified directory tree of your project, so it always understands your codebase layout.

-   **Why it's crucial:** Improves contextual awareness and accuracy, reducing the need for you to manually reference files.  
    ![Include Project Structure Setting](../assets/include_project_structure.png)

### 2. Web Search Tool (BETA)

**Enable this for a smarter AI.** It allows the agent to search the web for real-time information.

-   **Why it's essential:** Gives the AI access to current documentation, APIs, and articles beyond its training data.  
    ![Web Search Tool Setting](../assets/web_search_tool.png)

### 3. Enable auto-run mode

For users who want to work at maximum speed and are comfortable with the AI taking initiative.

-   **Why it's powerful:** The AI can execute terminal commands and apply file edits without pausing for your approval, creating a much smoother workflow. Use with confidence!  
    ![Enable Auto-run Mode Setting](../assets/auto_run_mode.png)

### 4. Play sound on finish (BETA)

A small but satisfying feature for positive reinforcement.

-   **Why it's nice:** Provides a clear auditory cue when a task is complete, so you don't have to keep checking the screen.  
    ![Play Sound on Finish Setting](../assets/play_sound_on_finish.png)

### 5. Use the Command Denylist for Stability

After every prompt, Cursor saves the full state of your workspace, including all files. This is an amazing feature—it means you can restore your project to its exact previous state if the AI makes a mistake. Just hit "Restore," and you're back to where you were.

However, this feature can cause issues with very large files.

-   **The Problem:** If you have a multi-gigabyte file in your project and the AI deletes it, Cursor can become completely unusable. It may try to store the entire file in memory for the restore process, leading to a crash.
-   **The Solution:** Add `rm` to the **Command Denylist** in your settings.

This prevents the AI from deleting files automatically. It can still *suggest* `rm` commands, but you will have to approve them explicitly. This small change adds a crucial safety net, making Cursor much more stable for projects with large assets, without disrupting your workflow.

---

By thoughtfully configuring these settings, you can create a highly efficient and context-aware working environment in Cursor.

---

[⬅️ Back to Custom Modes](./04-Custom-Modes-Tailoring-Cursor-to-You/README.md) | [Up: Cursor for Everyone](../README.md) | [Next: The MCP ➡️](./06-The-Model-Context-Protocol-MCP/README.md) 