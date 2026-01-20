# Using the Agent-First Template

## Overview

This template provides four complementary agents for the complete feature development lifecycle:

1. **Brainstorming Agent** - Helps you explore and refine feature ideas
2. **Decomposition Agent** - Breaks down features into actionable sub-issues
3. **Code Implementation Agent** 🔨 - Creates comprehensive implementation plans with code guidance
4. **Test Generation Agent** 🧪 - Generates comprehensive test coverage

Together, they enable a complete agent-first development workflow: **Brainstorm → Decompose → Implement → Test → Review**

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

---

# Using the Code Implementation Agent 🔨

## Quick Start

The Code Implementation Agent creates comprehensive implementation plans for well-defined sub-issues, providing step-by-step guidance with code examples.

### Step 1: Prepare Your Sub-Issue

You'll need a well-defined sub-issue with:
- Clear description and scope
- Specific acceptance criteria (3-5 criteria)
- Technical details (files, dependencies)
- Reference to parent issue

The decomposition agent creates perfectly formatted sub-issues for implementation!

### Step 2: Invoke the Code Implementation Agent

Use the GitHub Copilot interface to invoke the agent:

- Open GitHub Copilot chat
- Reference the agent file: `.github/agents/code-implementation.md`
- Provide the sub-issue content or URL

### Step 3: Context Gathering

The agent will:
1. **Analyze the sub-issue** and acceptance criteria
2. **Scan the codebase** for existing patterns and conventions
3. **Check for architecture/API docs** to follow
4. **Present its understanding** and ask for confirmation

This ensures the agent understands your requirements and environment correctly.

### Step 4: Review the Implementation Plan

The agent will generate:

1. **Context Summary** - Understanding of requirements and available resources
2. **Acceptance Criteria Mapping** - Each criterion mapped to implementation approach
3. **Files to Create/Modify** - Complete file paths and purposes
4. **Implementation Steps** - Step-by-step guidance with actual code examples
5. **Code Patterns to Follow** - Examples from your existing codebase
6. **Edge Cases** - Identified edge cases and handling approaches
7. **Quality Considerations** - Security, performance, accessibility guidance
8. **Checklists** - Pre/during/post implementation validation

### Step 5: Implement or Iterate

- Review the plan and request adjustments if needed
- Implement following the step-by-step guidance
- Use code examples as templates
- Verify against checklists
- Invoke Test Generation Agent when complete

## What to Prepare

Before starting an implementation session, have:

- **A well-defined sub-issue** with clear acceptance criteria
- **Understanding of your codebase** (or let the agent scan it)
- **Architecture/API docs** if available (agent will check)
- **Development environment** set up and ready

## Tips for Effective Implementation Planning

1. **Provide context**: Share any additional context the agent might not find
2. **Review patterns carefully**: Ensure suggested patterns fit your use case
3. **Validate file paths**: Confirm file organization matches your project structure
4. **Consider security first**: Pay attention to security guidance
5. **Plan for testing**: Implementation should be testable
6. **Iterate if needed**: Ask for adjustments to scope or approach

## What You'll Get

A production-ready implementation plan with:

- ✅ **Context-aware guidance** - Uses your project's patterns and conventions
- ✅ **Step-by-step instructions** - Clear, sequential implementation steps
- ✅ **Actual code examples** - Real code, not pseudocode
- ✅ **Pattern references** - Points to existing code to follow
- ✅ **Quality considerations** - Security, performance, accessibility
- ✅ **Edge case handling** - Identified and addressed
- ✅ **Testing guidance** - Ready for Test Generation Agent
- ✅ **Validation checklists** - Ensure nothing is missed

## Implementation Modes

The agent supports multiple modes:

### Guided Mode (Default)
- Detailed plan for human developers
- Explanations of why, not just what
- Learning opportunity in guidance
- Step-by-step walkthrough

### Autonomous Mode
- Works with GitHub Copilot Workspace
- More prescriptive instructions
- Complete code examples
- Can be used by AI to implement directly

### Review Mode
- Reviews existing implementation
- Compares against original plan
- Identifies gaps or deviations
- Suggests improvements

## Integration with Other Agents

**From Decomposition Agent**:
- Receives sub-issues with acceptance criteria
- Builds on parent issue context
- Follows implementation order

