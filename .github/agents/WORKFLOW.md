# Agent-First Development Workflow

This document describes the complete agent-driven development workflow from ideation to implementation, including when and how to use each agent.

## Overview

The agent-first approach breaks down feature development into distinct phases, each handled by specialized agents. This ensures consistency, thoroughness, and reduces the cognitive load on developers.

```mermaid
graph LR
    A[💡 Brainstorm] --> B[🗂️ Decompose]
    B --> C{Complex Feature?}
    C -->|Yes| D[🏗️ Architecture]
    C -->|Simple| F[⚡ Implementation]
    D --> E{APIs Needed?}
    E -->|Yes| G[🔌 API Design]
    E -->|No| F
    G --> F
    F --> H[✅ Review]
    H --> I[🚀 Deploy]
    
    style A fill:#e1f5ff
    style B fill:#e1f5ff
    style D fill:#fff3e1
    style G fill:#fff3e1
    style F fill:#e8f5e9
    style H fill:#e8f5e9
    style I fill:#e8f5e9
```

## Phase 1: Ideation 💡

### Agent: Brainstorm Agent

**When to Use**: Starting a new feature or exploring an idea

**Purpose**: Transform vague ideas into well-defined, comprehensive GitHub issues through Socratic questioning

**Input**: 
- Rough idea or problem statement
- User pain points
- Business objectives

**Process**:
1. Agent asks 10-15 targeted questions
2. User answers one at a time
3. Agent adapts follow-up questions based on answers
4. Agent synthesizes into comprehensive GitHub issue

**Output**:
- Complete GitHub issue with:
  - Problem statement
  - Proposed solution
  - User impact analysis
  - Success metrics
  - Technical considerations
  - MVP scope + future enhancements
  - Risk assessment

**Location**: `.github/agents/brainstorm.md`

**Example**: `.github/agents/brainstorm-example.md`

**Typical Duration**: 20-30 minutes

---

## Phase 2: Planning 🗂️

### Agent: Decompose Agent

**When to Use**: After brainstorming creates a comprehensive feature issue

**Purpose**: Break down complex features into actionable, independently-implementable sub-issues

**Input**: 
- GitHub issue from brainstorm phase (or manually created issue)
- Technical context about system architecture
- Team capacity considerations

**Process**:
1. Agent analyzes the feature and confirms understanding
2. Explains decomposition strategy (layer-based, component-based, etc.)
3. Generates 5-15 sub-issues with:
   - Clear, action-oriented titles
   - 3-5 specific acceptance criteria each
   - Dependencies and implementation order
   - Estimated complexity

**Output**:
- Analysis summary
- Execution plan with phases
- Detailed sub-issues ready for assignment
- Dependency map
- Parallel work opportunities identified

**Location**: `.github/agents/decompose.md`

**Example**: `.github/agents/decompose-example.md`

**Typical Duration**: 15-30 minutes

---

## Phase 3: Technical Design (Conditional) 🏗️🔌

After decomposition, you need to decide if technical design is required. Use the decision tree below.

### Decision Tree: Do You Need Design Phase?

```
┌─────────────────────────────────────────┐
│  Start: Review Sub-Issue from Decompose │
└──────────────┬──────────────────────────┘
               │
               ▼
        ┌──────────────┐
        │  Complexity  │
        │  Assessment  │
        └──────┬───────┘
               │
        ┌──────▼───────┐
        │ Is feature   │
        │ complex?     │
        │ (7+ on 1-10) │
        └──┬────────┬──┘
           │        │
         No│        │Yes
           │        │
           │        ▼
           │  ┌─────────────────┐
           │  │ New              │
           │  │ Infrastructure?  │
           │  └───┬─────────┬───┘
           │      │         │
           │    No│         │Yes
           │      │         │
           │      │         ▼
           │      │   ┌──────────────┐
           │      │   │ Architecture │──────┐
           │      │   │ Agent        │      │
           │      │   └──────────────┘      │
           │      │                         │
           │      ▼                         │
           │  ┌──────────┐                 │
           │  │ Database │                 │
           │  │ Changes? │                 │
           │  └─┬────┬───┘                 │
           │    │    │                     │
           │  No│    │Yes                  │
           │    │    │                     │
           │    │    ▼                     │
           │    │  ┌──────────────┐       │
           │    │  │ Architecture │───────┤
           │    │  │ Agent        │       │
           │    │  └──────────────┘       │
           │    │                         │
           │    ▼                         │
           │  ┌────────────┐              │
           │  │ Multiple   │              │
           │  │ APIs?      │              │
           │  └──┬─────┬───┘              │
           │     │     │                  │
           │   No│     │Yes               │
           │     │     │                  │
           │     │     ▼                  │
           │     │  ┌──────────────┐     │
           │     │  │ API Design   │─────┤
           │     │  │ Agent        │     │
           │     │  └──────────────┘     │
           │     │                       │
           │     │                       │
           ▼     ▼                       ▼
    ┌──────────────────────────────────────┐
    │       Skip to Implementation         │
    └──────────────────────────────────────┘
```

