# Using the Agent-First Template

## Overview

This template provides six complementary agents for the complete feature development lifecycle:

1. **Brainstorming Agent** 💡 - Helps you explore and refine feature ideas
2. **Decomposition Agent** 🗂️ - Breaks down features into actionable sub-issues
3. **Architecture Agent** 🏗️ - Designs technical architecture for complex features
4. **API Design Agent** 🔌 - Creates detailed API specifications
5. **Documentation Agent** 📚 - Generates and maintains comprehensive documentation
6. **Code Review Agent** 🔍 - Automated first-pass code review with actionable feedback

Together, they enable a complete agent-first development workflow: **Brainstorm → Decompose → Architecture (if needed) → API Design (if needed) → Implement → Document → Code Review → Merge**

For complete workflow guidance, see **[WORKFLOW.md](WORKFLOW.md)**.

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

---

# Using the Architecture Agent 🏗️

## Quick Start

The Architecture Agent designs comprehensive technical architecture for complex features including system components, data models, technology decisions, and integration patterns.

### Step 1: Decide If You Need Architecture

**✅ Use Architecture Agent When**:
- Feature complexity is 7+ out of 10
- New infrastructure components required
- Database schema changes needed
- Multi-component integrations
- Performance or security critical features

**❌ Skip to Implementation When**:
- Simple UI changes
- Bug fixes
- Well-established patterns apply
- Feature complexity below 4/10

**See [WORKFLOW.md](WORKFLOW.md) for complete decision tree**

### Step 2: Invoke the Agent

Use the GitHub Copilot interface to invoke the architecture agent:

- Open GitHub Copilot chat
- Reference the agent file: `.github/agents/architecture.md`
- Provide a sub-issue from decomposition or feature description

### Step 3: Provide Context

The agent will ask about:
- **Performance requirements**: Response times, throughput, scale
- **Existing system context**: Current architecture, technologies
- **Technology constraints**: Required or prohibited technologies
- **Timeline**: MVP vs. full production scale

### Step 4: Review the Architecture Design

The agent will generate:

1. **Complexity Assessment** - Validates if full architecture is needed
2. **System Architecture** - Component diagrams (Mermaid format), data flow
3. **Data Architecture** - Data models, database schema, migrations
4. **Technology Stack Decisions** - With Architecture Decision Records (ADRs)
5. **Integration Points** - How this connects with existing systems
6. **Security & Performance** - Considerations and optimization strategies
7. **Deployment Strategy** - Infrastructure, rollback plan, migration path
8. **API Surface Detection** - Recommends API Design Agent if APIs detected

### Step 5: Act on Recommendations

The agent provides conditional next steps:

```markdown
📋 Next Steps:

1. Review Architecture ✓
2. [CONDITIONAL] Invoke API Design Agent
   - Command: @api-design design APIs for issue #105 using this architecture
   - Reason: 2 REST endpoints detected
3. [CONDITIONAL] Review database migrations with DBA
4. Ready for Implementation
```

## What You'll Get

A production-ready architecture document with:

- ✅ **Component diagrams** (Mermaid) showing system architecture
- ✅ **Data models** with validation rules and relationships
- ✅ **Database schemas** with migration and rollback plans
- ✅ **ADRs** documenting key technical decisions
- ✅ **Security considerations** addressing OWASP concerns
- ✅ **Performance targets** with optimization strategies
- ✅ **Scalability plan** for current and future growth
- ✅ **Integration patterns** for existing systems
- ✅ **Deployment strategy** with infrastructure requirements
- ✅ **API detection** with handoff to API Design Agent

## Integration with Other Agents

**From Decomposition Agent**:
```
Decompose Agent → Architecture Agent
- Receives sub-issue with clear scope
- Expands on technical details
```

**To API Design Agent**:
```
Architecture Agent → API Design Agent
- Detects APIs in architecture
- Provides architectural context
- Recommends: "@api-design design APIs..."
```

**To Implementation**:
```
Architecture Agent → Implementation
- Provides complete technical blueprint
- Attached to sub-issues for reference
```

## Example Commands

Depending on your GitHub Copilot setup:

```
Design the architecture for issue #105
```

or

```
@architecture analyze sub-issue #2 and create technical design
```

or

```
Use .github/agents/architecture.md to design architecture for this feature: [paste description]
```

## Tips for Effective Architecture

