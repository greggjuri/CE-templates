# CLAUDE.md - Claude Code Instructions

This file provides project-specific instructions and conventions for Claude Code.

## Project Overview

{PROJECT_NAME}: {Brief description}

**Tech Stack**: {Frontend} | {Backend} | {Database} | {IaC}

## Quick Commands

```bash
# Deploy backend
cd {infrastructure_dir} && {deploy_command}

# Start frontend dev server
cd {frontend_dir} && npm run dev

# Run backend tests
cd {backend_dir} && pytest --cov=. --cov-report=term-missing

# Run frontend tests
cd {frontend_dir} && npm test -- --coverage
```

## File Structure

```
{project-name}/
├── CLAUDE.md                    # This file
├── docs/
│   ├── PLANNING.md              # Architecture overview
│   ├── TASK.md                  # Current tasks
│   ├── DECISIONS.md             # ADRs
│   └── TESTING.md               # Testing standards
├── initials/                    # Feature specifications
├── prps/                        # Implementation plans
│   └── templates/
│       └── prp-template.md
├── .claude/
│   └── commands/
│       ├── generate-prp.md
│       └── execute-prp.md
├── examples/                    # Code patterns to follow
│   ├── {backend}/
│   ├── {infrastructure}/
│   └── {frontend}/
├── {infrastructure_dir}/        # IaC code
├── {backend_dir}/               # Backend code
└── {frontend_dir}/              # Frontend code
```

## Critical Rules

### 1. File Size Limit
- **Maximum 500 lines per file**
- When approaching limit: split into modules
- Prefer many small files over few large files

### 2. Commit Strategy
- **Commit after every feature** - atomic, working commits
- Use conventional commits: `feat:`, `fix:`, `refactor:`, `docs:`, `test:`
- Each commit should be deployable

### 3. Testing Requirements
- **Unit test coverage**: 80% minimum
- Run tests before committing
- Manual integration testing after deployment

### 4. Documentation
- Update `docs/TASK.md` when starting/completing tasks
- Create ADR in `docs/DECISIONS.md` for architectural choices
- Add learnings to relevant docs when debugging issues

## Coding Conventions

### Backend ({Language})

```{language}
# {Example pattern - customize for your stack}

# Use type hints everywhere
def function_name(param: str) -> dict:
    """Docstring explaining purpose."""
    pass

# Pydantic models for validation
class RequestModel(BaseModel):
    field: str = Field(..., description="Description")
    optional_field: int | None = None

# Error handling pattern
try:
    result = risky_operation()
except SpecificException as e:
    logger.error(f"Operation failed: {e}")
    raise HTTPException(status_code=400, detail=str(e))
```

### Frontend (TypeScript/React)

```typescript
// Functional components with hooks
const ComponentName: React.FC<Props> = ({ prop1, prop2 }) => {
  const [state, setState] = useState<Type>(initial);
  
  // Event handlers
  const handleAction = useCallback(() => {
    // Implementation
  }, [dependencies]);
  
  return (
    <div className="tailwind-classes">
      {/* JSX */}
    </div>
  );
};

// Custom hooks
const useCustomHook = (param: Type): ReturnType => {
  // Hook logic
  return value;
};
```

### Infrastructure ({Tool})

```{language}
# Naming convention: {pattern}
# Group related resources
# Use variables for repeated values
# Comment non-obvious configurations
```

## Error Handling Patterns

### Backend
- Log errors with context
- Return appropriate HTTP status codes
- Never expose internal errors to clients
- Use structured error responses

### Frontend
- Catch and display user-friendly errors
- Log errors for debugging
- Provide retry mechanisms where appropriate
- Show loading states during async operations

## API Design

### Request/Response Format
```json
{
  "field_name": "snake_case for JSON",
  "nested_object": {
    "child_field": "value"
  }
}
```

### Error Response Format
```json
{
  "error": "Brief error description",
  "detail": "More detailed explanation (optional)",
  "code": "ERROR_CODE (optional)"
}
```

## PRP Workflow

### Generating PRPs
```bash
/generate-prp initials/init-{feature}.md
```

This command:
1. Reads project documentation
2. Reads the init specification
3. Researches existing codebase
4. Generates comprehensive PRP
5. Scores confidence and lists concerns

### Executing PRPs
```bash
/execute-prp prps/prp-{feature}.md
```

This command:
1. Reads the PRP
2. Executes each step sequentially
3. Runs tests after each step
4. Reports progress
5. Handles errors gracefully

## Common Patterns

### Database Access
{Describe your database access patterns}

### Authentication
{Describe your auth patterns}

### State Management
{Describe your state management approach}

### Caching
{Describe your caching strategy}

## Cost Awareness (if applicable)

- Monitor API usage in responses
- Implement rate limiting where needed
- Log token/request counts
- Alert on unusual usage patterns

## Debugging Checklist

When something isn't working:

1. **Check logs**: {Where to find logs}
2. **Check browser console**: Network tab + Console tab
3. **Verify deployment**: {How to verify}
4. **Check configuration**: Environment variables, API URLs
5. **Review recent changes**: Git log, blame

## DO NOT

- Commit secrets or API keys
- Skip tests to save time
- Create files over 500 lines
- Contradict existing ADRs without discussion
- Deploy without testing

## Reference Documents

- `docs/PLANNING.md` - Architecture and data models
- `docs/DECISIONS.md` - Past decisions to respect
- `docs/TASK.md` - Current work status
- `docs/TESTING.md` - Testing standards
- `examples/` - Code patterns to follow
