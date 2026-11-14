# Claude Project Guidelines - KinetRig

Agent Profile: Claude (CLAUDE.md)

## System Architecture & Overview
This file contains instructions and context for Claude when working within `KinetRig`.

## Available AI Skills & Tools
The following skills and tools are configured for this environment:

### Git Workflow & Conventional Commits
- **Description:** Smart Conventional Commits, diff metric analysis & commit approval
- **Usage Instructions:**
  1. Change Detection & Metrics: Before creating a commit or when instructed, inspect working tree changes using `git status` and `git diff --stat`. If there are no changes ('nothing to commit, working tree clean'), immediately notify the user in English: 'Working tree clean: nothing to commit.' and stop without prompting for a commit.
2. Security Guard: Verify that no secrets, `.env` files, API keys, certificates (*.pem), or build artifacts are staged. Warn immediately if detected.
3. Conventional Message Generation: Draft a concise, context-aware Conventional Commit message (`feat`, `fix`, `docs`, `chore`, `test`, `refactor`) with appropriate scope based on exact diffs (e.g. `feat(auth): add jwt refresh token validation`).
4. Strict Attribution Policy: NEVER include 'Co-Authored-By: Claude Code', 'Generated with Claude Code', or any AI attribution/trailers in commit messages or pull request bodies.
5. User Approval Protocol: Always present the draft commit message and changed file list to the user first. Ask for confirmation before executing `git commit`.

### Graphify (Code & Knowledge Graph)
- **Description:** Code dependency graph & God Nodes
- **Usage Instructions:**
  To analyze and graph project dependencies, run 'python rigtools/graphify.py .'. This generates an interactive visual graph at 'graphify-out/graph.html', raw graph data at 'graphify-out/graph.json', and an architectural summary at 'graphify-out/GRAPH_REPORT.md'. MANDATORY: Always inspect 'graphify-out/GRAPH_REPORT.md' first before searching or reading multiple files to trace God Nodes and direct connections, cutting token usage.
- **Pip Dependencies:** `networkx`

### UI/UX Pro Max (Design System & UX Intelligence)
- **Description:** Searchable UI/UX design system generator, color/font pairings, 22 tech stacks, and pre-delivery UX audit
- **Usage Instructions:**
  Follow the UI/UX Pro Max workflow (full guide in rigtools/ui_ux_pro_max/SKILL.md; detailed rules in rigtools/ui_ux_pro_max/references/quick-reference.md and rigtools/ui_ux_pro_max/references/pro-rules.md). Before designing or building UI:
1. Generate a cohesive design system first: run `python rigtools/ui_ux_pro_max/scripts/search.py "<product_type> <industry> <keywords>" --design-system -p "<Project Name>"` (add `--persist --output-dir .` to save `design-system/<slug>/MASTER.md`).
2. Query stack or domain specifics as needed: `--stack <nextjs|react|html-tailwind|shadcn|vue|svelte|laravel|flutter|react-native>` or `--domain <style|color|typography|chart|landing|ux|icons|motion>`.
3. Enforce pre-delivery checks: no OS emojis as UI icons (use SVG), minimum 4.5:1 text contrast, visible keyboard focus, `prefers-reduced-motion`, and responsive breakpoints (375px, 768px, 1024px, 1440px).


## Operating Principles
- Follow standard project conventions and keep code modular.
- Validate all assumptions and run tests when adding features.

