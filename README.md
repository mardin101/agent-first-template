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

### Feature Decomposition Agent

Use the decomposition agent to break down comprehensive GitHub issues into actionable sub-issues that can be assigned to developers or coding agents.

**Location**: `.github/agents/decompose.md`

**How to use**:
1. Invoke the decomposition agent with a GitHub issue (typically created by the brainstorm agent)
2. The agent will analyze the feature and confirm its understanding
3. It will explain its decomposition strategy
4. The agent will generate detailed sub-issues with acceptance criteria, dependencies, and implementation order

**What you'll get**:
- A complete decomposition with:
  - Analysis summary of the feature breakdown
  - Execution plan with recommended implementation order
  - Detailed sub-issues (typically 5-15) including:
    - Clear, action-oriented titles
    - Specific acceptance criteria (3-5 per issue)
    - Technical details and dependencies
    - Suggested labels and complexity estimates
    - Parent-child relationships
  - Critical path identification
  - Opportunities for parallel work

**Example workflow**:
```
You: [Provide GitHub issue URL or content]

Agent: [Analyzes and confirms understanding]

Agent: [Explains decomposition strategy]

Agent: [Generates 9 sub-issues organized into 5 phases]
- Phase 1: Infrastructure & Data
- Phase 2: Backend Services  
- Phase 3: Frontend Integration
- Phase 4: Integration & Polish
- Phase 5: Validation

[Each sub-issue includes full details ready for implementation]
```

**Example**: See `.github/agents/decompose-example.md` for a complete decomposition session

## Agent-First Development Workflow

This template supports a complete agent-driven development workflow:

```
1. Brainstorm → 2. Decompose → 3. Implement → 4. Review
   (brainstorm.md)  (decompose.md)  (coding agents)  (human/agent)
```

**Step 1: Brainstorm** - Use the brainstorming agent to explore and refine feature ideas into comprehensive GitHub issues

**Step 2: Decompose** - Use the decomposition agent to break down the issue into actionable sub-issues

**Step 3: Implement** - Assign sub-issues to coding agents or developers for implementation

**Step 4: Review** - Human review and merge, or use review agents

This workflow ensures features are well-thought-out, properly scoped, and ready for efficient implementation.

## Adding More Agents

To add additional agents to this template:

1. Create a new markdown file in `.github/agents/`
2. Define the agent's purpose, behavior, and output format
3. Update this README with usage instructions
4. Optionally create an example file showing the agent in action

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

MIT License - feel free to use this template for your projects.
