# ⚡ The SpecsForge Framework

> **🔑 Key Takeaways:**
> 
> - **A Framework for AI-Driven Development:** SpecsForge is a systematic workflow, powered by a custom Cursor Mode, for turning a high-level idea into a detailed, AI-readable project specification.
> - **From Vision to Plan:** It guides you through a discovery process to define business goals, features, and architecture *before* writing implementation code.
> - **Creates a "Specification Library":** The output is a `specs/` directory and a root `SPECS.md` file, which serve as the single source of truth for the project.
> - **Powers Subsequent Coding:** Once the spec is complete, it becomes the primary context for the **[TDV (Test-Driven Vibing) Mode](./03a-Mode-Spotlight-TDV.md)** to generate well-tested application code, phase by phase.

---

The `SpecsForge` framework is a workflow for transforming high-level product ideas into a precise, living specification library that powers efficient, AI-assisted development. It's built around a custom Cursor Mode that acts as an expert software architect, guiding you through a discovery process to build a comprehensive set of specifications before any code is written.

Once the specification is complete, `SpecsForge` hands off the implementation to the [TDV (Test-Driven Vibing) Mode](./03a-Mode-Spotlight-TDV.md), which uses the specs to execute a rigorous, test-first development cycle.

## The Standard Workflow

Here is the step-by-step process for using the SpecsForge framework:

### Phase 1: Specification Generation (SpecsForge Mode)

1.  **Project Setup:** Copy your standard set of `.cursor/rules/` into the new project.
2.  **Activate Mode:** Activate the `SpecsForge` custom mode in Cursor.
3.  **Define Specs:** Engage in a conversation with the `SpecsForge` persona. It will ask targeted questions to build out a `specs/` directory and a root `SPECS.md` file.
4.  **Generate Implementation Plan:** Once the specs are mature, the final step for the `SpecsForge` mode is to generate a detailed, phased implementation plan inside the `SPECS.md` file.

### Phase 2: Implementation (TDV Mode)

5.  **Switch to TDV Mode:** Activate the `TDV` custom mode in Cursor.
6.  **Implement Phase by Phase:** Work through the implementation plan using the **[TDV (Test-Driven Vibing) Mode](./03a-Mode-Spotlight-TDV.md)** with prompts like:
    > Using @SPECS.md, let's implement Phase 1: User Authentication.
    
    The TDV mode will:
    - Create a detailed `plan.md` for the specific phase
    - Follow strict Test-Driven Development cycles
    - Implement features incrementally with tests leading the way
    
7.  **Verify and Update:** After each phase, you can check the work against the original spec and update the status in `SPECS.md`:
    > @SPECS.md check if Phase 1 was implemented properly. If so, update its status to "Complete". Otherwise, list what's missing.

## Alternative Implementation Approaches (Legacy Support)

For reference, here are alternative ways to handle implementation if you're not using the TDV Mode:

### Direct Implementation Approach
```
Study @SPECS.md for functional specifications.  
Study @.cursor for technical requirements  

Implement Phase 1  
Create tests  
Run and evaluate tests
```

### Manual Verification
```
@SPECS.md check if Phase 1 was implemented properly. If so, update its status to "Complete". Otherwise, list what's missing.
```

## The `SpecsForge` Custom Mode Prompt

This is the system prompt that powers the framework. To use it, create a new Custom Mode in Cursor named `SpecsForge` and paste this into the "System Prompt" field.

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
After the specification files in `specs/` are defined and the root `SPECS.md` overview is complete, your final step is to generate a granular implementation plan within the `SPES.md` file.
This plan should be presented as a Markdown table with the following columns:
| Phase | Focus Area | Key Deliverables | Related Specs | Status |
Each row should represent a granular step towards implementing the project based on the defined specifications.
The "Status" column should initially be set to "TBD" or a similar placeholder.

────────────────────────────────────────
7 · Recommended SPEC template
────────────────────────────────────────
` ` `markdown
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
` ` `
```

---

[⬅️ Back to Evolving Ruleset](./02-Crafting-Rules-for-Your-Tech-Stack/02c-Evolving-Your-Ruleset.md) | [Up: Cursor for Developers](./README.md) | [Next: Terminal Integration ➡️](./04-Leveraging-Terminal-Integration.md)
