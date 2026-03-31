# Default Project Templates

A reusable template package for projects using the Claude.ai + Claude Code workflow.

## What's Included

```
default-templates/
├── README.md                           # This file
├── default-PROJECT-INSTRUCTIONS.md     # Claude.ai project system prompt
├── default-CLAUDE.md                   # Claude Code conventions
├── docs/
│   ├── default-PLANNING.md             # Architecture documentation
│   ├── default-TASK.md                 # Sprint/task tracking
│   ├── default-DECISIONS.md            # Architecture Decision Records
│   └── default-TESTING.md              # Testing standards
├── initials/
│   └── default-init-template.md        # Feature specification template
├── prps/
│   └── templates/
│       └── default-prp-template.md     # Implementation plan template
└── .claude/
    └── commands/
        ├── default-generate-prp.md     # PRP generation command
        └── default-execute-prp.md      # PRP execution command
```

## Quick Start

### 1. Create Your Project Structure

```bash
mkdir my-project && cd my-project
mkdir -p docs initials prps/templates .claude/commands examples
```

### 2. Copy and Customize Templates

Copy each `default-*` file, remove the `default-` prefix, and customize:

```bash
# Example (adjust paths as needed)
cp default-CLAUDE.md CLAUDE.md
cp docs/default-PLANNING.md docs/PLANNING.md
cp docs/default-TASK.md docs/TASK.md
cp docs/default-DECISIONS.md docs/DECISIONS.md
cp docs/default-TESTING.md docs/TESTING.md
cp initials/default-init-template.md initials/init-template.md
cp prps/templates/default-prp-template.md prps/templates/prp-template.md
cp .claude/commands/default-generate-prp.md .claude/commands/generate-prp.md
cp .claude/commands/default-execute-prp.md .claude/commands/execute-prp.md
```

### 3. Set Up Claude.ai Project

1. Create a new Project in Claude.ai
2. Copy contents of `default-PROJECT-INSTRUCTIONS.md`
3. Customize for your project
4. Paste into Project Instructions
5. Attach your `PLANNING.md`, `TASK.md`, `DECISIONS.md` as project files

### 4. Start Building

**In Claude.ai:**
1. Create feature specs: `initials/init-{feature}.md`
2. Discuss architecture decisions
3. Review generated PRPs

**In Claude Code:**
1. Generate PRPs: `/generate-prp initials/init-{feature}.md`
2. Execute PRPs: `/execute-prp prps/prp-{feature}.md`

## Workflow Overview

```
┌─────────────────────────────────────────────────────────────┐
│                     CLAUDE.AI                               │
│                                                             │
│  1. Discuss feature requirements                            │
│  2. Create init-{feature}.md spec                           │
│  3. Review architecture decisions                           │
│  4. Review generated PRPs                                   │
│  5. Troubleshoot blockers                                   │
│                                                             │
└─────────────────────────────────────────────────────────────┘
                              │
                              │ init spec
                              ▼
┌─────────────────────────────────────────────────────────────┐
│                     CLAUDE CODE                             │
│                                                             │
│  1. /generate-prp initials/init-{feature}.md                │
│  2. /execute-prp prps/prp-{feature}.md                      │
│  3. Run tests, fix issues                                   │
│  4. Deploy                                                  │
│  5. Git operations                                          │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

## Customization Guide

### Project Instructions (`default-PROJECT-INSTRUCTIONS.md`)
- Replace `{PROJECT_NAME}` with your project name
- Update tech stack section
- Add domain-specific constraints
- Remove irrelevant sections (e.g., AI API if not used)

### CLAUDE.md
- Customize quick commands for your stack
- Update file structure diagram
- Add project-specific coding conventions
- Update testing commands

### PLANNING.md
- Draw your architecture diagram
- Define your data models
- List your API endpoints
- Set development phases

### TASK.md
- Start with empty task lists
- Add backlog items as you identify them
- Update as you progress

### DECISIONS.md
- Make your first ADRs for tech stack choices
- Document constraints and rationale
- Add ADRs as you make decisions

### TESTING.md
- Update test commands for your stack
- Add project-specific test scenarios
- Document debugging tips as you learn them

### Commands
- Replace `{PROJECT_NAME}` placeholder
- Update file paths for your structure
- Customize test/deploy commands

## Key Principles

1. **Separation of Concerns**: Claude.ai for thinking, Claude Code for doing
2. **Documentation First**: Specs before code
3. **Atomic Progress**: Small, working, committed changes
4. **Cost Awareness**: Budget constraints are explicit
5. **Decision Tracking**: ADRs prevent contradictions
6. **Quality Gates**: Tests and validation at each step

## File Size Convention

All project files should stay under **500 lines**. When approaching this limit:
- Split into multiple modules
- Extract shared code
- Create new files with clear responsibilities

## Commit Convention

Use conventional commits:
- `feat:` - New feature
- `fix:` - Bug fix
- `refactor:` - Code improvement (no behavior change)
- `docs:` - Documentation only
- `test:` - Adding/updating tests
- `chore:` - Maintenance tasks

## Tips for Success

1. **Answer all open questions** in init specs before generating PRPs
2. **Review confidence scores** - don't proceed if below 7
3. **Test manually after deployment** - automated tests miss integration bugs
4. **Update TASK.md frequently** - it's your source of truth
5. **Create ADRs for decisions** - future you will thank you
6. **Keep init specs focused** - one clear problem per spec

## Template Evolution

As you use these templates, improve them:
- Add learnings to TESTING.md
- Create new ADR patterns in DECISIONS.md
- Update init/PRP templates with better sections
- Share improvements back!

---

*Template version: 1.0.0*
*Created from Chaos Dungeon project patterns*
# CE-templates
