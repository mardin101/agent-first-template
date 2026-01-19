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
@workspace I want to brainstorm a new feature using the socratic method
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

Happy brainstorming! 🚀
