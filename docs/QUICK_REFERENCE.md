# Quick Reference Guide

Quick reference for working with this agent-first template.

## 🤖 Custom Agents

| Agent | Purpose | Use When |
|-------|---------|----------|
| **Code Reviewer** | Reviews code quality, security, performance | Before PRs, after changes |
| **Test Writer** | Creates comprehensive tests | Adding features, improving coverage |
| **Documentation Writer** | Creates clear documentation | Documenting APIs, writing guides |
| **Bug Fixer** | Debugs and fixes issues | Fixing bugs, troubleshooting |

## 📝 Quick Commands

### Using an Agent
```
@workspace Use the [agent-name] agent to [specific task]
```

### Examples
```
@workspace Use the code-reviewer agent to review src/auth.js
@workspace Use the test-writer agent to create tests for UserService
@workspace Use the documentation-writer agent to document the API
@workspace Use the bug-fixer agent to debug the login issue
```

## 📁 Directory Structure

```
.github/agents/     → Custom agent definitions
src/                → Source code
tests/              → Test files
docs/               → Documentation
.github/workflows/  → CI/CD workflows
```

## 🔄 Common Workflows

### Adding a Feature
1. Code Reviewer: Review design
2. Test Writer: Create tests
3. Code Reviewer: Review implementation
4. Documentation Writer: Document feature

### Fixing a Bug
1. Bug Fixer: Identify and fix
2. Test Writer: Add regression tests
3. Code Reviewer: Review fix
4. Documentation Writer: Update docs

### Refactoring
1. Test Writer: Create safety tests
2. Code Reviewer: Analyze before refactor
3. Code Reviewer: Review after refactor
4. Documentation Writer: Update docs

## 💡 Best Practices

- ✅ Be specific in your requests
- ✅ Provide file paths and context
- ✅ Review agent output before accepting
- ✅ Test agent-generated code
- ✅ Iterate in small steps

## 📚 Documentation

- [README.md](../README.md) - Main documentation
- [CONTRIBUTING.md](../CONTRIBUTING.md) - How to contribute
- [AGENT_GUIDE.md](./AGENT_GUIDE.md) - Detailed agent guide
- [AGENT_EXAMPLES.md](./AGENT_EXAMPLES.md) - Usage examples

## 🚀 Getting Started

1. Use this template to create a new repo
2. Clone your new repository
3. Start using agents with `@workspace`
4. Customize agents for your needs

## 🔗 Quick Links

- [GitHub Copilot Docs](https://docs.github.com/en/copilot)
- [GitHub Actions Docs](https://docs.github.com/en/actions)

---

**Need more details?** Check the full documentation in the links above.