### 3A: Architecture Design 🏗️

#### Agent: Architecture Agent

**When to Use**:
- ✅ Complex features (complexity 7+ out of 10)
- ✅ New infrastructure components
- ✅ Database schema changes
- ✅ Multi-component integrations
- ✅ Performance-critical features
- ✅ Security-sensitive features

**When to Skip**:
- ❌ Simple UI changes
- ❌ Bug fixes
- ❌ Trivial refactorings
- ❌ Single-file changes

**Purpose**: Create comprehensive technical architecture including system design, data models, ADRs, and integration patterns

**Input**:
- Sub-issue from decompose phase
- Performance requirements
- Existing system constraints
- Technology preferences

**Process**:
1. Complexity assessment (determines if full design is needed)
2. Requirements clarification
3. Generate architecture design with:
   - Component diagrams (Mermaid)
   - Data models and schema
   - ADRs for key decisions
   - Integration approach
   - Security, performance, scalability considerations
4. API surface detection
5. Handoff recommendations

**Output**:
- Complete architecture design document
- ADRs for key decisions
- Mermaid diagrams
- Database migration plan
- Next steps with conditional recommendations
- **Recommendation to use API Design Agent if APIs detected**

**Location**: `.github/agents/architecture.md`

**Example**: `.github/agents/architecture-example.md`

**Typical Duration**: 30-60 minutes

---

### 3B: API Design 🔌

#### Agent: API Design Agent

**When to Use**:
- ✅ Recommended by Architecture Agent (APIs detected)
- ✅ Creating new REST/GraphQL/WebSocket/gRPC APIs
- ✅ Modifying existing API contracts
- ✅ Adding endpoints to existing APIs
- ✅ Complex API interactions

**When to Skip**:
- ❌ No APIs in the feature
- ❌ Internal function interfaces (not external APIs)
- ❌ Simple CRUD with well-established patterns (optional)

**Can Work**:
- **With Architecture Context** (Recommended): Receives architecture decisions and aligns API design
- **Standalone**: For simple API changes without architecture phase

**Purpose**: Create detailed API specifications including OpenAPI/AsyncAPI specs, authentication, error handling, and security

**Input**:
- Architecture document (if available)
- Sub-issue or feature description
- Existing API patterns in codebase
- Authentication requirements

**Process**:
1. Check for architecture context
2. Analyze requirements for API needs
3. Design comprehensive API specifications:
   - Endpoint definitions
   - Request/response schemas
   - Authentication/authorization
   - Error responses
   - Rate limiting
   - Security patterns
4. Generate OpenAPI/AsyncAPI specification
5. Provide implementation guidance

**Output**:
- Complete API design document
- OpenAPI 3.0 or AsyncAPI 2.0 specification
- Request/response examples
- Security considerations
- Implementation notes referencing existing code patterns

**Location**: `.github/agents/api-design.md`

**Example**: `.github/agents/api-design-example.md`

**Typical Duration**: 30-45 minutes

---

## Phase 4: Implementation ⚡

**When to Use**: After planning (and design if needed) is complete