1. **Provide complete context**: More detail = better architecture
2. **Answer questions thoroughly**: Agent adapts to your responses
3. **Review ADRs carefully**: These document "why" behind decisions
4. **Follow recommendations**: If agent says invoke API Design Agent, do it
5. **Attach to sub-issues**: Link architecture doc to implementation tasks
6. **Update based on learnings**: Architecture is a living document

## Need Help?

- See `.github/agents/architecture-example.md` for a complete example session
- Read the agent configuration in `.github/agents/architecture.md`
- Check [WORKFLOW.md](WORKFLOW.md) for when to use architecture vs. skip to implementation
- Review template files in `.github/templates/` for ADRs and design docs

---

# Using the API Design Agent 🔌

## Quick Start

The API Design Agent creates comprehensive API specifications including OpenAPI/AsyncAPI specs, authentication patterns, error handling, and security considerations.

### Step 1: Decide If You Need API Design

**✅ Use API Design Agent When**:
- Creating new REST, GraphQL, WebSocket, or gRPC APIs
- Modifying existing API contracts
- Multiple endpoints to design
- External-facing APIs
- Architecture Agent recommends it (APIs detected)

**❌ Skip When**:
- No APIs in the feature
- Internal function interfaces only
- Simple CRUD following established patterns (optional)

### Step 2: Check for Architecture Context

**With Architecture Context** (Recommended):
- Run Architecture Agent first for complex features
- API Design Agent uses architectural decisions for consistency
- Ensures alignment on auth, data models, tech stack

**Standalone Mode**:
- For simple API changes without architecture phase
- Agent will ask if you want to continue without context
- Good for: Adding pagination, modifying response format, simple endpoints

### Step 3: Invoke the Agent

Use the GitHub Copilot interface:

```
@api-design design APIs for issue #105 using this architecture: [architecture link]
```

or standalone:

```
Design REST API for user preferences feature
```

### Step 4: Provide Requirements

The agent will ask about:
- **API Type**: REST, GraphQL, WebSocket, gRPC, or mixed?
- **Consumers**: Internal services, external clients, mobile apps, web?
- **Existing Patterns**: Are there APIs to follow for consistency?
- **Authentication**: Requirements and method
- **Expected Volume**: Request rates and scaling needs

### Step 5: Review API Specifications

The agent will generate:

1. **API Overview** - Summary of endpoints and authentication
2. **Detailed Specifications** - Full specs for each endpoint including:
   - Request/response formats with examples
   - Query parameters and headers
   - Authentication and authorization
   - Error responses (400, 401, 403, 404, 429, 500)
   - Rate limiting rules
3. **OpenAPI/AsyncAPI Spec** - Complete machine-readable specification
4. **Security Considerations** - OWASP mitigations, auth patterns
5. **Implementation Guidance** - Code patterns to follow from existing codebase

## What You'll Get

A production-ready API specification with:

- ✅ **Endpoint definitions** for all APIs (REST/GraphQL/WebSocket/gRPC)
- ✅ **Request/response schemas** with validation rules
- ✅ **Authentication & authorization** patterns
- ✅ **Error handling** with consistent error responses
- ✅ **Rate limiting** strategy and configuration
- ✅ **Security considerations** (OWASP Top 10 mitigations)
- ✅ **OpenAPI 3.0** or **AsyncAPI 2.0** specification
- ✅ **Code examples** for client integration (JavaScript, Swift, Kotlin)
- ✅ **Implementation notes** referencing existing patterns

## API Types Supported

### REST APIs
- Full CRUD operations
- Pagination strategies (offset, cursor, page-based)
- Filtering and sorting
- Bulk operations
- OpenAPI 3.0 specification

### GraphQL APIs
- Query and Mutation definitions
- Schema with types and inputs
- Pagination (connections, edges, cursors)
- Error handling patterns

### WebSocket APIs
- Connection lifecycle
- Message format standards
- Bidirectional communication
- Authentication flow
- AsyncAPI 2.0 specification

### gRPC APIs
- Service definitions
- Message types (proto3)
- Streaming patterns
- Error codes

## Integration with Other Agents

**From Architecture Agent** (Recommended):
```
Architecture Agent → API Design Agent
- Receives architecture context
- Aligns with architectural decisions
- Uses data models from architecture
```

