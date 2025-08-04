# ⚡ The SpecsForge Framework

> **🔑 Key Takeaways:**
> 
> - **A Framework for AI-Driven Development:** SpecsForge is a systematic workflow, powered by a custom Cursor Mode, for turning a high-level idea into a detailed, AI-readable project specification.
> - **From Vision to Plan:** It guides you through a discovery process to define business goals, features, and architecture *before* writing implementation code.
> - **Creates a "Specification Library":** The output is a `specs/` directory and a root `SPECS.md` file, which serve as the single source of truth for the project.
> - **Multiple Implementation Paths:** Choose from **TDV Mode** (rigorous testing), **Stock Agent + "Make a todo list"** (rapid scaffolding), or **[Claude Code](https://www.anthropic.com/claude-code)** (cross-platform alternative) based on your needs.
> - **Cross-Platform Compatibility:** Your SpecsForge specifications work seamlessly across different AI coding environments - try `/init` in [Claude Code](https://www.anthropic.com/claude-code) then `read SPECS.md and implement phase X`.
> - **The "Make a Todo List" Technique:** A game-changing phrase that transforms scattered AI output into organized, actionable steps - perfect for rapid prototyping and project setup tasks.

> **📋 Table of Contents**
> 
> 1. [What is SpecsForge?](#what-is-specsforge)
> 2. [Quick Implementation Guide](#quick-implementation-guide)
> 3. [Complete Workflow](#complete-workflow)
> 4. [Setting Up the Custom Mode](#setting-up-the-custom-mode)
> 5. [Legacy & Alternative Approaches](#legacy--alternative-approaches)

---

## What is SpecsForge?

The `SpecsForge` framework is a systematic workflow for transforming high-level product ideas into a precise, living specification library that powers efficient, AI-assisted development. It's built around a custom Cursor Mode that acts as an expert software architect, guiding you through a discovery process to build comprehensive specifications before any code is written.

### 🔑 Key Benefits

- **📐 Structured Planning:** Transforms scattered ideas into organized, AI-readable specifications
- **🎯 Multiple Implementation Paths:** Choose the right approach for each task type
- **🔗 Cross-Platform Compatible:** Works seamlessly across different AI coding environments
- **📚 Living Documentation:** Creates a `specs/` directory and root `SPECS.md` as single source of truth
- **⚡ Smart Handoffs:** Seamlessly transitions from planning to implementation with specialized modes

### 🎭 The Magic Phrase: "Make a Todo List"

A game-changing technique that transforms scattered AI output into organized, actionable steps. Perfect for rapid prototyping and project setup tasks.

---

## Quick Implementation Guide

### 🚀 Implementation Path Decision Matrix

| Task Type | Recommended Approach | Key Indicator | Magic Phrase |
|-----------|---------------------|---------------|--------------|
| 🏗️ **Setup & Scaffolding** | Stock Agent Mode | "Just needs to work quickly" | "Make a todo list" |
| 🧪 **Core Features** | TDV Mode | "Needs extensive testing" | "Using @SPECS.md, implement..." |
| ⚡ **Utilities & Scripts** | Stock Agent Mode | "One-off or simple logic" | "Make a todo list" |
| 🎯 **Business Logic** | TDV Mode | "Complex rules and edge cases" | "Using @SPECS.md, implement..." |
| 🚀 **Cross-Platform Dev** | [Claude Code](https://www.anthropic.com/claude-code) | "Want different AI perspective" | "/init → read SPECS.md → implement phase X" |

### 🎯 When to Use Each Approach

#### ✅ TDV Mode (Test-Driven Development)
**Best for:**
- Complex business logic requiring thorough testing
- Core application features with multiple edge cases  
- APIs and data processing workflows
- Long-term, maintainable code

#### ✅ Stock Agent Mode
**Best for:**
- Initial project scaffolding and setup
- Simple utility scripts and one-off tools
- Configuration files and basic structure
- Quick prototypes and proof-of-concepts

**💡 Pro Tip:** Always end Stock Agent prompts with **"Make a todo list"** to get organized, actionable steps.

#### ✅ [Claude Code](https://www.anthropic.com/claude-code) (Cross-Platform)
**Best for:**
- Getting different AI perspective on implementation
- Cross-platform development workflows
- Leveraging Claude's specific strengths
- Teams using multiple AI coding environments

---

## Complete Workflow

### 📋 Phase 1: Specification Generation (SpecsForge Mode)

1. **🛠️ Project Setup:** Copy your standard set of `.cursor/rules/` into the new project
2. **🎯 Activate Mode:** Activate the `SpecsForge` custom mode in Cursor  
3. **💬 Define Specs:** Engage with the SpecsForge persona through targeted questions to build:
   - A comprehensive `specs/` directory
   - A root `SPECS.md` file as the project's single source of truth
4. **📊 Generate Implementation Plan:** Create a detailed, phased implementation plan within `SPECS.md`

### ⚙️ Phase 2: Implementation Execution

Choose your implementation approach based on the task type:

#### 🧪 Option A: TDV Mode (For Complex Features)

1. **Switch to TDV Mode:** Activate the `TDV` custom mode in Cursor
2. **Implement Phase by Phase:** Work through the implementation plan using **[TDV (Test-Driven Vibing) Mode](./03a-Mode-Spotlight-TDV.md)**

```
Using @SPECS.md, let's implement Phase 1: User Authentication.
```

**TDV Mode Benefits:**
- Creates detailed `plan.md` for each phase
- Follows strict Test-Driven Development cycles  
- Implements features incrementally with tests leading

#### ⚡ Option B: Stock Agent (For Setup & Scaffolding)

1. **Use Default Agent:** Keep Cursor in its default agent mode
2. **Describe + Magic Phrase:** Explain your task, then add the magic phrase:

```
[Describe your task clearly]

Make a todo list
```

**Stock Agent Benefits:**
- Generates organized, step-by-step implementation
- Creates scaffolding and boilerplate efficiently
- Provides clear next steps for development

#### 🚀 Option C: Claude Code (Cross-Platform Alternative)

1. **Open Claude Code:** Launch Claude Code in your project directory
2. **Initialize:** Run the initialization command: `/init`
3. **Load Specifications:** Tell Claude to read your specs:

```
Read SPECS.md and implement Phase 1: User Authentication
```

**Claude Code Benefits:**
- Leverages Claude's specific AI capabilities
- Works seamlessly with SpecsForge specifications
- Enables cross-platform AI development workflows

### 🔍 Verification & Progress Tracking

After each implementation phase, verify progress against your specifications:

```
@SPECS.md check if Phase 1 was implemented properly. If so, update its status to "Complete". Otherwise, list what's missing.
```

---

## Setting Up the Custom Mode

### 🛠️ Creating the SpecsForge Mode

To create the SpecsForge custom mode in Cursor:

1. **Open Cursor Settings** → Navigate to Custom Modes
2. **Create New Mode** → Name it `SpecsForge`  
3. **Copy the System Prompt** → Paste the prompt below into the "System Prompt" field

### 📝 The SpecsForge System Prompt

```
SYSTEM
You are **SpecForge**, an expert software architect and full-stack engineer.
Your mission is to transform high-level product ideas into a precise, living *specification library* that powers automated "vibe-coding" in Cursor.

────────────────────────────────────────
1 · Discovery loop
────────────────────────────────────────
Ask targeted questions until you are confident about:

• business goals & success metrics
• feature scope & priorities
• architectural choices (DB tech, frontend stack, auth, APIs, coding standards, etc.)
• operational constraints (security, performance, compliance, budget)
• gaps, risks, and opportunities for improvement

**Always inspect any existing `.cursor/rules` directory first** and ask follow-up questions about the technical requirements it defines.

────────────────────────────────────────
2 · Spec-writing phase
────────────────────────────────────────
When you have sufficient context, begin writing Markdown spec files under `specs/`, *one file per domain or technical topic*.

────────────────────────────────────────
3 · Root index (`SPECS.md`)
────────────────────────────────────────
Maintain a root-level `SPECS.md` that contains:

1. Project overview
2. A table linking to every file in `specs/` (filename · short description)
3. Open questions / future work

Keep this file perfectly in sync whenever specs change.

────────────────────────────────────────
4 · Iteration
────────────────────────────────────────
Each time the user says **"continue"**:

1. Re-read all current specs and `.cursor/rules`.
2. Ask any new clarifying questions.
3. Extend or refine spec files and update `SPECS.md`.
4. Stop and wait for the next instruction.

────────────────────────────────────────
5 · Guiding principles
────────────────────────────────────────
• **IMPORTANT** — *Write the specifications into the `specs/` folder with each domain topic (including technical topic) as a separate Markdown file, and keep the root-level `SPECS.md` overview table up to date.*
• Never emit implementation code or run commands; you produce **specifications only**.
• Generate task lists only if the user explicitly asks; otherwise the specs themselves are authoritative.
• Be concise yet unambiguous; these specs feed directly into automated coding tools.
• Propose architectural improvements proactively.

────────────────────────────────────────
6 · Implementation Plan Generation
────────────────────────────────────────
After the specification files in `specs/` are defined and the root `SPECS.md` overview is complete, your final step is to generate a granular implementation plan within the `SPECS.md` file.
This plan should be presented as a Markdown table with the following columns:
| Phase | Focus Area | Key Deliverables | Related Specs | Status |
Each row should represent a granular step towards implementing the project based on the defined specifications.
The "Status" column should initially be set to "TBD" or a similar placeholder.

────────────────────────────────────────
7 · Recommended SPEC template
────────────────────────────────────────
```markdown
# <Domain Topic> Specification
## Purpose
## Functional Requirements
## Non-functional Requirements / Constraints
## Architecture & Data Flow
## Implementation Notes
## Deployment Strategy & Environments
## Acceptance Criteria
## Out of Scope
## Risks & Mitigations
## Future Considerations
```
```

---

## Legacy & Alternative Approaches

### 🔄 Direct Implementation (Manual Approach)

For projects not using the TDV Mode, you can implement directly:

```
Study @SPECS.md for functional specifications.  
Study @.cursor for technical requirements  

Implement Phase 1  
Create tests  
Run and evaluate tests
```

### ✅ Manual Verification

```
@SPECS.md check if Phase 1 was implemented properly. If so, update its status to "Complete". Otherwise, list what's missing.
```

---

[⬅️ Back to Evolving Ruleset](./02-Crafting-Rules-for-Your-Tech-Stack/02c-Evolving-Your-Ruleset.md) | [Up: Cursor for Developers](./README.md) | [Next: Terminal Integration ➡️](./04-Leveraging-Terminal-Integration.md)
