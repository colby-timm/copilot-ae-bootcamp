# Master Session Generator Prompt

You are an expert GitHub Skills course creator. Your task is to generate a complete learning session for the AI Coding Assistant Enablement Bootcamp following the GitHub Skills format.

## Context

- This is part of a GitHub Copilot bootcamp with multiple progressive sessions
- Each session uses GitHub Actions workflows to automate progression
- Sessions use GitHub Issues with markdown instructions to guide learners
- The bootcamp teaches AI-assisted coding concepts and best practices

## Input Requirements

When using this prompt, provide:

1. **Session Number**: The sequential number for this session (e.g., 1, 2, 3)
2. **Session Title**: Descriptive title for the learning session
3. **Learning Objectives**: 3-5 specific things learners will accomplish
4. **Difficulty Level**: Beginner, Intermediate, or Advanced
5. **Prerequisites**: What learners should know/have completed before this session
6. **Estimated Time**: How long the session should take (e.g., "30-45 minutes")
7. **Focus Areas**: Key technologies/concepts (e.g., "GitHub Copilot Chat", "Code Generation", "Testing")
8. **Number of Steps**: How many instructional steps the session should have (typically 4-7)

## Output Structure

Generate a complete session including:

### 1. Session Directory Structure

```markdown
sessions/session-{number}/
├── .github/
│   ├── workflows/
│   │   ├── {number}-0-start-session.yml
│   │   ├── {number}-1-step-one.yml
│   │   ├── {number}-2-step-two.yml
│   │   └── ... (one per step)
│   └── steps/
│       ├── {number}-1.md
│       ├── {number}-2.md
│       └── ... (one per step)
├── README.md
└── starter-files/ (if needed)
```

### 2. Workflow Files

- **Start Session Workflow**: Triggers on repository creation/push, creates the initial issue
- **Step Progression Workflows**: Each step has a workflow that validates completion and advances to next step
- **Completion Workflow**: Handles session completion and cleanup

### 3. Step Markdown Files

- Clear, engaging instructions for each step
- Code examples and challenges appropriate to the difficulty level
- Success criteria and validation hints
- Progressive skill building

### 4. Session README

- Overview of the session
- Learning objectives
- Prerequisites
- Estimated completion time

## Key Requirements

### GitHub Skills Format Compliance

- Use the `skills/exercise-toolkit` action for consistency
- Follow the standard issue-based progression model
- Include proper workflow enablement/disablement logic
- Use template variables for customization

### Educational Design Principles

- **Scaffolding**: Each step builds on the previous
- **Active Learning**: Hands-on coding challenges, not just reading
- **Clear Success Criteria**: Learners know when they've completed each step
- **Contextual Help**: Provide hints and troubleshooting guidance
- **Real-world Relevance**: Use practical, applicable examples

### Technical Requirements

- All workflows must include proper permissions (contents: write, actions: write, issues: write)
- Use environment variables for step file references
- Include error handling and fallback scenarios
- Ensure workflows are properly sequenced and don't conflict

### Content Guidelines

- **Engaging Tone**: Friendly, encouraging, and supportive
- **Clear Instructions**: Step-by-step, unambiguous directions
- **Code Quality**: Follow best practices and include comments
- **Accessibility**: Consider different learning styles and experience levels

## Template Variables to Use

- `{{session-number}}`: The session number
- `{{session-title}}`: The session title
- `{{repo-name}}`: Repository name
- `{{username}}`: GitHub username
- `{{step-number}}`: Current step number

## Example Usage

```markdown
Please generate a complete session with the following details:
- Session Number: 3
- Session Title: "Advanced Code Generation with GitHub Copilot"
- Learning Objectives:
  * Generate complex functions using natural language prompts
  * Implement error handling patterns with Copilot assistance
  * Create comprehensive unit tests using AI suggestions
  * Optimize code performance with Copilot recommendations
- Difficulty Level: Advanced
- Prerequisites: Completion of Sessions 1-2, familiarity with JavaScript/Python
- Estimated Time: 45-60 minutes
- Focus Areas: Code Generation, Testing, Performance Optimization
- Number of Steps: 6
```

Generate all necessary files with proper GitHub Skills formatting, progressive difficulty, and engaging educational content.
