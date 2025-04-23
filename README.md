# Collection of my personal Cursor Best Practices
Here I just store my Cursor best practices, rules, snippets and so on from whatever I gathered on the interwebs so far.

# What to expect

I'll smash in a bunch of markdown files summarising on how I use Cursor, as well as more specific guides on some concepts.

Under `.cursor/rules` you can find a collection of my Cursor rules.

You can pick and choose what you like.

# My Standard Workflow

## Project Setup
1. Pick and choose cursor rules from `.cursor/rules`
2. Copy the chosen `.cursor/rules` to the root of your project
3. Start with the `SpecsForge` custom mode and interactively define the specs for the project.
4. Ask Cursor to edit the `SPECS.md` file to include an implementation plan broken down into granular phases.
5. Iterate with the following prompt:
```
Study @SPECS.md for functional specifications.
Study @.cursor for technical requirements

Implement Phase X

Create tests
Run and evaluate tests
```
6. After each phase complete I like to run the following prompt (requires `pytest` and `pre-commit`):
```
Run pytest and fix issues. Afterwards run pre-commit run --all-files until it succeeds
```

### 'SpecsForge' Custom Mode

Cursor custom modes are a way to extend Cursor's capabilities by adding custom agent modes with prompts and tool settings. I have built one for defining specs for my projects.

1. Enable Custom Modes in Cursor Settings (currently beta feature)
2. Create a new mode named `SpecsForge`
3. Add the following prompt:
```
SYSTEM  
You are **SpecForge**, an expert software architect and full-stack engineer.  
Your mission is to transform high-level product ideas into a precise, living *specification library* that powers automated “vibe-coding” in Cursor.

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
Each time the user says **“continue”**:

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
6 · Recommended SPEC template  
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
```
4. Add the following tools:
- Search (everything)
- Edit (everything)

# Acknowledgements & Sources

- [From Design doc to code: the Groundhog AI coding assistant (and new Cursor vibecoding meta)](https://ghuntley.com/specs/)
- [Cursor Rules](https://docs.cursor.com/context/rules)
- [Cursor Custom Modes](https://docs.cursor.com/chat/custom-modes)
