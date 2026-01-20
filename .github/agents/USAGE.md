# Using the Agent-First Template

## Overview

This template provides two complementary agents for feature development:

1. **Brainstorming Agent** - Helps you explore and refine feature ideas
2. **Decomposition Agent** - Breaks down features into actionable sub-issues

Together, they enable a complete agent-first development workflow: **Brainstorm → Decompose → Implement**

---

# Using the Brainstorming Agent

## Quick Start

The Brainstorming Agent is designed to be invoked through GitHub Copilot's agent interface. Here's how to use it:

### Step 1: Invoke the Agent

Use the GitHub Copilot interface to invoke the brainstorming agent. You can typically do this by:

- Opening GitHub Copilot chat
- Referencing the agent file: `.github/agents/brainstorm.md`
- Starting with a prompt like: "I want to brainstorm a new feature"

### Step 2: Answer Questions One at a Time

The agent will guide you through a series of questions. Take your time with each answer:

- The agent asks questions about problem, solution, impact, technical details, and scope
- Answer thoughtfully - your responses will shape the final issue
- The agent adapts to your answers and may ask follow-up questions
- Be specific but don't worry about perfect formatting

### Step 3: Review and Create the Issue

After 10-15 questions, the agent will:

1. Summarize your brainstorming session
2. Generate a comprehensive GitHub issue
3. Present the issue in a formatted code block
4. The issue is ready to be copied and submitted to your repository

## What to Prepare

Before starting your brainstorming session, have a rough idea of:

- **The problem** you're trying to solve
- **Who** is affected by this problem
- **Why** this matters to your users or business

You don't need detailed answers - the agent will help you explore and refine these ideas!

## Tips for a Great Brainstorming Session

1. **Be honest**: Share what you know and don't know
2. **Think about users**: Focus on real user problems
3. **Consider constraints**: Technical limitations, time, resources
4. **Start broad**: Let the agent help you narrow down
5. **Stay engaged**: Each question builds on the previous ones

## What You'll Get

A production-ready GitHub issue with:

- ✅ Clear problem statement
- ✅ Well-defined solution
- ✅ User impact analysis
- ✅ Measurable success metrics
- ✅ Technical considerations
- ✅ MVP scope definition
- ✅ Future enhancement ideas
- ✅ Risk assessment
- ✅ Proper labels and priority

This issue can be immediately:
- Assigned to team members
- Prioritized in sprint planning
- Broken down into tasks
- Picked up by implementation agents

## Example Commands

Depending on your GitHub Copilot setup, you might invoke the agent like:

```
@workspace I want to brainstorm a new feature using the Socratic method
```

or

```
Use .github/agents/brainstorm.md to help me brainstorm a feature
```

or simply:

```
I need to brainstorm a new feature idea
```

The agent will recognize your intent and start the questioning process.

## Need Help?

- See `.github/agents/brainstorm-example.md` for a complete example session
- Read the agent configuration in `.github/agents/brainstorm.md` to understand its behavior
- Check the README.md for additional documentation

---

# Using the Decomposition Agent

## Quick Start

The Decomposition Agent takes comprehensive GitHub issues (like those created by the brainstorming agent) and breaks them down into actionable sub-issues ready for implementation.

### Step 1: Prepare Your Feature Issue

You'll need a comprehensive GitHub issue with:
- Problem statement and solution
- Technical considerations
- Scope definition (MVP and future work)

The brainstorming agent creates perfectly formatted issues for decomposition!

### Step 2: Invoke the Decomposition Agent

Use the GitHub Copilot interface to invoke the decomposition agent:

- Open GitHub Copilot chat
- Reference the agent file: `.github/agents/decompose.md`
- Provide the GitHub issue URL or paste the full issue content

### Step 3: Review the Analysis

The agent will:
1. **Analyze the issue** and present its understanding
2. **Explain the decomposition strategy** (e.g., layer-based, component-based)
3. **Ask for confirmation** before proceeding

This ensures the agent understands your feature correctly.

### Step 4: Review the Decomposition

The agent will generate:

1. **Analysis Summary** - How it approached the breakdown
2. **Execution Plan** - Recommended implementation order with phases
3. **Detailed Sub-Issues** - Each with:
   - Clear title and description
   - 3-5 specific acceptance criteria
   - Technical details and dependencies
   - Suggested labels and complexity
   - Parent-child relationships

### Step 5: Iterate and Refine

Review the sub-issues and:
- Request adjustments to scope, order, or details
- Ask for more sub-issues to break down complex tasks further
- Merge sub-issues that are too granular

The agent will adapt based on your feedback.

### Step 6: Create GitHub Issues

Once approved, use the generated sub-issues to:
- Create them manually in GitHub
- Use GitHub API or CLI to automate creation
- Copy to your project management tool

## What to Prepare

Before starting a decomposition session, have:

- **A comprehensive feature issue** with clear problem statement and solution
- **Understanding of your architecture** (helps validate the decomposition)
- **Knowledge of your team's capacity** (helps assess if scope is appropriate)

