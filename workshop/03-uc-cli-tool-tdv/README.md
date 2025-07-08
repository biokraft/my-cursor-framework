
# UseCase 3: Building a CLI Tool with TDV Mode

### 🎯 The Goal
To showcase the **TDV (Test-Driven Vibing) Mode** by building a simple, yet practical, command-line tool from scratch. This highlights how to go from a high-level requirement to fully tested code.

### 💼 The Real-World Scenario
**The Problem:** A Data Scientist frequently receives data reports as PDF files and needs a quick way to extract the text content for analysis. They are tired of manually copying and pasting from PDF viewers.

**The Pain Point:** Building a quick, one-off tool can feel like a chore. Writing tests is often skipped for "simple" scripts, which later break unexpectedly. The developer has to figure out which libraries to use, how to structure the code, and how to handle command-line arguments.

### 🚀 The Cursor Framework Solution
Using the **TDV Mode**, we can enforce a test-first workflow. The AI will guide the process, from planning and writing failing tests to implementing the code to make them pass. This ensures we build a reliable and well-structured tool.

### 🤖 Live Demo Script
1.  **Activate TDV Mode:** In the chat, select the `TDV` custom mode.
2.  **Initial Prompt:**
    > "I need to build a Python CLI tool that extracts text from a PDF file and saves it to a `.txt` file. Let's call the tool `pdf-to-text`. It should take an input PDF path as an argument and optionally an output path. Use the `PyMuPDF` library. Let's start by creating a plan for this."
3.  **Review the Plan:** The AI, following the `TDV` persona, will create a `plan.md` outlining the TDD steps:
    *   Set up project structure (`pyproject.toml`, `src/`, `tests/`).
    *   Write a failing test for the core extraction logic.
    *   Implement the extraction logic.
    *   Write a failing test for the CLI argument parsing.
    *   Implement the CLI logic using `argparse` or `click`.
4.  **Execute the TDD Cycle:**
    > "The plan looks great. Let's proceed with the first step: setting up the project structure and writing the first failing test for the extraction logic."
5.  **Follow the AI:** The AI will create the files, write a test that asserts text can be extracted, and run it to show it failing. Then, it will prompt to write the implementation code.
    > "Okay, the test failed as expected. Now write the implementation for the `extract_text_from_pdf` function to make the test pass."
6.  **Show the Outcome:** Continue this cycle for the CLI logic. At the end, you will have:
    *   A fully functional Python CLI tool.
    *   A suite of tests that verify its functionality.
    *   A well-structured project that is easy to maintain and extend.
    *   Demonstrate running the final tool from the command line.

---
[⬅️ Back to Workshop Overview](../README.md) 