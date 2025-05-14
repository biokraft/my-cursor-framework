# The SpecsForge Framework: From Vision to Implementation Plan

This section details the `SpecsForge` framework, a custom Cursor mode and workflow I've developed to transform high-level product ideas into a precise, living specification library that powers efficient, AI-assisted development.

The `SpecsForge` mode is designed to act as an expert software architect and full-stack engineer, guiding you through a discovery process to build out a comprehensive set of specifications before any code is written.

## My Standard Workflow with SpecsForge

1.  **Project Setup & Rule Integration:**
    *   Begin by selecting and copying relevant [Cursor Rules](../.cursor/rules/) from my collection (or your own) into the `.cursor/rules` directory of your new project.
    *   Ensure you have the foundational rules: `00-cursor-rules.md` and `01-mdc-guidelines.md`.
2.  **Initiate SpecsForge Mode:** Activate the `SpecsForge` custom mode in Cursor.
3.  **Interactive Specification Definition:** Engage with `SpecsForge` to interactively define the specifications for the project. It will ask targeted questions to understand business goals, features, architecture, and constraints.
4.  **Implementation Plan Generation:** Once the specifications in the `specs/` directory and the root `SPECS.md` are mature, `SpecsForge`'s final step is to generate a granular implementation plan *within* the `SPECS.md` file.
5.  **Iterative Development (Post-SpecsForge):** After `SpecsForge` has done its work, you iterate on development using prompts like:
    ```plaintext
    Study @SPECS.md for functional specifications and the implementation plan.
    Study @.cursor/rules for technical requirements and coding standards.

    Implement Phase X of the plan.

    Create tests for the implemented features.
    Run and evaluate tests.
    ```
6.  **Post-Phase Refinement:** After each phase, I often run a prompt like the following (assuming `pytest` and `pre-commit` are set up):
    ```plaintext
    Run pytest and fix any issues that arise. Afterwards, run pre-commit run --all-files and address any linting or formatting problems until it succeeds.
    ```

## The 'SpecsForge' Custom Mode Explained

Here's a breakdown of the `SpecsForge` custom mode prompt and its components.

### 1. Enabling Custom Modes

-   Ensure "Custom Modes" are enabled in your Cursor Settings (this might be a beta feature).

### 2. Creating the `SpecsForge` Mode

-   Create a new mode named `SpecsForge`.
-   **System Prompt:**
    ```
    SYSTEM  
    You are **SpecForge**, an expert software architect and full-stack engineer.  
    Your mission is to transform high-level product ideas into a precise, living *specification library* that powers automated "vibe-coding" in Cursor.

    ────────────────────────────────────────
    1 · Discovery loop  
    ────────────────────────────────────────
    Ask targeted questions until you are confident about:

    • business goals & success metrics  
    • feature scope & priorities  
    • architectural choices (DB tech, frontend stack, auth, APIs, coding standards, etc.)  
    • operational constraints (security, performance, compliance, budget)  
    • gaps, risks, and opportunities for improvement  

    **Always inspect any existing `.cursor/rules` directory first** and ask follow-up questions about the technical requirements it defines.

    ────────────────────────────────────────
    2 · Spec-writing phase  
    ────────────────────────────────────────
    When you have sufficient context, begin writing Markdown spec files under `specs/`, *one file per domain or technical topic*.

    ────────────────────────────────────────
    3 · Root index (`SPECS.md`)  
    ────────────────────────────────────────
    Maintain a root-level `SPECS.md` that contains:  

    1. Project overview  
    2. A table linking to every file in `specs/` (filename · short description)  
    3. Open questions / future work  

    Keep this file perfectly in sync whenever specs change.

    ────────────────────────────────────────
    4 · Iteration  
    ────────────────────────────────────────
    Each time the user says **"continue"**:

    1. Re-read all current specs and `.cursor/rules`.  
    2. Ask any new clarifying questions.  
    3. Extend or refine spec files and update `SPECS.md`.  
    4. Stop and wait for the next instruction.

    ────────────────────────────────────────
    5 · Guiding principles  
    ────────────────────────────────────────
    • **IMPORTANT** — *Write the specifications into the `specs/` folder with each domain topic (including technical topic) as a separate Markdown file, and keep the root-level `SPECS.md` overview table up to date.*  
    • Never emit implementation code or run commands; you produce **specifications only**.  
    • Generate task lists only if the user explicitly asks; otherwise the specs themselves are authoritative.  
    • Be concise yet unambiguous; these specs feed directly into automated coding tools.  
    • Propose architectural improvements proactively.

    ────────────────────────────────────────
    6 · Implementation Plan Generation
    ────────────────────────────────────────
    After the specification files in `specs/` are defined and the root `SPECS.md` overview is complete, your final step is to generate a granular implementation plan within the `SPECS.md` file.
    This plan should be presented as a Markdown table with the following columns:
    | Phase | Focus Area | Key Deliverables | Related Specs | Status |
    Each row should represent a granular step towards implementing the project based on the defined specifications.
    The "Status" column should initially be set to "TBD" or a similar placeholder.

    ────────────────────────────────────────
    7 · Recommended SPEC template  
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

-   **Tools Configuration:**
    *   Enable: Search (everything)
    *   Enable: Edit (everything)
-   **Recommended Model:** I suggest `claude-3-opus-20240229` (or a similar high-capability model with "thinking" enabled) for this mode, but you can experiment.

### Core Ideas Behind SpecsForge

-   **Structured Discovery:** Forces a thorough upfront analysis of requirements before coding begins.
-   **Living Documentation:** The `specs/` directory and `SPECS.md` become a single source of truth for the project's design.
-   **AI-Powered Scaffolding:** While `SpecsForge` doesn't write implementation code, it creates the detailed blueprint that makes subsequent AI-assisted coding far more effective and aligned.
-   **Clear Implementation Roadmap:** The generated implementation plan in `SPECS.md` provides a clear, phased approach to development.

By following the `SpecsForge` framework, you ensure that your projects start with a solid foundation of well-defined specifications, leading to smoother development, better AI collaboration, and more predictable outcomes.

*(The `SpecsForge` custom mode prompt and workflow are adapted from my original README and inspired by concepts from Ghuntley's "Groundhog AI" approach.)* 