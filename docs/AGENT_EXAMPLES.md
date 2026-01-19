# Agent Usage Examples

This document provides practical examples of using the custom agents in this repository.

## Quick Start Examples

### Example 1: Code Review Request

**Scenario**: You've just completed a new authentication feature and want it reviewed.

**Command**:
```
@workspace Use the code-reviewer agent to review the authentication implementation in src/auth.js. 
Focus on security vulnerabilities and error handling.
```

**Expected Output**:
- Security analysis of authentication logic
- Error handling assessment
- Suggestions for improvements
- Potential edge cases to handle

---

### Example 2: Writing Unit Tests

**Scenario**: You need comprehensive tests for a new user service class.

**Command**:
```
@workspace Use the test-writer agent to create unit tests for the UserService class in src/services/user-service.js. 
Include tests for creating users, updating profiles, and error conditions.
```

**Expected Output**:
- Test suite with multiple test cases
- Tests for happy path scenarios
- Tests for edge cases and errors
- Proper test setup and teardown

---

### Example 3: API Documentation

**Scenario**: You've added new REST API endpoints that need documentation.

**Command**:
```
@workspace Use the documentation-writer agent to create API documentation for the endpoints in src/routes/api.js. 
Include request/response formats, authentication requirements, and usage examples.
```

**Expected Output**:
- Clear API endpoint descriptions
- Request/response examples
- Authentication requirements
- Error codes and handling

---

### Example 4: Bug Investigation

**Scenario**: Users report that the search function returns incorrect results.

**Command**:
```
@workspace Use the bug-fixer agent to investigate why the search function in src/search.js 
returns incorrect results when the query contains special characters.
```

**Expected Output**:
- Root cause analysis
- Fix implementation
- Test to prevent regression
- Explanation of the issue

---

## Real-World Workflows

### Workflow 1: Adding a New Feature

**Step 1: Design Review**
```
@workspace Use the code-reviewer agent to review my design for the new notification system. 
Here's my approach: [describe your design]
```

**Step 2: Test Planning**
```
@workspace Use the test-writer agent to suggest test cases for the notification system 
that will handle real-time alerts and email notifications.
```

**Step 3: Implementation Review**
```
@workspace Use the code-reviewer agent to review the notification system implementation 
in src/notifications/. Focus on performance and scalability.
```

**Step 4: Documentation**
```
@workspace Use the documentation-writer agent to create user documentation 
for the notification system, including setup and configuration.
```

---

### Workflow 2: Fixing a Complex Bug

**Step 1: Bug Analysis**
```
@workspace Use the bug-fixer agent to debug why the payment processing 
fails intermittently. Error logs show: [paste error logs]
```

**Step 2: Create Regression Test**
```
@workspace Use the test-writer agent to create a test that reproduces 
the intermittent payment processing failure.
```

**Step 3: Review Fix**
```
@workspace Use the code-reviewer agent to review the payment processing fix. 
Ensure it handles race conditions and maintains transaction integrity.
```

**Step 4: Update Documentation**
```
@workspace Use the documentation-writer agent to document the payment processing 
fix and any new error handling in the user guide.
```

---

### Workflow 3: Refactoring Legacy Code

**Step 1: Initial Review**
```
@workspace Use the code-reviewer agent to analyze src/legacy/old-module.js 
and suggest refactoring opportunities for better maintainability.
```

**Step 2: Test Coverage**
```
@workspace Use the test-writer agent to create comprehensive tests for the legacy 
module before refactoring. Cover all current functionality.
```

**Step 3: Implementation Review**
```
@workspace Use the code-reviewer agent to review the refactored code. 
Ensure backward compatibility and improved code quality.
```

**Step 4: Documentation Update**
```
@workspace Use the documentation-writer agent to update the module documentation 
to reflect the new architecture and improved APIs.
```

---

## Advanced Usage Patterns

### Pattern 1: Iterative Improvement

Start broad, then narrow down:

```
1. @workspace Use the code-reviewer agent to review src/api/
2. [Review results]
3. @workspace Use the code-reviewer agent to focus on error handling in src/api/routes.js
4. [Implement suggestions]
5. @workspace Use the code-reviewer agent to verify the error handling improvements
```

### Pattern 2: Multi-Agent Collaboration

Use multiple agents in sequence:

```
1. Test-Writer: Create tests for new feature
2. Code-Reviewer: Review test quality
3. [Implement feature]
4. Code-Reviewer: Review implementation
5. Documentation-Writer: Document the feature
```

### Pattern 3: Preventive Analysis

Before making changes:

```
@workspace Use the code-reviewer agent to analyze src/critical-module.js 
before I make changes. Identify any fragile areas or dependencies I should be aware of.
```

---

## Tips for Better Results

### 1. Provide Context

**Bad**:
```
@workspace Review this
```

**Good**:
```
@workspace Use the code-reviewer agent to review the error handling in src/auth/login.js. 
I'm concerned about security and proper validation of user input.
```

### 2. Be Specific About Scope

**Bad**:
```
@workspace Document everything
```

**Good**:
```
@workspace Use the documentation-writer agent to create getting started documentation 
for new contributors, covering setup, development workflow, and testing.
```

### 3. Mention Constraints

**Include**:
- Performance requirements
- Security considerations
- Compatibility requirements
- Coding standards

**Example**:
```
@workspace Use the test-writer agent to create tests for the payment module. 
Tests must complete in under 100ms and not require external services.
```

### 4. Reference Files Explicitly

**Include**:
- Full file paths
- Specific functions or classes
- Line numbers if relevant

**Example**:
```
@workspace Use the bug-fixer agent to fix the memory leak in src/services/cache.js, 
specifically in the CacheManager.cleanup() method around lines 45-60.
```

---

## Common Scenarios

### Scenario: New Team Member Onboarding

```
@workspace Use the documentation-writer agent to create an onboarding guide 
for new developers, including project structure, development setup, and key concepts.
```

### Scenario: Performance Optimization

```
@workspace Use the code-reviewer agent to analyze src/data/processor.js 
for performance issues. The function processes large datasets and is currently slow.
```

### Scenario: Security Audit

```
@workspace Use the code-reviewer agent to perform a security review of src/api/ 
focusing on authentication, authorization, and input validation.
```

### Scenario: Test Coverage Improvement

```
@workspace Use the test-writer agent to improve test coverage for src/utils/. 
Current coverage is 60%, target is 90%. Focus on edge cases and error conditions.
```

### Scenario: Legacy Code Understanding

```
@workspace Use the documentation-writer agent to document what src/legacy/processor.js does. 
The code has no comments and the original author is no longer available.
```

---

## Troubleshooting

### Agent Not Understanding Context

**Problem**: Agent gives generic responses

**Solution**: 
- Provide more specific context
- Reference exact files and functions
- Describe what you're trying to achieve
- Include relevant code snippets

### Agent Output Too Broad

**Problem**: Agent provides too much information

**Solution**:
- Narrow your request scope
- Focus on one aspect at a time
- Specify exact requirements
- Break complex requests into smaller parts

### Agent Suggestions Not Helpful

**Problem**: Suggestions don't apply to your situation

**Solution**:
- Explain your constraints
- Mention what you've already tried
- Describe your specific use case
- Provide examples of what you need

---

## Resources

- [Main README](../README.md) - Project overview
- [Agent Guide](./AGENT_GUIDE.md) - Detailed agent configuration
- [Contributing](../CONTRIBUTING.md) - Contribution guidelines

---

**Ready to start?** Try one of the examples above with your own code!
