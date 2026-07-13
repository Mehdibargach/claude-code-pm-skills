---
name: user-stories
description: Turn a feature description into well-structured user stories with acceptance criteria, edge cases, and dependencies.
argument-hint: "[feature description]"
allowed-tools: Read, Write
---

# User Story Generator

Turn a feature description into a complete set of user stories ready for sprint planning. Each story is independently deliverable with testable acceptance criteria.

## Process

1. Read and analyze the feature description.
2. Identify the epic and break it into independently deliverable user stories.
3. For each story, write acceptance criteria using Given/When/Then format.
4. Identify edge cases and unhappy paths for each story.
5. Map dependencies between stories and to external systems.
6. Define what is explicitly out of scope.
7. Save the output to a file in the current working directory as `stories-[feature-name].md`.

## Output Format

### Epic Summary
- Epic name
- Goal (one sentence — what does this epic achieve for the user?)
- Context (why now, what triggered this work)

### User Stories

For each story:

#### Story [number]: [short title]

**Story:** As a [specific user type], I want [concrete action], so that [measurable or observable benefit].

**Priority:** Must-have / Should-have / Nice-to-have

**Acceptance Criteria:**
- Given [precondition], When [action], Then [expected result]
- Given [precondition], When [action], Then [expected result]

**Edge Cases:**
- What happens when [unusual condition]?
- What happens when [error condition]?
- What happens when [boundary condition]?

**Notes:** Any implementation hints or context the team needs.

### Dependencies
- Between stories (which stories must be done before others)
- External dependencies (APIs, services, teams, approvals)
- Technical prerequisites

### Out of Scope
- Features or behaviors explicitly excluded from this epic
- Adjacent work that might come up but belongs to a different epic

## Rules

- Each story must be independently deliverable. If a story can't ship without another, either merge them or make the dependency explicit.
- Acceptance criteria must be testable — a QA engineer should be able to verify each one without asking questions.
- Always include unhappy paths: what happens on failure, timeout, invalid input, missing permissions.
- User stories are written from the user's perspective, not the system's. "The system validates the input" is not a user story.
- Be specific about the user type. "As a user" is too vague — "As a workspace admin with billing access" is specific.
- The benefit in "so that" must be real. "So that I can use the feature" is circular. "So that I can onboard new team members without filing a support ticket" is real.
- If the feature description is too vague, list clarifying questions before writing stories.
- Include story sizing hints (S/M/L) only if enough context is available to estimate.
