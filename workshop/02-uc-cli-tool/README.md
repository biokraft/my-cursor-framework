
# 🛠️ 2. Rapidly Scaffolding a CLI Tool

> **🔑 Key Takeaways:**
>
> - **The Magic Phrase:** Adding "Make a todo list" to any prompt transforms chaotic AI output into organized, actionable steps.
> - **Perfect for Rapid Prototyping:** Stock Agent mode excels at scaffolding, setup tasks, and simple utilities that don't require extensive testing.
> - **Workflow Decision:** Use this technique for quick wins; save TDV mode for complex business logic that needs rigorous testing.
> - **From Chaos to Clarity:** This simple trick turns scattered implementation details into structured next steps you can actually follow.

**Goal:** Generate a complete, working command-line tool from a single prompt using the "Make a todo list" technique.

---

## 🎯 The Secret Sauce: "Make a todo list"

This workshop showcases a **game-changing technique** for rapid prototyping and project scaffolding. When you need to quickly build tools, set up project structure, or create utilities that don't require extensive testing, the stock Agent mode with a simple trick is incredibly powerful.

**The Magic Phrase:** End your prompt with **"Make a todo list"**

This transforms scattered AI output into organized, actionable steps - turning chaos into clarity!

---

### Workshop Steps:

1.  **Create a Python File:** Make a new file: `pdf_to_text.py`.
2.  **Use the Default Agent:** Make sure no custom mode is selected.
3.  **The Power Prompt:** Ask the AI to create a Python CLI tool using `PyMuPDF` to extract text from a PDF:
    ```
    Create a Python CLI tool using PyMuPDF to extract text from a PDF.
    
    Requirements:
    - Required input path argument for the PDF file
    - Optional output file argument (--output)
    - If no output is given, print to console
    - Include proper error handling and help text
    
    Make a todo list
    ```
4.  **Marvel at the Organization:** The AI will generate both the complete script AND a structured todo list for next steps.
5.  **Test It:** Run the script from the terminal to confirm it works.
    -   *Example: `python pdf_to_text.py my_report.pdf`*

---

## 🧠 When to Use This Approach vs TDV

**✅ Perfect for Stock Agent + "Make a todo list":**
- Initial project scaffolding
- Simple utility scripts
- Configuration setup
- Quick prototypes
- One-off tools and scripts

**🧪 Better for TDV Mode:**
- Complex business logic
- Core application features
- APIs requiring extensive testing
- Long-term, maintainable codebases

---
[⬅️ Back to Workshop Overview](../README.md) 