**Standalone** (Simple APIs):
```
Sub-Issue → API Design Agent → Implementation
- No architecture needed for simple APIs
- Agent uses existing patterns
```

**To Implementation**:
```
API Design Agent → Implementation
- Provides OpenAPI/AsyncAPI spec
- Implementation uses spec for contract testing
- Developers follow examples
```

## Example Commands

Depending on your setup:

```
@api-design design APIs for issue #105 using this architecture: [link]
```

or

```
Design WebSocket protocol for real-time notifications
```

or

```
Create OpenAPI spec for user management CRUD endpoints
```

## Tips for Effective API Design

1. **Architecture first for complex APIs**: Run Architecture Agent before API Design for features with multiple APIs
2. **Standalone for simple changes**: Skip to API Design for simple additions
3. **Provide existing patterns**: Point agent to existing APIs to follow
4. **Review security thoroughly**: Ensure auth, rate limiting, and error handling are appropriate
5. **Validate OpenAPI spec**: Use Swagger UI to test the generated spec
6. **Share with consumers**: Give API spec to frontend/mobile teams early

## When to Use Standalone vs. With Architecture

| Scenario | Recommendation | Reason |
|----------|----------------|--------|
| Multiple endpoints + new infrastructure | Architecture → API Design | Need system design first |
| Simple CRUD endpoint | API Design standalone | Established patterns work |
| WebSocket/Real-time | Architecture → API Design | Complex protocol needs architecture |
| Modifying existing API | API Design standalone | Architecture already exists |
| External-facing API | Architecture → API Design | Security and scale critical |

## Need Help?

- See `.github/agents/api-design-example.md` for a complete WebSocket example
- Read the agent configuration in `.github/agents/api-design.md`
- Check [WORKFLOW.md](WORKFLOW.md) for decision tree on when to use API Design
- Review `.github/templates/openapi-template.yaml` for starter template
- See "Integration with Architecture Agent" section above for collaboration patterns

---

# Using the Documentation Agent 📚

## Quick Start

The Documentation Agent generates and maintains comprehensive technical documentation for your code, including API references, code comments, user guides, and changelogs.

### Step 1: Decide What Documentation You Need

**✅ Use Documentation Agent When**:
- Feature is implemented and ready to document
- Creating or updating APIs
- Adding new components or libraries
- Documentation gaps identified in code review
- Updating user-facing features

**Documentation Types**:
- API reference documentation (REST, GraphQL, WebSocket)
- Code documentation (JSDoc, docstrings)
- User guides and tutorials
- Changelog entries
- README updates

### Step 2: Invoke the Agent

Use the GitHub Copilot interface to invoke the documentation agent:

- Open GitHub Copilot chat
- Reference the agent file: `.github/agents/documentation.md`
- Provide code, PR URL, or files to document

### Step 3: Provide Context

The agent will ask about:
- **Audience**: Who will use this documentation? (developers, end-users, API consumers)
- **Existing Patterns**: Documentation standards or examples to follow
- **Format Preferences**: Markdown, JSDoc, OpenAPI, other formats
- **Depth**: Quick reference or comprehensive guides with examples

### Step 4: Review Generated Documentation

The agent will generate:

1. **API Documentation** - Complete reference with examples
2. **Code Documentation** - JSDoc/docstrings for functions and classes
3. **User Guides** - Step-by-step tutorials and use cases
4. **Changelog Entries** - Following Keep a Changelog format
5. **README Updates** - Installation, configuration, examples

### Step 5: Integrate and Iterate

Review the documentation and:
- Verify code examples are accurate
- Check that all endpoints/functions are covered
- Ensure examples work as written
- Request updates for any gaps or errors

## What You'll Get

A complete documentation suite with:

- ✅ **API Reference** - All endpoints with request/response examples
- ✅ **Code Documentation** - JSDoc/docstrings for public APIs
- ✅ **User Guides** - Comprehensive tutorials and use cases
- ✅ **Changelog Entries** - Properly formatted version history
- ✅ **README Updates** - Quick start and configuration
- ✅ **Multiple Languages** - Examples in JavaScript, Python, etc.
- ✅ **Gap Analysis** - Identification of missing documentation

## Integration with Other Agents

**From Implementation/API Design Agent**:
```
Implementation Complete → Documentation Agent
- Receives code and specifications
- Reviews tests for examples
- Generates comprehensive docs
```

