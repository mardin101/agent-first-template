# Agent-First Template

A template repository for agent-driven development with pre-configured agents to streamline feature development.

## Available Agents

### Feature Brainstorming Agent

Use the brainstorming agent to explore and refine new feature ideas through Socratic questioning.

**Location**: `.github/agents/brainstorm.md`

**How to use**:
1. Invoke the brainstorming agent through your GitHub Copilot interface
2. The agent will guide you through a structured brainstorming session
3. Answer questions one at a time - the agent will adapt to your responses
4. After 10-15 questions, the agent will create a GitHub issue ready for implementation

**What you'll get**:
- A well-structured GitHub issue with:
  - Clear problem statement
  - Proposed solution
  - User impact analysis
  - Success metrics
  - Technical considerations
  - MVP scope and future enhancements
  - Risk assessment

**Example conversation flow**:
```
Agent: What problem are you trying to solve with this new feature?
You: [Your answer]

Agent: Who experiences this problem most acutely?
You: [Your answer]

... (continues for 10-15 questions)

Agent: [Generates comprehensive GitHub issue]
```

## Adding More Agents

To add additional agents to this template:

1. Create a new markdown file in `.github/agents/`
2. Define the agent's purpose, behavior, and output format
3. Update this README with usage instructions

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

MIT License - feel free to use this template for your projects.