**To Test Generation Agent**:
- Implementation plan feeds into test planning
- Acceptance criteria map to test cases
- Code patterns inform test structure

**From Architecture Agent** (if available):
- Follows architectural decisions
- Respects design constraints
- Implements according to patterns

## Example Commands

Depending on your GitHub Copilot setup, you might invoke the agent like:

```
@workspace Create an implementation plan for this sub-issue
```

or

```
Use .github/agents/code-implementation.md to plan implementation for: [paste sub-issue]
```

or simply:

```
I need to implement sub-issue #105, help me create an implementation plan
```

The agent will recognize your intent and start the planning process.

## Best Practices

### For Backend Features
- Emphasize database schema and migrations
- Focus on API design and error handling
- Consider performance and scalability
- Include authentication/authorization

### For Frontend Features
- Focus on component structure and reusability
- Emphasize accessibility (WCAG compliance)
- Consider responsive design
- Include state management patterns

### For Full-Stack Features
- Plan backend first, then frontend
- Define API contracts clearly
- Consider data flow and state management
- Plan integration points carefully

### For Refactoring Tasks
- Identify current patterns to improve
- Plan incremental changes
- Ensure backward compatibility
- Include migration strategy

## Reviewing Generated Implementation Plans

When reviewing the plan, check:

- [ ] **Completeness**: Does it cover all acceptance criteria?
- [ ] **Accuracy**: Do file paths and patterns match your project?
- [ ] **Clarity**: Are steps clear and actionable?
- [ ] **Quality**: Are security/performance/accessibility addressed?
- [ ] **Testability**: Can implementation be tested?
- [ ] **Dependencies**: Are new dependencies justified?
- [ ] **Edge cases**: Are edge cases identified and handled?

## Common Adjustments

Frequently requested adjustments:

**"Add more code examples"** - For complex implementation steps

**"Simplify the approach"** - When suggested solution is over-engineered

**"Add database indexing strategy"** - For performance-critical queries

**"Include more security validation"** - For user-facing features

**"Adjust file organization"** - To match project structure better

**"Add migration rollback plan"** - For database changes

## Need Help?

- See `.github/agents/code-implementation-example.md` for a complete example session
- Read the agent configuration in `.github/agents/code-implementation.md` to understand its behavior
- Check the README.md for the complete agent-first workflow
- Use the decomposition agent first to create well-defined sub-issues

---

# Using the Test Generation Agent 🧪

## Quick Start

The Test Generation Agent creates comprehensive test coverage for implemented features, mapping acceptance criteria to test cases.

### Step 1: Complete Implementation

