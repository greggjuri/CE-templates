# {PROJECT_NAME} - Architecture Decisions

## ADR-001: {First Major Decision Title}

**Date**: {YYYY-MM-DD}
**Status**: Accepted

### Context
{What is the issue that we're seeing that is motivating this decision?}

### Decision
{What is the change that we're proposing and/or doing?}

### Rationale
- {Reason 1}
- {Reason 2}
- {Reason 3}

### Alternatives Considered
| Option | Pros | Cons | Verdict |
|--------|------|------|---------|
| {Option 1} | {Pros} | {Cons} | {Why rejected/selected} |
| {Option 2} | {Pros} | {Cons} | {Why rejected/selected} |

### Consequences

**Positive:**
- {Benefit 1}
- {Benefit 2}

**Negative:**
- {Tradeoff 1}
- {Tradeoff 2}

---

## ADR-002: {Second Decision Title}

**Date**: {YYYY-MM-DD}  
**Status**: Accepted

### Context
{Context description}

### Decision
{Decision description}

### Rationale
- {Reason 1}
- {Reason 2}

### Consequences

**Positive:**
- {Benefit 1}

**Negative:**
- {Tradeoff 1}

---

## ADR-003: {Third Decision Title}

**Date**: {YYYY-MM-DD}  
**Status**: Proposed

### Context
{Context description}

### Decision
{Decision description}

### Rationale
{Rationale}

### Consequences
{Consequences}

---

## Template for New Decisions

```markdown
## ADR-XXX: Title

**Date**: YYYY-MM-DD  
**Status**: Proposed/Accepted/Deprecated/Superseded

### Context
What is the issue that we're seeing that is motivating this decision?

### Decision
What is the change that we're proposing and/or doing?

### Rationale
Why is this the best choice? What alternatives were considered?

### Alternatives Considered (optional)
| Option | Pros | Cons | Verdict |
|--------|------|------|---------|
| Option A | ... | ... | Selected/Rejected |

### Consequences
What becomes easier or more difficult because of this change?

**Positive:**
- Benefit 1
- Benefit 2

**Negative:**
- Tradeoff 1
- Tradeoff 2

### References (optional)
- PRP: `prps/prp-xxx.md`
- Init spec: `initials/init-xxx.md`
- External: [link]
```

---

## ADR Status Definitions

| Status | Meaning |
|--------|---------|
| **Proposed** | Under discussion, not yet approved |
| **Accepted** | Approved and in effect |
| **Deprecated** | No longer recommended, but may still be in use |
| **Superseded** | Replaced by another ADR (link to replacement) |

## When to Create an ADR

Create an ADR when:
- Choosing between multiple valid approaches
- Making a decision that's hard to reverse
- Setting a pattern others should follow
- Explicitly rejecting an approach
- Learning something that changes future decisions

## ADR Numbering

- Use sequential numbers: ADR-001, ADR-002, etc.
- Never reuse numbers, even for superseded ADRs
- Reference superseded ADRs: "Supersedes ADR-003"

## Key Principles Captured in ADRs

{As you make decisions, summarize key principles here}

1. **{Principle 1}**: {Brief explanation}
2. **{Principle 2}**: {Brief explanation}
3. **{Principle 3}**: {Brief explanation}
