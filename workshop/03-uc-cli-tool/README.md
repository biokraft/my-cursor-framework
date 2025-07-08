
# UseCase 3: Rapidly Scaffolding a CLI Tool

### 🎯 The Goal
To demonstrate how to use Cursor's stock agent to rapidly prototype and build a functional command-line tool, going from a simple prompt to a working script in minutes.

### 💼 The Real-World Scenario
**The Problem:** A Data Scientist frequently receives data reports as PDF files and needs a quick way to extract the text content for analysis. They are tired of manually copying and pasting.

**The Pain Point:** Even for a "simple" script, they have to deal with finding the right library, writing boilerplate for argument parsing, and handling file I/O. It's a distraction from their main task.

### 🚀 The Cursor Framework Solution
Using Cursor's default agent, we can describe the desired tool in plain English and have it generate the complete, working code. This is perfect for quick, one-off utilities where a full TDD process is overkill.

### 🤖 Live Demo Script
1.  **Activate Stock Mode:** Ensure you are using the default agent mode.
2.  **Create the file:** Start by creating a new file: `workshop/03-uc-cli-tool/pdf_to_text.py`.
3.  **Initial Prompt:**
    > "Create a Python script named `pdf_to_text.py`. It should be a command-line tool that uses the `PyMuPDF` library to extract all text from a PDF file.
    > - It must accept one required argument: the path to the input PDF file.
    > - It should have an optional argument `--output` to specify the output text file path.
    > - If the output path is not provided, it should print the extracted text directly to the console.
    > - Add comments explaining the code."
4.  **Review and Test:** The AI will generate the complete script. Briefly review the code with the audience, pointing out the argument parsing and the core logic.
5.  **Show the Outcome:** Run the script from the terminal to prove it works.
    > `python workshop/03-uc-cli-tool/pdf_to_text.py my_report.pdf --output report.txt`
6.  **Highlight the Speed:** Emphasize that in less than a minute, you've created a functional, useful tool without any manual boilerplate coding. This is for getting quick wins and automating small, repetitive tasks.

---
[⬅️ Back to Workshop Overview](../README.md) 