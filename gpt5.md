## Cursor Docs Sync TODO (GPT-5 pass)

Keep this guide in lockstep with official Cursor docs and changelogs. Check each item and update text, screenshots, links, and examples as needed.

## Global

- [ ] **Beta → GA/default audit**: Review all mentions of BETA features and update status/naming (Include project structure, Web Search, Auto-run, Play sound on finish).
  - Source: Changelog (scan latest entries) — `https://cursor.com/changelog`
- [ ] **New platform features**: Integrate coverage where relevant:
  - [ ] Background Agent (incl. Slack launch, panel shortcut Cmd/Ctrl+E)
    - Source: 1.0 Changelog — `https://cursor.com/en/changelog/1-0`
  - [ ] BugBot for PR reviews
    - Source: 1.0 Changelog — `https://cursor.com/en/changelog/1-0`
  - [ ] Memories
    - Source: 1.0 Changelog — `https://cursor.com/en/changelog/1-0`
  - [ ] Jupyter Notebook editing (multi-cell apply)
    - Source: 1.0 Changelog — `https://cursor.com/en/changelog/1-0`
  - [ ] Richer chat rendering (Mermaid, tables)
    - Source: 1.0 Changelog — `https://cursor.com/en/changelog/1-0`
  - [ ] Global ignore patterns/user-level ignores and `.cursorignore`
    - Source: Changelog — `https://cursor.com/changelog`
  - [ ] Dashboard usage analytics; export/duplicate chats
    - Source: Changelog — `https://cursor.com/changelog`
- [ ] **Models**: Refresh availability, naming, long-context support, and guidance on “Max mode”.
  - Source: Changelog (models/Max mode updates) — `https://cursor.com/changelog`
- [ ] **Links**: Prefer official `docs.cursor.com`/Cursor changelog pages; annotate any community resources as such.
- [ ] **Indexing**: Document automatic indexing behavior and configuration; include `.cursorignore` examples.
  - Source: Concepts — `https://docs.cursor.com/get-started/concepts`
- [ ] **Advanced dev features (optional)**: Consider adding AI Review and Shadow Workspace tips where they add value.
  - Source (Community): Cursor 101 — `https://github.com/alchaincyf/cursor101`
- [ ] **Assets**: Re-capture screenshots if UI labels/locations changed in settings, Docs, Custom Modes, etc.

## Root

- [x] `README.md`
  - [ ] Verify links to official Rules and Custom Modes docs.
    - Sources: Rules — `https://docs.cursor.com/context/rules`, Custom Modes — `https://docs.cursor.com/chat/custom-modes`
  - [x] Add brief mentions of Background Agent, BugBot, Memories, richer chat in high-level overview.
    - Source: 1.0 Changelog — `https://cursor.com/en/changelog/1-0`
  - [ ] Update model examples/names to current lineup.
    - Source: Changelog — `https://cursor.com/changelog`
  - [x] Add sources section with official links (Concepts, Changelog, 1.0).
    - Done in root README.

- [ ] `CHANGELOG.md`
  - [ ] Add entry for this docs-sync pass (highlights, impacted sections).

- [ ] `Yolo-README.md`
  - [ ] Keep disclaimer; no maintenance needed.

## 01-Cursor-for-Everyone

- [x] `00-The-Golden-Rule-Context-is-King.md`
  - [x] Confirm Web Search status/naming; remove outdated BETA labels.
    - Source: Concepts — `https://docs.cursor.com/get-started/concepts`
  - [x] Mention Background Agent availability and panel shortcut.
    - Source: 1.0 Changelog — `https://cursor.com/en/changelog/1-0`

- [x] `01-Welcome-to-Cursor.md`
  - [x] Add marquee features: Background Agent, BugBot, Memories, richer chat.
    - Source: 1.0 Changelog — `https://cursor.com/en/changelog/1-0`
  - [x] Align terminology with current docs (Chat/Composer/Inline Edit naming if referenced).
    - Source: Get Started — `https://docs.cursor.com/get-started/introduction`

- [x] `02-Understanding-Cursor-Rules/README.md`
  - [ ] Verify current UI naming for project rules vs user/global rules and their locations.
  - [ ] Ensure `.mdc` extension/frontmatter remains current.
    - Source: Rules — `https://docs.cursor.com/context/rules`

- [x] `02-Understanding-Cursor-Rules/02a-What-Why-How.md`
  - [ ] Validate frontmatter keys (`description`, `globs`, `alwaysApply`) and examples (string vs array for `globs`).
  - [ ] Confirm how rules are attached (description triggers vs globs vs alwaysApply behavior).
    - Source: Rules — `https://docs.cursor.com/context/rules`

- [x] `02-Understanding-Cursor-Rules/02b-Interactive-Rule-Development.md`
  - [ ] Verify the `/Generate Cursor Rules` command name and availability.
  - [ ] Keep guidance on referencing master rules via `@` mentions.
    - Source: Rules — `https://docs.cursor.com/context/rules`

