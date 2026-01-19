# Contributing to Agent-First Template

Thank you for your interest in contributing! This document provides guidelines for contributing to this project.

## 🎯 How to Contribute

### Reporting Issues

- Check if the issue already exists
- Use a clear, descriptive title
- Provide detailed information about the problem
- Include steps to reproduce if applicable

### Suggesting Enhancements

- Describe the enhancement clearly
- Explain why it would be useful
- Provide examples if possible

### Contributing Code

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Make your changes
4. Test your changes thoroughly
5. Commit your changes (`git commit -m 'Add amazing feature'`)
6. Push to the branch (`git push origin feature/amazing-feature`)
7. Open a Pull Request

## 📋 Pull Request Guidelines

### Before Submitting

- Ensure your code follows the project's style
- Update documentation if needed
- Add tests for new functionality
- Make sure all tests pass
- Keep changes focused and minimal

### PR Description

Include:
- **Purpose**: What does this PR do?
- **Changes**: What files/components were modified?
- **Testing**: How was this tested?
- **Notes**: Any additional context or considerations

## 🤖 Working with Agents

This project is optimized for GitHub Copilot Agents. When contributing:

### Using Custom Agents

- Leverage existing custom agents for tasks they're designed for
- Test agent-generated code thoroughly
- Review all agent suggestions before accepting
- Document any agent collaboration in your PR

### Adding New Agents

When adding a new custom agent:

1. **Create Agent File**: Add `.md` file in `.github/agents/`
2. **Define Clearly**: Specify role, responsibilities, and guidelines
3. **Provide Examples**: Include usage examples
4. **Document**: Update README.md with agent information
5. **Test**: Verify the agent works as intended

#### Agent File Structure

```markdown
# Agent Name

Brief description of the agent's purpose.

## Your Responsibilities

- List of what the agent should do
- Key areas of focus

## Guidelines

- How the agent should approach tasks
- Best practices to follow

## Output Format

- Expected format of agent responses
```

## 🎨 Code Style

### General Principles

- Write clear, readable code
- Use meaningful variable and function names
- Keep functions small and focused
- Comment complex logic
- Follow existing patterns in the codebase

### File Organization

- Place source code in `src/`
- Place tests in `tests/` or alongside source files
- Place documentation in `docs/`
- Keep related files together

## ✅ Testing

- Write tests for new functionality
- Ensure existing tests pass
- Test edge cases and error conditions
- Use descriptive test names

## 📝 Documentation

### Code Documentation

- Document public APIs
- Explain complex algorithms
- Include usage examples
- Keep comments up-to-date

### Project Documentation

- Update README.md for significant changes
- Add guides for new features
- Document configuration options
- Include migration guides for breaking changes

## 🔍 Review Process

### What We Look For

- **Correctness**: Does it work as intended?
- **Quality**: Is the code clean and maintainable?
- **Testing**: Are there adequate tests?
- **Documentation**: Are changes documented?
- **Impact**: Does it align with project goals?

### Review Timeline

- Most PRs are reviewed within 1-3 days
- Complex changes may take longer
- Feel free to ping if no response after a week

## 🌟 Recognition

Contributors are recognized in:
- GitHub contributors page
- Release notes for significant contributions
- Project documentation

## 💬 Communication

### Getting Help

- Open an issue for questions
- Use discussions for broader topics
- Tag maintainers for urgent matters

### Being Respectful

- Be kind and constructive
- Assume good intentions
- Focus on ideas, not people
- Help create a welcoming environment

## 📜 Code of Conduct

- Be respectful and inclusive
- Welcome newcomers
- Focus on constructive feedback
- Maintain a professional environment

## 🚀 Quick Checklist

Before submitting a PR:

- [ ] Code follows project style
- [ ] Tests added/updated
- [ ] Documentation updated
- [ ] All tests pass
- [ ] Commits are clear and descriptive
- [ ] PR description is complete

## 🙏 Thank You

Your contributions make this project better. We appreciate your time and effort!

---

Questions? Open an issue or start a discussion. Happy contributing! 🎉