**Who Does It**: 
- Coding agents (GitHub Copilot, custom implementation agents)
- Human developers

**Input**:
- Sub-issues from decompose agent
- Architecture document (if created)
- API specification (if created)
- Acceptance criteria

**Process**:
1. Read attached design documents
2. Follow architecture patterns
3. Implement per API specifications
4. Write tests per acceptance criteria
5. Create PR for review

**Tools**:
- GitHub Copilot for code generation
- Custom coding agents
- Traditional development

**Typical Duration**: Varies by sub-issue (1-5 days per sub-issue)

---

## Phase 5: Review ✅

**When to Use**: After implementation is complete

**Who Does It**:
- Code review agents
- Human reviewers
- Automated testing

**Process**:
1. Verify acceptance criteria met
2. Check adherence to architecture
3. Validate API contracts
4. Security review
5. Performance testing

**Typical Duration**: 1-2 days

---

## Phase 6: Deploy 🚀

**When to Use**: After review is approved

**Process**:
1. Merge to main branch
2. CI/CD pipeline runs
3. Deploy to staging
4. Validation tests
5. Deploy to production
6. Monitor metrics

**Typical Duration**: 1-2 hours to days (depending on deployment strategy)

---

## Complete Workflow Examples

### Example 1: Complex Feature - Real-Time Notification System

**Scenario**: Adding WebSocket-based real-time notifications for error documentation

```
1. Brainstorm Agent (20 min)
   ↓ Creates comprehensive issue
   
2. Decompose Agent (25 min)
   ↓ Breaks into 9 sub-issues across 5 phases
   
3. Review Sub-Issue #2: "Build Real-Time Notification System"
   ↓ Complexity Assessment: 8/10 (High)
   
4. Architecture Agent (45 min)
   ↓ Designs WebSocket architecture with Redis pub/sub
   ↓ Detects WebSocket API needed
   ↓ Recommends: "Invoke API Design Agent"
   
5. API Design Agent (40 min)
   ↓ Designs WebSocket protocol with 10 message types
   ↓ Creates AsyncAPI specification
   ↓ Provides Socket.io implementation examples
   
6. Implementation (2-3 weeks)
   ↓ Backend team builds WebSocket server
   ↓ Frontend team integrates Socket.io client
   ↓ Following architecture and API specs
   
7. Review (3 days)
   ↓ Code review
   ↓ Security testing
   ↓ Load testing (2000+ connections)
   
8. Deploy (1 week gradual rollout)
   ↓ 10% → 50% → 100% of users
   
Total: 4-5 weeks from idea to production
```

---

### Example 2: Medium Feature - REST API for User Preferences

**Scenario**: Adding CRUD API for user preference management

```
1. Brainstorm Agent (15 min)
   ↓ Creates issue for user preferences feature
   
2. Decompose Agent (15 min)
   ↓ Breaks into 5 sub-issues
   
3. Review Sub-Issue: "Create User Preferences API"
   ↓ Complexity Assessment: 4/10 (Medium)
   ↓ Decision: Skip Architecture, use API Design only
   
4. API Design Agent (25 min) - STANDALONE MODE
   ↓ Designs RESTful CRUD endpoints
   ↓ Creates OpenAPI 3.0 specification
   ↓ No architecture context, uses existing patterns
   
5. Implementation (1 week)
   ↓ Backend implements endpoints per spec
   ↓ Frontend integrates with API
   
6. Review (2 days)
   
7. Deploy (2 days)
   
Total: 2 weeks from idea to production
```

---

### Example 3: Simple Feature - UI Component

**Scenario**: Adding a new button to existing page

```
1. Brainstorm Agent (10 min) - OPTIONAL
   ↓ Or just write GitHub issue manually
   
2. Decompose Agent (10 min) - OPTIONAL
   ↓ Or break down manually
   
3. Complexity Assessment: 1/10 (Trivial)
   ↓ Decision: Skip Architecture AND API Design
   
4. Implementation (2 hours)
   ↓ Add button component
   ↓ Wire up event handler
   ↓ Update tests
   
5. Review (1 hour)
   
6. Deploy (same day)
   
Total: 1 day from idea to production
```

