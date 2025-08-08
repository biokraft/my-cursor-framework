# 🎯 Why Tech-Specific Rules Matter

> **🔑 Key Takeaways:**
> 
> - **Go Beyond General Knowledge:** The AI's general knowledge is broad, but it lacks specific details about your project's libraries, framework versions, and internal patterns.
> - **Encode Your Expertise:** Rules are how you teach the AI the specific conventions of your tech stack (e.g., "Always use Pydantic models for FastAPI responses").
> - **Bridge the "Context Gap":** Tech-specific rules fill the gap between the AI's general training and your project's unique requirements, from internal logging libraries to specific architectural patterns.
> - **The Result: Better Code, Less Rework:** Well-crafted rules lead to higher-quality AI suggestions that require less manual correction.

---

While the AI has broad programming knowledge, it doesn't know the specific conventions of your project or the nuances of your tech stack. This is where tech-specific rules become essential.

## The Problem: General AI vs. Specific Needs

An AI might know Python, but does it know:
-   That your project uses **Pydantic V2**, not V1?
-   That you have a **custom logging library** that must be used instead of `print()`?
-   That all database calls must go through a **specific service layer**?
-   The "idiomatic" way to write a **React hook** according to your team's style guide?

Without specific instructions, the AI will make its best guess, which often leads to code that is functional but doesn't align with your project's standards, requiring you to rework it.

## The Solution: Rules as Focused Instructions

Tech-specific rules bridge this gap by providing explicit, targeted instructions.

### Example: Enforcing FastAPI Best Practices
A rule can tell the AI:
> "When creating FastAPI path operation functions, always use Pydantic models for request bodies and define the `response_model` explicitly."

### Example: Guiding React Component Structure
A rule can enforce:
> "All new React components must be functional components using Hooks. Place them in the `src/components/{Type}` directory, where Type is Atom, Molecule, or Organism, following Atomic Design principles."

### Example: Integrating Internal Libraries
A rule can mandate:
> "For all server-side logging, import and use the `app.utils.logger` instance. Do not use the standard Python `logging` module directly."

By creating these rules, you encode your team's expert knowledge and project-specific conventions directly into your AI assistant, leading to higher-quality suggestions and a more efficient workflow.

---

### Sources

- Cursor Rules: https://docs.cursor.com/context/rules

[⬅️ Back to Crafting Rules](./README.md) | [Up: Cursor for Developers](../README.md) | [Next: Auto-Generating Rules ➡️](./02b-Auto-Generating-Rules-from-Docs.md) 