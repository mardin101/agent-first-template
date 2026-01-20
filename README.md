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

### Code Implementation Agent 🔨

Use the code implementation agent to create comprehensive implementation plans for well-defined sub-issues with production-ready code guidance.

**Location**: `.github/agents/code-implementation.md`

**How to use**:
1. Invoke the code implementation agent with a sub-issue (typically from the decompose agent)
2. The agent analyzes the codebase for patterns and conventions
3. It checks for architecture/API documentation
4. The agent generates a detailed implementation plan with code examples

**What you'll get**:
- A comprehensive implementation plan with:
  - Context from architecture docs and existing codebase patterns
  - Acceptance criteria mapped to implementation tasks
  - Step-by-step implementation guidance with code examples
  - Files to create/modify with full paths
  - Code patterns to follow (error handling, logging, auth)
  - Edge cases and security considerations
  - Performance and accessibility guidance
  - Pre/post implementation checklists

**Example workflow**:
```
You: [Provide sub-issue with acceptance criteria]

Agent: [Analyzes codebase patterns and confirms understanding]

Agent: [Generates implementation plan with:]
- Database schema changes
- Service class implementation with code examples
- API integration guidance
- Error handling patterns
- Security considerations
- Testing suggestions

[Ready to implement or pass to autonomous coding agent]
```

**Example**: See `.github/agents/code-implementation-example.md` for a complete implementation planning session

### Test Generation Agent 🧪

Use the test generation agent to create comprehensive test coverage for implemented features, mapping acceptance criteria to test cases.

**Location**: `.github/agents/test-generation.md`

**How to use**:
1. Invoke the test generation agent after implementing a feature
2. The agent analyzes the implementation code
3. It detects the test framework and existing patterns
4. The agent generates comprehensive unit, integration, and E2E tests

**What you'll get**:
- Comprehensive test coverage with:
  - Acceptance criteria mapped to test cases
  - Unit tests for individual functions/methods
  - Integration tests for API endpoints
  - E2E tests for user workflows (when applicable)
  - Test fixtures and mock data
  - Edge case and error scenario coverage
  - Security and performance test guidance
  - Expected coverage report (>80%)

**Example workflow**:
```
You: [Provide implementation reference]

Agent: [Analyzes code and test framework]

Agent: [Generates test suite with:]
- Unit tests with proper mocking
- Integration tests with database setup
- E2E tests for critical paths
- Test coverage analysis
- Running instructions

[Ready to run tests and verify coverage]
```

**Example**: See `.github/agents/test-generation-example.md` for a complete test generation session

## Agent-First Development Workflow

This template supports a complete agent-driven development workflow:

```
1. Brainstorm → 2. Decompose → 3. Implement → 4. Test → 5. Review
   (brainstorm)    (decompose)    (code-impl)    (test-gen)  (human/agent)
```

**Step 1: Brainstorm** - Use the brainstorming agent to explore and refine feature ideas into comprehensive GitHub issues

**Step 2: Decompose** - Use the decomposition agent to break down the issue into actionable sub-issues with acceptance criteria

**Step 3: Implement** - Use the code implementation agent to create detailed implementation plans, then implement following the guidance (manually or with autonomous coding agents)

**Step 4: Test** - Use the test generation agent to create comprehensive test coverage that validates all acceptance criteria

**Step 5: Review** - Human review and merge, or use review agents

This workflow ensures features are well-thought-out, properly scoped, systematically implemented, thoroughly tested, and ready for production.

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