---

### Example 4: Database Schema Change

**Scenario**: Adding new tables for audit logging

```
1. Decompose Agent (optional, or direct from issue)
   ↓ Sub-issue: "Add Audit Log Tables"
   
2. Complexity Assessment: 6/10 (Medium-High)
   ↓ Database changes detected
   ↓ Decision: Use Architecture Agent, skip API Design
   
3. Architecture Agent (30 min)
   ↓ Designs schema with proper indexes
   ↓ Creates migration plan
   ↓ Documents rollback strategy
   ↓ No APIs detected → Skip API Design
   
4. Implementation (3 days)
   ↓ Write migrations
   ↓ Test in staging
   ↓ Update application code
   
5. Review (2 days)
   ↓ DBA review
   ↓ Test rollback
   
6. Deploy (1 day)
   
Total: 1-2 weeks
```

---

## Decision Matrix: Which Agents When?

| Feature Type | Brainstorm | Decompose | Architecture | API Design | Total Time |
|--------------|------------|-----------|--------------|------------|------------|
| **New major feature** | ✅ Yes | ✅ Yes | ✅ Yes | ⚠️ If APIs | 1-2 hours design |
| **REST API (complex)** | ⚠️ Optional | ⚠️ Optional | ✅ Yes | ✅ Yes | 1-2 hours design |
| **REST API (simple CRUD)** | ❌ No | ❌ No | ❌ No | ✅ Yes | 30 min design |
| **WebSocket/Real-time** | ✅ Yes | ✅ Yes | ✅ Yes | ✅ Yes | 2 hours design |
| **Database schema change** | ⚠️ Optional | ⚠️ Optional | ✅ Yes | ❌ No | 30-60 min design |
| **UI-only feature** | ⚠️ Optional | ⚠️ Optional | ❌ No | ❌ No | 0-20 min design |
| **Bug fix** | ❌ No | ❌ No | ❌ No | ❌ No | 0 min design |
| **Refactoring** | ❌ No | ⚠️ Optional | ⚠️ If complex | ❌ No | 0-30 min design |
| **Third-party integration** | ⚠️ Optional | ✅ Yes | ✅ Yes | ⚠️ Sometimes | 1-2 hours design |
| **Background job** | ⚠️ Optional | ⚠️ Optional | ⚠️ If complex | ❌ No | 0-60 min design |

**Legend**:
- ✅ Yes: Strongly recommended
- ⚠️ Optional: Use judgment, consider complexity
- ❌ No: Skip this phase

---

## Agent Collaboration Model

### Sequential Workflow (Most Common)

```
Brainstorm → Decompose → Architecture → API Design → Implementation
```

**Best For**: 
- New features
- Complex systems
- When requirements need exploration

**Handoffs**:
1. Brainstorm → Decompose: Issue URL passed
2. Decompose → Architecture: Sub-issue URL passed
3. Architecture → API Design: Architecture doc link passed
4. API Design → Implementation: API spec link attached to sub-issues

---

### Standalone API Design

```
Issue → API Design → Implementation
```

**Best For**:
- Simple API additions
- Modifying existing endpoints
- When architecture is already established

**Example**: Adding pagination to existing endpoint

---

### Skip Design Phases

```
Issue → Implementation
```

**Best For**:
- UI-only changes
- Bug fixes
- Simple refactorings
- When patterns are well-established

**Risk**: Higher chance of inconsistency, rework

---

## Best Practices

### When to Use Brainstorm Agent

**✅ Use When**:
- Feature idea is vague or exploratory
- Need to involve multiple stakeholders
- Want structured thinking about trade-offs
- Building case for new feature

**❌ Skip When**:
- Requirements are crystal clear
- Just fixing a bug
- Time-sensitive small changes

---

### When to Use Decompose Agent

**✅ Use When**:
- Feature has multiple components
- Need to parallelize work across team
- Want clear acceptance criteria
- Planning sprints

**❌ Skip When**:
- Single atomic task
- Already have clear task breakdown
- Extremely urgent hotfix

---

### When to Use Architecture Agent

