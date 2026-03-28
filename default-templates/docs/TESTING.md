# {PROJECT_NAME} - Testing Standards

## Testing Pyramid

```
        /\
       /  \     Manual/E2E (few)
      /----\
     /      \   Integration (some)
    /--------\
   /          \ Unit (many)
  --------------
```

## When to Test What

| Test Type | When | Tools |
|-----------|------|-------|
| Unit | Every code change | {pytest/vitest/jest} |
| Integration | After deployment | Browser DevTools, curl |
| E2E | Before releases | Manual checklist |

## Automated Tests (CI)

```bash
# Backend
cd {backend_dir} && {test_command}

# Frontend
cd {frontend_dir} && npm test -- --coverage

# Infrastructure
cd {infrastructure_dir} && {test_command}
```

**Minimum Coverage**: 80%

## Manual Integration Testing

Required after every PRP execution that touches:
- API endpoints
- Frontend API calls
- Authentication/headers
- localStorage/state management
- External service integrations

### Setup
1. Deploy backend: `{deploy_command}`
2. Start frontend: `cd {frontend_dir} && npm run dev`
3. Open DevTools (F12)

### Checklist
- [ ] Console tab: No red errors
- [ ] Network tab: Requests succeed (2xx)
- [ ] Feature works end-to-end
- [ ] Error states handled gracefully
- [ ] Mobile/responsive works (if applicable)

### Common Bugs to Catch

| Bug | How to Detect | Fix Pattern |
|-----|---------------|-------------|
| CORS | Console shows CORS error | Add CORS config to API |
| Missing header | 401/403 response | Check required headers |
| URL malformed | 404 response | Check API_URL config |
| State not persisting | localStorage null | Check hook initialization |
| JS error blocking action | Nothing in Network tab | Check Console for errors |
| Async race condition | Intermittent failures | Add loading states |

## Testing Patterns

### Backend Unit Tests
```{language}
# Test file naming: test_{module}.py or {module}.test.ts

def test_function_does_expected_thing():
    # Arrange
    input_data = {...}
    
    # Act
    result = function_under_test(input_data)
    
    # Assert
    assert result == expected_output

def test_function_handles_error_case():
    # Test error conditions
    with pytest.raises(ExpectedException):
        function_under_test(invalid_input)
```

### Frontend Unit Tests
```typescript
// Test file naming: Component.test.tsx

describe('ComponentName', () => {
  it('renders correctly', () => {
    render(<ComponentName prop="value" />);
    expect(screen.getByText('expected text')).toBeInTheDocument();
  });

  it('handles user interaction', async () => {
    render(<ComponentName />);
    await userEvent.click(screen.getByRole('button'));
    expect(screen.getByText('result')).toBeInTheDocument();
  });
});
```

### Integration Test Pattern
```bash
# API test with curl
curl -X POST {API_URL}/endpoint \
  -H "Content-Type: application/json" \
  -H "X-User-Id: test-user" \
  -d '{"field": "value"}'

# Expected: 200 OK with response body
```

## Bug Report Template

```markdown
### Bug
[Brief description]

### Environment
- Browser: {Chrome/Firefox/Safari}
- URL: {Local/Production}
- User: {Test user ID if relevant}

### Steps to Reproduce
1. {Step 1}
2. {Step 2}
3. {Step 3}

### Expected
[What should happen]

### Actual
[What actually happened]

### Console Output
```
[Paste errors]
```

### Network Tab
[Request/response details]

### Screenshots
[If applicable]
```

## Test Data Management

### Test User IDs
- `test-user-001`: Basic test user
- `test-user-002`: User with specific state
- {Add more as needed}

### Cleanup
{Describe how to reset test data}

## Debugging Workflow

1. **Reproduce**: Confirm the bug exists
2. **Isolate**: Find the smallest reproduction
3. **Diagnose**: 
   - Check browser console
   - Check network requests/responses
   - Check server logs
   - Add debug logging if needed
4. **Fix**: Make minimal change
5. **Verify**: Confirm fix works
6. **Test**: Add test to prevent regression

## Lessons Learned

### {Feature Name}

| Bug | Root Cause | Prevention |
|-----|------------|------------|
| {Bug description} | {What caused it} | {How to prevent} |

{Add lessons as you encounter and fix bugs}

---

## Pre-Deployment Checklist

- [ ] All unit tests pass
- [ ] Test coverage meets minimum (80%)
- [ ] No linting errors
- [ ] Manual integration test completed
- [ ] Error scenarios tested
- [ ] Mobile/responsive tested (if applicable)
- [ ] Performance acceptable
