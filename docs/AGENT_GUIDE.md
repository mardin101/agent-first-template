# GitHub Copilot Agent Configuration Guide

This guide explains how to configure and use the custom agents in this repository.

## Overview

Custom agents are specialized AI assistants that help with specific development tasks. Each agent has a defined role, expertise area, and set of guidelines.

## Available Agents

### 1. Code Reviewer Agent
**File**: `.github/agents/code-reviewer.md`

**Purpose**: Reviews code for quality, security, and best practices

**When to Use**:
- Before submitting pull requests
- After making significant code changes
- When you want a second opinion on your implementation

**Example Usage**:
```
@workspace Use the code-reviewer agent to review my changes to the authentication module
```

### 2. Test Writer Agent
**File**: `.github/agents/test-writer.md`

**Purpose**: Creates comprehensive tests following best practices

**When to Use**:
- When adding new features that need tests
- To improve test coverage
- When refactoring existing tests

**Example Usage**:
```
@workspace Use the test-writer agent to create unit tests for the UserService class
```

### 3. Documentation Writer Agent
**File**: `.github/agents/documentation-writer.md`

**Purpose**: Creates clear, comprehensive documentation

**When to Use**:
- When documenting new features
- Updating API documentation
- Creating user guides or tutorials

**Example Usage**:
```
@workspace Use the documentation-writer agent to document the new API endpoints
```

### 4. Bug Fixer Agent
**File**: `.github/agents/bug-fixer.md`

**Purpose**: Identifies and fixes bugs systematically

**When to Use**:
- When debugging issues
- After receiving bug reports
- When tests are failing

**Example Usage**:
```
@workspace Use the bug-fixer agent to debug why the login function fails with empty passwords
```

## How Agents Work

### Agent Structure

Each agent file contains:

1. **Role Definition**: What the agent does
2. **Responsibilities**: Specific tasks the agent handles
3. **Guidelines**: Best practices and approaches
4. **Output Format**: How the agent structures responses

### Invoking Agents

To use an agent with GitHub Copilot:

1. Open Copilot Chat
2. Use `@workspace` to reference the workspace context
3. Mention the specific agent in your message
4. Provide clear context and requirements

### Best Practices

#### Be Specific
✅ Good: "Use the code-reviewer agent to review the error handling in src/auth.js"
❌ Bad: "Review my code"

#### Provide Context
Include:
- What you're working on
- What you need help with
- Any constraints or requirements
- Relevant file paths

#### Iterate
- Start with high-level requests
- Refine based on agent responses
- Break complex tasks into smaller steps

#### Review Agent Output
- Always review agent-generated code
- Test the changes
- Ensure it meets your requirements

## Creating Custom Agents

### Step 1: Create Agent File

Create a new markdown file in `.github/agents/`:

```bash
touch .github/agents/my-custom-agent.md
```

### Step 2: Define Agent Role

```markdown
# My Custom Agent

Brief description of what this agent does.

## Your Responsibilities

- List key responsibilities
- Define scope of work
```

### Step 3: Add Guidelines

```markdown
## Guidelines

1. Principle 1
2. Principle 2

## Best Practices

- Practice 1
- Practice 2
```

### Step 4: Specify Output Format

```markdown
## Output Format

Describe how the agent should structure its responses.
```

### Step 5: Test the Agent

1. Use the agent for its intended task
2. Refine the prompt based on results
3. Document usage examples

## Agent Templates

### General Purpose Agent Template

```markdown
# [Agent Name]

[Brief description of the agent's purpose and expertise]

## Your Responsibilities

- [Responsibility 1]
- [Responsibility 2]
- [Responsibility 3]

## [Category] Guidelines

1. **[Guideline 1]**: Description
2. **[Guideline 2]**: Description

## Approach

[Describe the agent's methodology]

## Output Format

[Specify expected output structure]

## Best Practices

- [Practice 1]
- [Practice 2]
```

## Troubleshooting

### Agent Not Responding as Expected

1. **Check Agent File**: Ensure the markdown file is properly formatted
2. **Be More Specific**: Provide clearer instructions
3. **Add Context**: Include relevant background information
4. **Iterate**: Refine your request based on responses

### Agent Output Quality Issues

1. **Refine Agent Guidelines**: Update the agent's markdown file
2. **Add Examples**: Include example outputs in the agent file
3. **Specify Constraints**: Be clear about requirements
4. **Test Iteratively**: Start with simple tasks, increase complexity

## Tips and Tricks

### Combining Agents

You can use multiple agents in sequence:

1. Use test-writer to create tests
2. Use code-reviewer to review the tests
3. Use documentation-writer to document the test suite

### Agent Workflows

Create workflows for common tasks:

**Feature Development Flow**:
1. Code reviewer: Review design approach
2. Test writer: Create tests for new feature
3. Code reviewer: Review implementation
4. Documentation writer: Document the feature

**Bug Fix Flow**:
1. Bug fixer: Identify and fix the issue
2. Test writer: Add regression tests
3. Code reviewer: Review the fix
4. Documentation writer: Update relevant docs

## Advanced Configuration

### Agent Context

Agents work best with:
- Clear project structure
- Well-organized code
- Existing documentation
- Good test coverage

### Performance Optimization

- Keep agent files focused and concise
- Use specific, actionable guidelines
- Provide examples in agent definitions
- Regular refine agent prompts based on usage

## Further Reading

- [GitHub Copilot Documentation](https://docs.github.com/en/copilot)
- [Prompt Engineering Best Practices](https://platform.openai.com/docs/guides/prompt-engineering)
- [AI-Assisted Development Guide](https://github.blog/developer-skills/)

---

Need help? Open an issue or check the main README for more information.