- [x] `02-Understanding-Cursor-Rules/02c-Rules-for-Stellar-Documentation.md`
  - [ ] Keep examples; optionally add note on `.cursorignore` for large doc trees.
    - Source: Concepts — `https://docs.cursor.com/get-started/concepts`

- [x] `03-Choosing-Your-AI-Model.md`
  - [ ] Refresh recommended models and names (Anthropic, OpenAI, Google) and availability inside Cursor.
  - [ ] Reassess “Avoid MAX” guidance to reflect current “Max mode” behavior/costs.
  - [ ] Confirm “Auto” model selection naming/behavior.
    - Source: Changelog (models/Max mode) — `https://cursor.com/changelog`

- [x] `04-Custom-Modes-Tailoring-Cursor-to-You/README.md`
  - [ ] Confirm UI path/name for creating modes; verify where modes appear in chat.
  - [ ] Verify tool toggles naming/availability.
    - Source: Custom Modes — `https://docs.cursor.com/chat/custom-modes`

- [x] `04a-Introduction-to-Custom-Modes.md`
  - [ ] Update screenshots/labels if the UI changed.
  - [ ] Confirm “mode shows in chat input selector”.
    - Source: Custom Modes — `https://docs.cursor.com/chat/custom-modes`

- [x] `04b-Mode-Spotlight-Learn.md`
  - [ ] Ensure Web/Search tool naming matches current settings and permissions.
    - Source: Concepts — `https://docs.cursor.com/get-started/concepts`

- [x] `04c-Mode-Spotlight-MDP.md`
  - [ ] Neutral; optionally add tip to export chats to Markdown.
    - Source: Changelog — `https://cursor.com/changelog`

- [x] `04d-Mode-Spotlight-Research.md`
  - [ ] Confirm Web Search naming; add note on @link/PDF parsing if supported.
    - Source: Changelog — `https://cursor.com/changelog`

- [x] `04e-Mode-Spotlight-Yolo.md`
  - [ ] No product coupling; leave as-is.

- [x] `05-Essential-Cursor-Settings.md`
  - [ ] “Include project structure (BETA)” → verify current status/name; update text and screenshot.
  - [ ] “Web Search Tool (BETA)” → verify status/name; add @link/PDF parsing where applicable.
  - [ ] “Enable auto-run mode” → verify label/location and current best-practice cautions.
  - [ ] “Play sound on finish (BETA)” → verify status.
  - [ ] Command Denylist → confirm setting exists; recommend `rm` at minimum; update restore-behavior note.
  - [ ] Add global ignore patterns and `.cursorignore` guidance.
  - [ ] Add Background Agent panel shortcut and dashboard usage analytics mention.
    - Sources: Concepts — `https://docs.cursor.com/get-started/concepts`, Changelog — `https://cursor.com/changelog`, 1.0 Changelog — `https://cursor.com/en/changelog/1-0`

- [x] `06-The-Model-Context-Protocol-MCP/README.md`
  - [ ] Add one-click MCP install and OAuth support notes.
  - [ ] Confirm settings path/file used to register MCP servers (still `mcp.json`?).
    - Source: 1.0 Changelog — `https://cursor.com/en/changelog/1-0`

- [x] `06a-MCP-The-Big-Picture.md`
  - [ ] Align terminology; add link to MCP Inspector and official MCP docs.
    - Sources: MCP Inspector — `https://modelcontextprotocol.io/docs/tools/inspector`

- [x] `06b-MCP-in-Action-Jira-and-Confluence.md`
  - [ ] Validate recommended image (`ghcr.io/sooperset/mcp-atlassian`) and env names; update if an official image now exists.
  - [ ] Clarify cloud/server token setups; read-only defaults; example tool command names.
  - [ ] Mention one-click setup/OAuth if available.
    - Sources: Atlassian MCP (community) — `https://github.com/sooperset/mcp-atlassian`, 1.0 Changelog — `https://cursor.com/en/changelog/1-0`

- [x] `06c-MCP-Spotlight-DBHub.md`
  - [ ] Confirm `@bytebase/dbhub` package/flags; DSN examples; read-only flag.
  - [ ] Add MCP Inspector tip for debugging.
    - Sources: DBHub — `https://github.com/bytebase/dbhub`, MCP Inspector — `https://modelcontextprotocol.io/docs/tools/inspector`

- [ ] `06d-Exploring-the-MCP-Ecosystem.md`
  - [ ] Keep `mcp.so`/PulseMCP; add official server directories and in-app discovery if present.
    - Sources: mcp.so — `https://mcp.so/`, PulseMCP — `https://www.pulsemcp.com/servers`, MCP servers — `https://github.com/modelcontextprotocol/servers`

- [x] `07-Quick-Look-The-Docs-Feature.md`
  - [ ] Verify it’s still called “@Docs”; confirm settings label/path (“Docs” vs “Knowledge”).
  - [ ] Add PDF parsing/@link notes if supported.
    - Sources: Get Started/Concepts — `https://docs.cursor.com/get-started/concepts`, Changelog — `https://cursor.com/changelog`