## Tips for Effective Decomposition

1. **Start with brainstorm output**: Issues from the brainstorming agent work perfectly
2. **Provide context**: Share relevant technical details the agent might not know
3. **Review dependencies carefully**: Ensure the implementation order makes sense
4. **Consider your team**: Adjust complexity based on your team's expertise
5. **Think parallel**: Identify which sub-issues can be worked on simultaneously
6. **Plan for testing**: Ensure testing and documentation sub-issues are included

## What You'll Get

A complete feature breakdown with:

- ✅ **5-15 sub-issues** (typical range, varies by feature complexity)
- ✅ **Implementation phases** clearly defined
- ✅ **Acceptance criteria** specific and testable (3-5 per sub-issue)
- ✅ **Dependencies mapped** showing what blocks what
- ✅ **Parallel work identified** to optimize team velocity
- ✅ **Technical details** sufficient for implementation
- ✅ **Estimated complexity** to help with sprint planning
- ✅ **Proper labels** for categorization and filtering

## Integration with Brainstorming Agent

The decomposition agent is designed to work seamlessly with the brainstorming agent:

```
Brainstorming Agent Output (GitHub Issue)
           ↓
    [Copy or link to issue]
           ↓
   Decomposition Agent Input
           ↓
Decomposition Agent Output (Sub-Issues)
           ↓
   [Assign to developers/agents]
           ↓
      Implementation
```

**Complete workflow example**:

1. **Brainstorm session** → Generates "Smart Error Documentation Assistant" issue
2. **Decompose session** → Breaks into 9 sub-issues across 5 phases
3. **Implementation** → Teams pick up sub-issues in priority order
4. **Integration** → Sub-issues come together to complete the feature

## Example Commands

Depending on your GitHub Copilot setup, you might invoke the agent like:

```
@workspace Decompose this GitHub issue into sub-issues
```

or

```
Use .github/agents/decompose.md to break down this feature: [paste issue]
```

or simply:

```
I need to break down this feature into implementation tasks: [paste issue URL]
```

The agent will recognize your intent and start the decomposition process.

## Best Practices

### For Complex Features (10+ sub-issues)
- Request clear phases (e.g., "Infrastructure", "Backend", "Frontend")
- Ask for a dependency diagram if relationships are complex
- Consider breaking into multiple rounds (MVP first, then enhancements)

### For Simple Features (3-5 sub-issues)
- Still worth decomposing for clarity
- Focus on testability and clear acceptance criteria
- May not need complex dependency tracking

### For Technical Debt or Refactoring
- Emphasize risk mitigation and incremental changes
- Request sub-issues that maintain functionality while improving code
- Include testing sub-issues to prevent regressions

### For Cross-Cutting Features
- Highlight integration points clearly
- Create dedicated integration sub-issues
- Map dependencies across system boundaries

## Reviewing Generated Sub-Issues

When reviewing the decomposition, check:

- [ ] **Completeness**: Does it cover all aspects of the parent issue?
- [ ] **Independence**: Can most sub-issues be worked on separately?
- [ ] **Testability**: Does each have clear acceptance criteria?
- [ ] **Scope**: Are sub-issues appropriately sized (1-3 days)?
- [ ] **Order**: Does the implementation sequence make sense?
- [ ] **Dependencies**: Are blocking relationships logical and necessary?
- [ ] **Coverage**: Are testing, documentation, and error handling included?

## Adjusting the Decomposition

Common adjustment requests:

**"Break down sub-issue #3 further"** - For complex sub-issues that need more granularity

**"Merge sub-issues #5 and #6"** - When tasks are too granular

**"Add a spike for researching the API integration"** - For uncertain areas

**"Reorder sub-issues to do frontend first"** - When implementation strategy needs to change

**"Add more testing sub-issues"** - To increase quality focus

## Advanced Usage

### Using with Coding Agents

Sub-issues generated by the decomposition agent are designed to be:
- **Self-contained**: Coding agents can implement without additional context
- **Well-specified**: Clear acceptance criteria guide implementation
- **Testable**: Agents can verify their work against criteria

### Using for Sprint Planning

The decomposition helps with:
- **Estimation**: Complexity levels guide story points
- **Prioritization**: Implementation order suggests sprint sequence
- **Velocity planning**: Parallel work opportunities maximize throughput
- **Risk management**: Dependencies highlight critical path

### Using for Onboarding

New team members can:
- **Understand feature scope**: Parent issue + sub-issues show big picture
- **Pick appropriate tasks**: Complexity levels help match skills
- **Learn the codebase**: Sub-issues guide through system components
- **Make progress quickly**: Clear acceptance criteria reduce ambiguity

## Need Help?

- See `.github/agents/decompose-example.md` for a complete example decomposition
- Read the agent configuration in `.github/agents/decompose.md` to understand its behavior  
- Check the README.md for the complete agent-first workflow
- Try the brainstorming agent first if you don't have a comprehensive issue yet

Happy decomposing! 🚀
