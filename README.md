# claude-md-generator

Interactive builder for the per-project markdown file every coding agent should read first. Outputs `CLAUDE.md` (Claude Code) or `AGENTS.md` (general convention). Browser only.

**Live demo:** https://0xelitesystem.github.io/claude-md-generator/

## Use

Open [`index.html`](./index.html). Fill in what's relevant: project name, description, stack with versions, build/test/run commands, codebase structure, conventions, gotchas, hard constraints, recent direction.

Switch between CLAUDE.md and AGENTS.md output formats. Copy or download.

## Why

Most teams hand-roll their CLAUDE.md / AGENTS.md as a stream of consciousness. The result misses the sections agents actually use (build commands, structure, gotchas) and over-includes things they don't (aspirational descriptions, generic style advice).

This tool enforces structure: sections in the right order, headings agents recognize, no filler, no bullet-shaped restatements of the obvious.

## What goes in

The form's sections, in priority order:

- **Stack and versions**, pin them, agents have stale knowledge of versions
- **Commands**, build, test, run, lint (the agent will need these)
- **Codebase structure**, where things live, only if non-default
- **Conventions**, naming, patterns, style choices that aren't obvious
- **Hard constraints**, things that must NOT change
- **Gotchas**, past failures, specific mistakes to avoid
- **Active migrations**, recent direction the agent should know

Skip sections that don't apply. The output structure adapts.

## What's NOT in

- "Welcome to our project" boilerplate
- Generic coding advice
- Aspirational descriptions
- Detailed style rules better left to a linter
- Project mission statements

These reduce signal in agent context.

## Privacy

Everything runs in your browser. No upload, no analytics, no third-party scripts.

## Run locally

```
git clone https://github.com/0xelitesystem/claude-md-generator
cd claude-md-generator
```

Open `index.html` in a browser. Or:

```
python -m http.server 8000
```

## Contribute

PRs welcome:

- Output formats for other agent tools (Aider's conventions file, .cursorrules)
- Field validation (e.g. warning when "stack" doesn't include versions)
- Stack-specific section presets

Don't add: external scripts, npm dependencies, telemetry. Single file.

## Build

No build. Single HTML file.

## License

MIT.

## Related

- [cursor-rules-collection](https://github.com/0xelitesystem/cursor-rules-collection) - examples by stack
- [agentic-workflow-patterns](https://github.com/0xelitesystem/agentic-workflow-patterns) - shared-context-files pattern
- [ai-coding-prompt-recipes](https://github.com/0xelitesystem/ai-coding-prompt-recipes) - prompts that work with a good context file