**✅ Use When**:
- Complexity score 7+ out of 10
- New infrastructure components
- Database schema changes
- Performance/security critical
- Multi-system integration

**❌ Skip When**:
- Complexity score below 4
- Well-established patterns apply
- UI-only changes
- Simple bug fixes

**⚠️ Optional When**:
- Complexity score 4-6
- Small database changes
- Refactoring existing code

---

### When to Use API Design Agent

**✅ Use When**:
- Creating new APIs (REST, GraphQL, WebSocket, gRPC)
- Modifying API contracts
- Multiple endpoints
- External-facing APIs
- Need OpenAPI specification

**❌ Skip When**:
- No APIs in feature
- Internal function interfaces only
- Following well-established CRUD pattern

**⚠️ Optional When**:
- Single simple CRUD endpoint
- Internal APIs with established patterns

---

## Agent Invocation Commands

### Brainstorm Agent
```
I want to brainstorm a new feature
```
or
```
Use .github/agents/brainstorm.md to help me explore this idea
```

### Decompose Agent
```
Decompose this GitHub issue into sub-issues: [issue URL]
```
or
```
Use .github/agents/decompose.md to break down this feature
```

### Architecture Agent
```
Design the architecture for issue #105
```
or
```
@architecture analyze sub-issue #2 and create technical design
```

### API Design Agent
```
@api-design design APIs for issue #105 using this architecture: [architecture link]
```
or
```
Design REST API for user preferences feature
```

---

## Measuring Success

### Metrics to Track

**Design Phase Efficiency**:
- Time from issue creation to implementation-ready
- Rework rate (how often do we need to redesign?)
- Blocker rate (waiting for design decisions)

**Implementation Quality**:
- Bug rate in features with vs. without design phase
- Security issues found in review
- Performance issues requiring rework

**Developer Experience**:
- Developer confidence level when starting implementation
- Questions about technical approach during implementation
- PR revision count

**Business Impact**:
- Time to market for features
- Feature quality (user satisfaction)
- Maintenance burden (post-launch bug rate)

### Expected Improvements

With proper use of design agents:
- **30-50% reduction** in implementation rework
- **20-30% improvement** in time to market (despite upfront design)
- **40-60% reduction** in architecture questions during implementation
- **Higher developer satisfaction** with clear specifications

---

## Troubleshooting

### "Architecture Agent says my feature is too simple"
- Trust the complexity assessment
- Proceed to implementation with existing patterns
- Saves time on unnecessary design

### "API Design Agent asks for architecture context but I skipped that phase"
- For simple APIs, choose "Continue anyway" in standalone mode
- For complex APIs, go back and run Architecture Agent first
- Use judgment: if you're unsure, do architecture first

### "I have architecture but agent recommends API Design, can I skip?"
- You can, but not recommended if:
  - Multiple endpoints
  - Complex protocols (WebSocket, gRPC)
  - External-facing APIs
  - Team needs OpenAPI spec
- Safe to skip if:
  - Internal APIs
  - Established CRUD patterns
  - Time-critical

### "Design phase taking too long"
- Ensure you provide complete context upfront
- Answer agent questions thoroughly the first time
- For urgent work, skip to implementation with known risks

---

## Summary

The agent-first workflow provides a systematic approach to feature development:

1. **💡 Brainstorm** - Explore ideas thoroughly
2. **🗂️ Decompose** - Break into actionable work
3. **🏗️ Architecture** (conditional) - Design system architecture
4. **🔌 API Design** (conditional) - Specify API contracts
5. **⚡ Implementation** - Build with clear specifications
6. **✅ Review** - Validate against design
7. **🚀 Deploy** - Ship with confidence

**Key Principle**: Use the right amount of design for the complexity of the feature. Not every feature needs full architecture, but complex features benefit immensely from upfront design.

**Remember**: 
- Design time is typically 1-10% of total feature time
- But prevents 30-50% of implementation rework
- ROI is highly positive for medium-complex features

**When in doubt**: Err on the side of more design for complex features, less for simple ones. The complexity assessment in the Architecture Agent helps make this decision.
