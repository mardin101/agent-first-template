# Agent-First Template Repository

A template repository optimized for working with GitHub Copilot Agents, providing pre-configured custom agents and project scaffolding for efficient AI-assisted development.

## 🚀 Features

- **Custom Agent Library**: Pre-built agents for common development tasks
- **Project Scaffolding**: Standard directory structure and configuration files
- **GitHub Actions Ready**: Workflows optimized for agent collaboration
- **Best Practices**: Built-in conventions and guidelines

## 📁 Project Structure

```
.
├── .github/
│   ├── agents/           # Custom agent definitions
│   │   ├── code-reviewer.md
│   │   ├── test-writer.md
│   │   ├── documentation-writer.md
│   │   └── bug-fixer.md
│   └── workflows/        # GitHub Actions workflows
├── src/                  # Source code
├── tests/                # Test files
├── docs/                 # Documentation
├── README.md            # This file
├── CONTRIBUTING.md      # Contribution guidelines
└── .gitignore          # Git ignore patterns
```

## 🤖 Available Custom Agents

### Code Reviewer Agent
Expert code reviewer that analyzes changes for correctness, security, performance, and maintainability.

**Usage**: Ask the agent to "review my code changes" or "review this pull request"

### Test Writer Agent
Specialized in writing comprehensive, maintainable tests following best practices.

**Usage**: Ask the agent to "write tests for this function" or "add test coverage"

### Documentation Writer Agent
Technical writer that creates clear, comprehensive documentation for your project.

**Usage**: Ask the agent to "document this API" or "update the README"

### Bug Fixer Agent
Debugging specialist that identifies root causes and implements targeted fixes.

**Usage**: Ask the agent to "fix this bug" or "debug this issue"

## 🎯 Getting Started

### Using This Template

1. Click "Use this template" button on GitHub
2. Create a new repository from this template
3. Clone your new repository
4. Start developing with agent assistance!

### Working with Agents

To use a custom agent:

1. Open GitHub Copilot Chat
2. Reference the agent using `@workspace` and mention the specific agent
3. Provide context about what you need help with

Example:
```
@workspace Use the code-reviewer agent to review my recent changes
```

## 💡 Best Practices

### For Agent Collaboration

- **Be Specific**: Provide clear context and requirements
- **Iterate**: Work with agents in small, focused iterations
- **Review**: Always review agent-generated code
- **Test**: Validate agent changes with tests
- **Document**: Keep documentation updated as code evolves

### Project Organization

- Keep source code in `src/`
- Place tests alongside code or in `tests/`
- Store documentation in `docs/`
- Use meaningful file and directory names
- Follow consistent naming conventions

## 🛠️ Customization

### Adding New Agents

1. Create a new `.md` file in `.github/agents/`
2. Define the agent's role, responsibilities, and guidelines
3. Include examples and best practices
4. Update this README to document the new agent

### Modifying Project Structure

This template provides a basic structure. Customize it based on your needs:

- Add language-specific configurations (package.json, requirements.txt, etc.)
- Include build tools and scripts
- Add CI/CD pipelines
- Configure linters and formatters

## 📝 Contributing

We welcome contributions! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## 📄 License

This template is provided as-is for you to use in your projects. Modify and distribute freely.

## 🤝 Support

- Report issues on GitHub
- Suggest improvements via pull requests
- Share your custom agents with the community

## 🎓 Learn More

- [GitHub Copilot Documentation](https://docs.github.com/en/copilot)
- [GitHub Actions Documentation](https://docs.github.com/en/actions)
- [Best Practices for AI-Assisted Development](https://github.blog/developer-skills/)

---

**Happy coding with AI assistance! 🚀**
