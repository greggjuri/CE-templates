# {PROJECT_NAME} - Task Tracker

## Current Sprint: {Sprint Name}

### In Progress
- [ ] {Task description} (assigned to: {who})

### Up Next
- [ ] {init-file.md} - {Brief description}
- [ ] {init-file.md} - {Brief description}

---

## Recently Completed

### {Feature Name} (prp-XX)
- [x] {Completed item 1}
- [x] {Completed item 2}
- [x] {Completed item 3}

### {Another Feature} (prp-YY)
- [x] {Completed item 1}
- [x] {Completed item 2}

---

## Backlog

### Phase {N} - {Phase Name} (Prioritized)
- [ ] {init-file.md} - {Brief description}
- [ ] {init-file.md} - {Brief description}
- [ ] {init-file.md} - {Brief description}

### Phase {N+1} - {Phase Name}
- [ ] {init-file.md} - {Brief description}
- [ ] {Feature idea} - {Brief description}

### Phase {N+2} - {Phase Name}
- [ ] {Feature idea}
- [ ] {Feature idea}

---

## Completed

### {Category 1}
- [x] {init-file.md} - {Brief description}
- [x] {init-file.md} - {Brief description}

### {Category 2}
- [x] {init-file.md} - {Brief description}
- [x] {init-file.md} - {Brief description}

---

## Architecture Decisions

### Key Learnings from {Feature}
1. **{Learning 1}** - {Explanation}
2. **{Learning 2}** - {Explanation}
3. **{Learning 3}** - {Explanation}

### Implemented: {Pattern/System Name}
{Description of what was implemented and why}

---

## Notes

### Configuration
- {CONFIG_NAME}: {value}
- {CONFIG_NAME}: {value}

### Cost Tracking (if applicable)
- Current estimated monthly: ~${X}
- Target: < ${Y}/month
- Protection: {Cost protection mechanism}

### Known Issues
- {Issue 1}: {Brief description and workaround if any}
- {Issue 2}: {Brief description}

---

*Last updated: {YYYY-MM-DD} ({what was updated})*

---

## Template Usage Notes

**Task Status Flow:**
```
Backlog → Up Next → In Progress → Recently Completed → Completed
```

**Update Triggers:**
- Starting a task: Move to "In Progress"
- Completing a task: Move to "Recently Completed"
- Starting new sprint: Move "Recently Completed" to "Completed"
- Learning something: Add to "Architecture Decisions"
- Finding an issue: Add to "Known Issues"

**Format for task items:**
- Backlog: `- [ ] {init-file.md} - {Brief description}`
- Completed: `- [x] {description}`
- With learnings: Add subsection under "Architecture Decisions"