**To Code Review Agent**:
```
Documentation Agent → Code Review Agent
- Documentation is complete
- Code Review validates documentation
```

## Example Commands

Depending on your GitHub Copilot setup, you might invoke the agent like:

```
Generate documentation for this PR: [URL]
```

or

```
@documentation document the new user preferences API
```

or

```
Use .github/agents/documentation.md to create API documentation
```

## Tips for Effective Documentation

1. **Provide Complete Code**: Agent needs full implementation to generate accurate docs
2. **Include Design Docs**: Architecture and API specs help generate better documentation
3. **Specify Audience**: Clear target audience improves documentation quality
4. **Review Examples**: Verify all code examples actually work
5. **Update Regularly**: Re-run agent when APIs or features change
6. **Follow Patterns**: Point agent to existing docs to match style

## Documentation Maintenance Mode

When updating existing documentation:

**Gap Identification**:
- Agent scans existing documentation
- Identifies missing or outdated sections
- Prioritizes documentation needs
- Estimates time to address gaps

**Update Strategy**:
- Reviews implementation changes
- Updates affected documentation
- Adds missing examples
- Fixes inconsistencies

## Need Help?

- See `.github/agents/documentation-example.md` for a complete example session
- Read the agent configuration in `.github/agents/documentation.md`
- Check [WORKFLOW.md](WORKFLOW.md) for when to use documentation in the lifecycle

---

# Using the Code Review Agent 🔍

## Quick Start

The Code Review Agent performs comprehensive automated first-pass code review, catching common issues before human review and providing actionable feedback.

### Step 1: Decide When to Run Review

**✅ Use Code Review Agent When**:
- Before requesting human code review
- After implementation and testing complete
- As automated quality gate in CI/CD
- When you want comprehensive feedback
- Before merging to main branch

**✅ Review Categories**:
- Security vulnerabilities
- Code quality and maintainability
- Performance optimization
- Test coverage validation
- Documentation completeness
- Accessibility (for UI changes)

### Step 2: Invoke the Agent

Use the GitHub Copilot interface to invoke the code review agent:

- Open GitHub Copilot chat
- Reference the agent file: `.github/agents/code-review.md`
- Provide PR URL or code changes to review

### Step 3: Provide Context

The agent will ask about:
- **PR URL or Code Changes**: What to review
- **Acceptance Criteria**: From original issue (if available)
- **Design Documents**: Architecture and API specs (if available)
- **Focus Areas**: Specific concerns (optional)

### Step 4: Review Feedback

The agent will provide:

1. **Executive Summary** - Overall assessment and key findings
2. **Critical Issues** 🔴 - Must fix before merge (security, data corruption)
3. **High Priority** 🟠 - Should fix before merge (performance, quality)
4. **Medium Priority** 🟡 - Consider fixing (duplication, minor issues)
5. **Low Priority** 🟢 - Nice to have (suggestions, optimizations)
6. **Positive Observations** ✨ - Good practices identified

Each issue includes:
- Specific file and line numbers
- Current code and recommended fix
- Clear explanation of the problem
- Estimated fix time
- Severity and impact assessment

### Step 5: Address Feedback

Review the findings and:
- **Fix all critical issues** (security, breaking bugs)
- **Fix most high priority issues** (performance, quality)
- **Consider medium priority** (based on time/priorities)
- **Optional low priority** (nice-to-have improvements)

### Step 6: Re-Review if Needed

After significant changes:
- Run code review again
- Verify fixes address original issues
- Ensure no new issues introduced

## What You'll Get

A comprehensive code review with:

- ✅ **Security Scan** - SQL injection, XSS, auth issues, OWASP Top 10
- ✅ **Code Quality** - Duplication, complexity, best practices, SOLID principles
- ✅ **Performance** - N+1 queries, inefficient algorithms, caching opportunities
- ✅ **Test Coverage** - Coverage %, missing test cases, edge cases
- ✅ **Documentation** - JSDoc/docstrings, API docs, changelog, examples
- ✅ **Accessibility** - WCAG compliance, keyboard nav, screen readers (for UI)
- ✅ **Prioritization** - Severity-based with critical issues highlighted
- ✅ **Actionable Fixes** - Specific code examples for every issue
- ✅ **Fix Time Estimates** - Help prioritize based on effort

## Integration with Other Agents