You'll need:
- Implemented code (following Code Implementation Agent's plan or manual implementation)
- Sub-issue with acceptance criteria
- Working code that compiles/runs

Implementation should be complete before generating tests!

### Step 2: Invoke the Test Generation Agent

Use the GitHub Copilot interface to invoke the agent:

- Open GitHub Copilot chat
- Reference the agent file: `.github/agents/test-generation.md`
- Provide implementation reference (file paths, PR, sub-issue)

### Step 3: Analysis

The agent will:
1. **Analyze the implementation** code
2. **Detect the test framework** (Jest, Vitest, Pytest, RSpec, etc.)
3. **Identify test patterns** in your project
4. **Plan test coverage** - types and count of tests needed
5. **Present the test plan** and ask for confirmation

This ensures comprehensive coverage is planned before generating tests.

### Step 4: Review the Test Suite

The agent will generate:

1. **Test Coverage Analysis** - Mapping of acceptance criteria to tests
2. **Unit Tests** - Testing individual functions/methods
3. **Integration Tests** - Testing component interactions (API, database)
4. **E2E Tests** - Testing complete user workflows (when applicable)
5. **Test Fixtures** - Reusable test data and helpers
6. **Coverage Report** - Expected coverage percentages
7. **Running Instructions** - Commands to run and validate tests

### Step 5: Run and Validate

- Copy tests into your project
- Run tests to verify they pass
- Check coverage meets threshold (>80%)
- Fix any failing tests or implementation issues
- Commit tests with implementation

## What to Prepare

Before starting a test generation session, have:

- **Completed implementation** - Code that works
- **Acceptance criteria** - To map to test cases
- **Test framework** - Installed and configured (agent will detect)
- **Understanding of edge cases** - To ensure comprehensive coverage

## Tips for Effective Test Generation

1. **Complete implementation first**: Don't generate tests for partial code
2. **Provide acceptance criteria**: Tests should validate requirements
3. **Run tests immediately**: Verify generated tests work
4. **Check coverage**: Ensure >80% coverage achieved
5. **Fix flaky tests**: Ensure tests are deterministic
6. **Add missing tests**: Supplement with additional edge cases if needed

## What You'll Get

A comprehensive test suite with:

- ✅ **Acceptance criteria coverage** - Every criterion validated
- ✅ **Multiple test types** - Unit, integration, E2E as appropriate
- ✅ **Edge case tests** - Identified and tested
- ✅ **Error scenario tests** - Validation errors, failures
- ✅ **Security tests** - Authentication, authorization, input validation
- ✅ **Framework-aware** - Uses your project's test framework and conventions
- ✅ **High coverage** - Typically >80%, often >90%
- ✅ **Clear structure** - Organized, well-named tests
- ✅ **Running instructions** - How to run and validate

## Test Types Generated

### Unit Tests
- Test individual functions/methods in isolation
- Mock external dependencies (database, APIs)
- Test all branches and conditions
- Validate return values and side effects
- Test error handling

### Integration Tests
- Test component interactions
- API endpoints end-to-end
- Database operations
- Authentication/authorization
- Real dependencies (not mocked)

### E2E Tests
- Complete user workflows
- UI interactions (if applicable)
- Cross-system integration
- Critical user paths

## Coverage Focus

The agent ensures:

- **Happy path**: Normal, expected operation
- **Error paths**: Invalid inputs, failures
- **Edge cases**: Boundary conditions, unusual inputs
- **Security**: Auth, validation, injection prevention
- **Performance**: Pagination, caching (tested indirectly)

## Test Quality Standards

Generated tests follow best practices:

- **Independent**: No shared state between tests
- **Repeatable**: Same result every time
- **Clear descriptions**: Given-When-Then format
- **Proper mocking**: External dependencies isolated
- **Fast execution**: No unnecessary delays
- **Comprehensive assertions**: Validate all important behavior

## Integration with Other Agents

**From Code Implementation Agent**:
- Uses acceptance criteria mapping
- Follows identified code patterns
- Tests implementation approach

**To Code Review**:
- Tests validate acceptance criteria
- Coverage demonstrates completeness
- Tests serve as documentation

## Example Commands

Depending on your GitHub Copilot setup, you might invoke the agent like:

```
@workspace Generate tests for the notification service implementation
```

or

```
Use .github/agents/test-generation.md to create tests for: [implementation reference]
```

or simply:

```
I've implemented sub-issue #105, generate comprehensive tests
```

The agent will recognize your intent and start test generation.

## Best Practices

### For Backend Services
- Focus on unit tests for business logic
- Integration tests for API endpoints
- Mock database in unit tests, use test DB in integration tests
- Test authentication and authorization thoroughly

### For Frontend Components
- Unit tests for component logic
- Integration tests for user interactions
- E2E tests for critical user flows
- Test accessibility features

### For Database Operations
- Test CRUD operations
- Test queries and filters
- Test transactions and rollbacks
- Test constraint violations

### For API Endpoints
- Test all HTTP methods
- Test authentication/authorization
- Test input validation
- Test error responses

## Reviewing Generated Tests

When reviewing the test suite, check:

- [ ] **Completeness**: All acceptance criteria tested?
- [ ] **Independence**: Tests don't depend on each other?
- [ ] **Clarity**: Test names are descriptive?
- [ ] **Coverage**: Meets >80% threshold?
- [ ] **Mocking**: External dependencies properly mocked?
- [ ] **Assertions**: Comprehensive validation?
- [ ] **Edge cases**: Boundary conditions tested?
- [ ] **Errors**: Failure scenarios tested?

## Running and Validating Tests

After generating tests:

```bash
# Run all tests
npm test
# or: pytest, bundle exec rspec, etc.

# Run with coverage
npm run test:coverage

# Run specific test file
npm test -- path/to/test.test.ts

# Run multiple times to check for flaky tests
for i in {1..5}; do npm test; done
```

**Verify**:
- ✅ All tests pass
- ✅ Coverage meets threshold
- ✅ No flaky tests
- ✅ Tests run in reasonable time
- ✅ CI/CD integration works

## Troubleshooting

### Tests Fail After Generation

**Check mocks**:
- Verify mock paths are correct
- Ensure mocks are configured before imports
- Clear mocks between tests

**Check test data**:
- Verify test fixtures are valid
- Check database setup/teardown
- Ensure test data doesn't conflict

**Check assertions**:
- Verify expected values are correct
- Check for timing issues (async)
- Ensure proper error matching

### Coverage Is Too Low

**Add tests for**:
- Untested branches (if/else)
- Error handling paths
- Edge cases
- Helper functions

**Consider**:
- Are some paths unreachable?
- Is there dead code to remove?
- Are tests actually running?

### Tests Are Flaky

**Common causes**:
- Timing issues (async)
- Random test data
- Shared state
- External dependencies

**Solutions**:
- Use proper async/await
- Use deterministic test data
- Ensure test independence
- Mock external services

## Need Help?

- See `.github/agents/test-generation-example.md` for a complete example session
- Read the agent configuration in `.github/agents/test-generation.md` to understand its behavior
- Check the README.md for the complete agent-first workflow
- Use the code implementation agent first to create a solid implementation

Happy testing! 🧪

---

## Complete Workflow Example

Here's how all four agents work together:

### Phase 1: Ideation (Brainstorming)
```
You: "I want to add a notification system"
↓
Brainstorm Agent: [Asks 10-15 questions]
↓
Output: Comprehensive GitHub Issue #42 - "Real-time Notifications System"
```

### Phase 2: Planning (Decomposition)
```
You: [Provide Issue #42]
↓
Decompose Agent: [Analyzes and breaks down]
↓
Output: 9 sub-issues organized into 5 phases
- Sub-issue #105: Implement Notification Backend Service
- Sub-issue #106: Create Notification API Endpoints
- [7 more sub-issues...]
```

### Phase 3: Implementation (Code Implementation)
```
You: [Provide Sub-issue #105]
↓
Code Implementation Agent: [Analyzes codebase, creates plan]
↓
Output: Detailed implementation plan with:
- Database schema changes
- Service class with code examples
- Error handling patterns
- Security considerations
↓
You/Coding Agent: [Implements following the plan]
```

### Phase 4: Testing (Test Generation)
```
You: [Provide completed implementation]
↓
Test Generation Agent: [Analyzes code, generates tests]
↓
Output: Comprehensive test suite with:
- 18 unit tests
- Integration tests (when applicable)
- 92% coverage
- All acceptance criteria validated
↓
You: [Runs tests, verifies coverage]
```

### Phase 5: Review & Merge
```
You: [Creates PR with implementation + tests]
↓
Team: [Reviews code and tests]
↓
Merge: [Feature complete and tested]
```

This complete workflow ensures:
- ✅ Features are well thought out (brainstorm)
- ✅ Work is properly scoped (decompose)
- ✅ Implementation follows best practices (code implementation)
- ✅ Code is thoroughly tested (test generation)
- ✅ Quality is maintained throughout

---

## Tips for Success

### Getting Started
1. Start with brainstorming for new features
2. Use decomposition for any complex work
3. Use code implementation for each sub-issue
4. Use test generation after implementing
5. Iterate and refine at each step

### Best Practices
- **Provide context**: The more context you give agents, the better their output
- **Review carefully**: Agents are helpful but not perfect - review their suggestions
- **Iterate**: Don't hesitate to ask agents to adjust their output
- **Combine agents**: Use agents together for best results
- **Customize**: Adapt agent suggestions to your specific needs

### Common Patterns
- **Small features**: Brainstorm → Decompose (maybe) → Implement → Test
- **Medium features**: Brainstorm → Decompose → Implement each → Test each
- **Large features**: Brainstorm → Decompose → Multiple implementation rounds → Comprehensive testing

---

## Need More Help?

- Check individual agent example files for detailed sessions
- Review agent configuration files to understand capabilities
- See README.md for overview and quick reference
- Experiment with agents on sample issues to learn their behavior
