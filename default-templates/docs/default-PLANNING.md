# {PROJECT_NAME} - Project Planning

## Project Vision

{2-3 sentence description of what you're building and why}

## Architecture Overview

```
┌─────────────────────────────────────────────────────────────────────┐
│                         FRONTEND                                     │
│                  {Framework + Language}                              │
│                    {Hosting solution}                                │
│                  {your-domain.com}                                   │
└─────────────────────────────────────────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────────────┐
│                       API LAYER                                      │
│                    {API Gateway/etc}                                 │
└─────────────────────────────────────────────────────────────────────┘
                              │
                              ▼
┌─────────────────────────────────────────────────────────────────────┐
│                       BACKEND                                        │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐                 │
│  │  Handler 1  │  │  Handler 2  │  │  Handler 3  │                 │
│  └─────────────┘  └─────────────┘  └─────────────┘                 │
└─────────────────────────────────────────────────────────────────────┘
                              │
              ┌───────────────┼───────────────┐
              ▼               ▼               ▼
┌─────────────────┐  ┌─────────────────┐  ┌─────────────────┐
│    Database     │  │  External APIs  │  │   Monitoring    │
└─────────────────┘  └─────────────────┘  └─────────────────┘
```

## Cost Budget: ${X}/month Maximum (if applicable)

### Service Cost Breakdown
| Service | Est. Cost | Notes |
|---------|-----------|-------|
| {Service 1} | ${X} | {Notes} |
| {Service 2} | ${Y} | {Notes} |
| {Service 3} | ${Z} | {Notes} |
| **Total** | **${TOTAL}** | Target: < ${BUDGET} |

### Cost Protection Strategies
1. {Strategy 1: e.g., rate limiting}
2. {Strategy 2: e.g., usage alerts}
3. {Strategy 3: e.g., caching}

## Tech Stack

### Frontend
- **Framework**: {React/Vue/etc} + TypeScript
- **Styling**: {Tailwind/CSS Modules/etc}
- **Build**: {Vite/Webpack/etc}
- **State**: {Context/Redux/Zustand/etc}
- **HTTP**: {fetch/axios/etc}

### Backend
- **Runtime**: {Python/Node.js/etc} {version}
- **Framework**: {Lambda/Express/FastAPI/etc}
- **Validation**: {Pydantic/Zod/etc}
- **Logging**: {Your logging solution}
- **AI**: {AI service if applicable}

### Infrastructure
- **IaC**: {CDK/Terraform/Pulumi/etc}
- **CI/CD**: {GitHub Actions/etc}
- **Domain**: {your-domain.com}

## Data Models

### Entity 1 (Database)
```
{Key format, e.g., PK: USER#{user_id}}
{SK format, e.g., SK: ENTITY#{entity_id}}
Attributes:
  - field1: type
  - field2: type
  - field3: type
  - created_at: ISO timestamp
  - updated_at: ISO timestamp
```

### Entity 2 (Database)
```
{Similar structure}
```

### Shared Types
```
{TypeName}:
  - field: type
  - field: type
```

## API Endpoints

| Method | Path | Description |
|--------|------|-------------|
| POST | /entities | Create entity |
| GET | /entities | List entities |
| GET | /entities/{id} | Get entity details |
| PUT | /entities/{id} | Update entity |
| DELETE | /entities/{id} | Delete entity |

### Authentication
{Describe your auth approach}

### Error Responses
```json
{
  "error": "string",
  "detail": "string (optional)"
}
```

## Project Structure

```
{project-name}/
├── CLAUDE.md                    # Project rules for Claude Code
├── docs/
│   ├── PLANNING.md              # This file
│   ├── TASK.md                  # Current tasks
│   ├── DECISIONS.md             # Architecture decisions
│   └── TESTING.md               # Testing standards
├── initials/                    # Feature specifications (init-*.md)
├── prps/                        # Implementation plans (prp-*.md)
│   └── templates/
│       └── prp-template.md
├── .claude/
│   └── commands/
│       ├── generate-prp.md
│       └── execute-prp.md
├── examples/                    # Code patterns for Claude Code
├── {infrastructure}/            # IaC code
├── {backend}/                   # Backend code
│   ├── {module1}/
│   ├── {module2}/
│   └── {shared}/
├── {frontend}/                  # Frontend code
│   ├── src/
│   │   ├── components/
│   │   ├── hooks/
│   │   ├── services/
│   │   └── types/
│   └── package.json
└── README.md
```

## Development Phases

### Phase 1: Foundation (Week X)
- [ ] Project structure setup
- [ ] Infrastructure (database, API, hosting)
- [ ] Basic CRUD API
- [ ] Frontend shell

### Phase 2: Core Features (Week X)
- [ ] {Core feature 1}
- [ ] {Core feature 2}
- [ ] {Core feature 3}

### Phase 3: Enhancement (Week X)
- [ ] {Enhancement 1}
- [ ] {Enhancement 2}
- [ ] {Enhancement 3}

### Phase 4: Polish (Week X)
- [ ] {Polish item 1}
- [ ] {Polish item 2}
- [ ] Production deployment

### Future Phases
- {Future feature 1}
- {Future feature 2}
- {Future feature 3}

## Key Constraints

1. **{Constraint 1}** - {Description and reason}
2. **{Constraint 2}** - {Description and reason}
3. **500-line file limit** - Split into modules when approaching
4. **Commit after each feature** - Atomic, working commits
5. **{Constraint N}** - {Description and reason}

## Success Criteria

1. [ ] {Criterion 1 - user can do X}
2. [ ] {Criterion 2 - system achieves Y}
3. [ ] {Criterion 3 - performance meets Z}
4. [ ] {Criterion 4 - costs stay under budget}
5. [ ] {Criterion 5 - complete user journey works}

## Non-Functional Requirements

### Performance
- {Response time targets}
- {Throughput requirements}

### Security
- {Authentication requirements}
- {Data protection requirements}

### Reliability
- {Uptime targets}
- {Backup strategy}

### Scalability
- {Expected growth}
- {Scaling strategy}