- [x] `08-Markdown-Driven-Planning.md`
  - [ ] Neutral; optionally add Duplicate Chats and Export Chat tips.
    - Source: Changelog — `https://cursor.com/changelog`

## 02-Cursor-for-Developers

- [ ] `00-The-Vibe-Programmer-Manifesto.md`
  - [ ] No product coupling; keep as-is.

- [ ] `01-Mastering-the-Docs-Feature.md`
  - [ ] Confirm settings path/label for adding docs sources.
  - [ ] Add advanced capabilities: PDFs, @link, interplay with codebase indexing.
  - [ ] Note explicit prompts referencing the chosen docs.
    - Sources: Concepts — `https://docs.cursor.com/get-started/concepts`, Changelog — `https://cursor.com/changelog`

- [ ] `02-Crafting-Rules-for-Your-Tech-Stack/README.md`
  - [ ] Ensure the bootstrap-from-docs flow matches current UI.
  - [ ] Optionally add AI Review/Shadow Workspace as complementary guardrails.
    - Sources: Rules — `https://docs.cursor.com/context/rules`, (Community) Cursor 101 — `https://github.com/alchaincyf/cursor101`

- [ ] `02a-Why-Tech-Specific-Rules-Matter.md`
  - [ ] Keep examples; ensure language mentions current stack specifics (e.g., Pydantic v2) as examples, not prescriptions.
    - Source: Rules — `https://docs.cursor.com/context/rules`

- [ ] `02b-Auto-Generating-Rules-from-Docs.md`
  - [ ] Confirm `@Docs` flow/UI; update screenshots/labels.
  - [ ] Keep master rule `@`-reference pattern.
    - Sources: Concepts — `https://docs.cursor.com/get-started/concepts`, Rules — `https://docs.cursor.com/context/rules`

- [ ] `02c-Evolving-Your-Ruleset.md`
  - [ ] Add note to use release notes via `@Docs` for rule refresh; consider team ceremonies tip.
    - Sources: Concepts — `https://docs.cursor.com/get-started/concepts`

- [ ] `03-The-SpecsForge-Framework.md`
  - [ ] Neutral; optionally add Duplicate Chats/export chat for branching/recordkeeping.
    - Source: Changelog — `https://cursor.com/changelog`

- [ ] `03a-Mode-Spotlight-TDV.md`
  - [ ] Neutral; optionally mention Background Agent for long-running test cycles.
    - Source: 1.0 Changelog — `https://cursor.com/en/changelog/1-0`

- [ ] `04-Leveraging-Terminal-Integration.md`
  - [ ] Verify Auto-run label/behavior; recommend non-interactive flags by default.
  - [ ] Mention Background Agent for long-running commands; confirm Inline Edit/Cmd+K UI changes if referenced.
    - Sources: Concepts — `https://docs.cursor.com/get-started/concepts`, Changelog — `https://cursor.com/changelog`

- [ ] `05-Working-Across-Repositories.md`
  - [ ] Confirm “File > Add Folder to Workspace…” label.
  - [ ] Add `.cursorignore` tips for large assets; note indexing behavior across multiple roots.
    - Sources: Concepts — `https://docs.cursor.com/get-started/concepts`

## Workshops & Assets

- [ ] Skim workshop README files for old labels/screenshots; queue refresh if needed.
- [ ] Update/recapture assets:
  - [ ] `include_project_structure.png`
  - [ ] `web_search_tool.png`
  - [ ] `auto_run_mode.png`
  - [ ] `add_docs_sources_ui.png`
  - [ ] `custom_modes_setup_ui.png`
  - [ ] `add_custom_mode_ui.png`
  - [ ] (New) Background Agent panel, dashboard analytics, export/duplicate chat as needed
    - Source: Current UI (capture fresh from latest Cursor build)

## Likely Changes To Verify (Quick Reference)

- [ ] Settings status for Include project structure, Web Search, Play sound → GA/default?
- [ ] Background Agent (incl. Slack), BugBot, Memories, Jupyter notebooks, richer chat rendering
- [ ] Models: names/availability/Max mode guidance
- [ ] @Docs naming, settings path; @link/PDF parsing
- [ ] MCP: one-click install, OAuth; Atlassian server image/env; MCP Inspector
- [ ] Indexing: automatic indexing settings; `.cursorignore` examples
- [ ] Shortcuts/UI: Cmd/Ctrl+E (Background Agent), Inline Edit/Cmd+K changes, multi-root workspaces
  - Sources: Changelog — `https://cursor.com/changelog`, 1.0 Changelog — `https://cursor.com/en/changelog/1-0`, Concepts — `https://docs.cursor.com/get-started/concepts`, MCP Inspector — `https://modelcontextprotocol.io/docs/tools/inspector`