**After Documentation Agent**:
```
Documentation Agent → Code Review Agent
- Reviews documentation completeness
- Validates documentation accuracy
- Checks changelog updates
```

**After Implementation/Test Agents**:
```
Implementation + Tests → Code Review Agent
- Reviews implementation quality
- Validates test coverage
- Checks acceptance criteria
```

**Before Human Review**:
```
Code Review Agent → Human Reviewer
- Catches 80%+ of common issues
- Reduces human review time by 30-50%
- Human focuses on architecture and logic
```

## Example Commands

Depending on your GitHub Copilot setup, you might invoke the agent like:

```
Review this PR: [URL]
```

or

```
@code-review perform automated review of PR #123
```

or

```
Use .github/agents/code-review.md to review my changes
```

## Severity Level Guidelines

### 🔴 Critical (Must Fix Before Merge)
- Security vulnerabilities (SQL injection, XSS, auth bypass)
- Data corruption risks
- Breaking changes without migration
- Critical bugs in core functionality

### 🟠 High Priority (Should Fix Before Merge)
- Performance issues affecting UX
- Poor error handling in critical paths
- Significant code quality issues
- Missing tests for critical functionality

### 🟡 Medium Priority (Consider Fixing)
- Code duplication
- Minor performance improvements
- Documentation gaps for public APIs
- Test coverage below 80%

### 🟢 Low Priority (Nice to Have)
- Code style inconsistencies
- Optimization with minimal impact
- Additional documentation
- Refactoring for readability

## Tips for Effective Code Review

1. **Provide Complete Context**: Include acceptance criteria and design docs
2. **Fix Critical First**: Focus on security and breaking bugs
3. **Re-Review After Major Changes**: Run again after significant fixes
4. **Don't Skip Low Severity**: Some may be quick wins
5. **Use in CI/CD**: Automate as quality gate
6. **Complement Human Review**: Use before, not instead of human review
7. **Track Metrics**: Monitor issues found over time

## Best Practices

**Before Running Review**:
- Ensure implementation is complete
- Run tests and verify they pass
- Generate documentation
- Self-review your code first

**When Reviewing Feedback**:
- Read all issues, even low severity
- Understand why something is an issue
- Learn from code examples provided
- Track patterns in your code

**After Addressing Issues**:
- Re-run review for complex changes
- Verify all critical issues resolved
- Document why you skipped any issues
- Update tests after fixes

## Need Help?

- See `.github/agents/code-review-example.md` for a complete example session
- Read the agent configuration in `.github/agents/code-review.md`
- Check [WORKFLOW.md](WORKFLOW.md) for when to use code review in the lifecycle
- Review severity guidelines to prioritize fixes

---

# Complete Workflow Summary

The full agent-driven development process:

```
1. 💡 Brainstorm → Creates comprehensive issue
2. 🗂️ Decompose → Breaks into actionable sub-issues
3. 🏗️ Architecture (if complex) → Designs technical architecture
4. 🔌 API Design (if APIs) → Specifies API contracts
5. ⚡ Implementation → Build with clear specs
6. 🧪 Testing → Validate functionality
7. 📚 Documentation → Generate comprehensive docs
8. 🔍 Code Review → Automated quality check
9. ✅ Human Review → Final validation
10. 🚀 Deploy → Ship with confidence
```

**For complete guidance**, see **[WORKFLOW.md](WORKFLOW.md)**.

---

## Need Help?

### Brainstorm Agent
- See `.github/agents/brainstorm-example.md` for an example session
- Read `.github/agents/brainstorm.md` for agent behavior

### Decompose Agent
- See `.github/agents/decompose-example.md` for an example decomposition
- Read `.github/agents/decompose.md` for agent behavior

### Architecture Agent
- See `.github/agents/architecture-example.md` for an example design
- Read `.github/agents/architecture.md` for agent behavior
- Review `.github/templates/adr-template.md` for ADR format
- Review `.github/templates/design-doc-template.md` for design doc format

### API Design Agent
- See `.github/agents/api-design-example.md` for a WebSocket example
- Read `.github/agents/api-design.md` for agent behavior
- Review `.github/templates/openapi-template.yaml` for OpenAPI template

### Complete Workflow
- See **[WORKFLOW.md](WORKFLOW.md)** for end-to-end guidance
- Decision trees for when to use each agent
- Complete workflow examples
- Best practices and troubleshooting

Happy building! 🚀
