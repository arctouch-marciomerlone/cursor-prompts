# AI Task Management Assistant Prompts

A comprehensive set of AI assistant prompts designed to streamline software development workflows from task initialization to code review and documentation.

## 🎯 Overview

This repository contains three specialized AI assistant prompts that work together to provide a complete development workflow:

- **Task Init Assistant** - Initialize new tasks with branch creation and planning
- **Code Review Assistant** - Comprehensive code analysis and review documentation
- **Task Wrapper Assistant** - Final documentation and PR preparation

## 📋 Available Prompts

### 1. Task Init Assistant (`task-init-assistant.txt`)

**Purpose**: Initialize new development tasks with proper planning and branch setup

**What it does**:

- Creates descriptive feature branches following naming conventions
- Analyzes existing codebase patterns and architecture
- Generates comprehensive implementation plans (PLAN-{TASK-CODE}.md)
- Provides specific Cursor prompts for implementation
- Sets up development environment safely

**When to use**: At the start of any new feature, bug fix, or development task

### 2. Code Review Assistant (`code-review.txt`)

**Purpose**: Perform comprehensive code analysis and generate review documentation

**What it does**:

- Analyzes code changes across 13+ quality criteria
- Supports multiple input methods (branches, PR URLs, auto-detection)
- Generates detailed review reports (REVIEW-{TASK-CODE}.md)
- Categorizes issues by severity (Critical/Major/Minor/Enhancement)
- Identifies positive patterns and highlights

**When to use**: Before merging code, during code reviews, or for quality assessments

### 3. Task Wrapper Assistant (`task-wrapper.txt`)

**Purpose**: Finalize tasks with comprehensive documentation and PR preparation

**What it does**:

- Integrates with code review for comprehensive analysis
- Generates semantic commit strategies
- Creates detailed PR documentation (PR-{TASK-CODE}.md)
- Includes build status, linting results, and issue summaries
- Provides merge-ready documentation

**When to use**: When completing a task and preparing for code review/merge

## 🚀 Quick Start

### Prerequisites

- AI assistant that supports custom prompts (Claude, ChatGPT, etc.)
- Git repository
- Development environment (Node.js recommended for build/lint commands)

### Basic Workflow

1. **Initialize Task**

   ```
   Use: task-init-assistant.txt
   Input: Task code, description, optional base branch
   Output: PLAN-{TASK-CODE}.md + feature branch
   ```

2. **Implement Changes**

   ```
   Follow the generated PLAN-{TASK-CODE}.md
   Use suggested Cursor prompts for development
   ```

3. **Review Code**

   ```
   Use: code-review.txt
   Input: Branch names or PR URL
   Output: REVIEW-{TASK-CODE}.md
   ```

4. **Finalize Task**
   ```
   Use: task-wrapper.txt
   Input: Task code and description
   Output: PR-{TASK-CODE}.md + commit strategy
   ```

## 📖 Detailed Usage

### Task Init Assistant

**Input Format**:

```
Task Code: FEAT-123
URL: https://github.com/org/repo/issues/123
Description: Add user authentication system
Base Branch: main (optional)
```

**Example Output**:

- Branch: `mm/FEAT-123/add-user-auth`
- File: `PLAN-FEAT-123.md`

### Code Review Assistant

**Input Options**:

```
Option 1: Two branch names
"feature/user-auth" "main"

Option 2: PR URL
"https://github.com/org/repo/pull/123"

Option 3: Single branch (auto-detects base)
"feature/user-auth"

Option 4: Auto-detection (uses current branch)
(no input - detects current feature branch)
```

**Example Output**:

- File: `REVIEW-FEAT-123.md`

### Task Wrapper Assistant

**Input Format**:

```
Task Code: FEAT-123
URL: https://github.com/org/repo/issues/123
Description: Add user authentication system
Base Branch: main (optional)
```

**Example Output**:

- File: `PR-FEAT-123.md`
- Includes git strategy and PR description

## 🏗️ File Naming Convention

All generated files use task codes to enable parallel development:

```
PLAN-{TASK-CODE}.md    # Implementation plan
REVIEW-{TASK-CODE}.md  # Code review documentation
PR-{TASK-CODE}.md      # Pull request documentation
```

**Benefits**:

- Work on multiple tasks simultaneously
- No file conflicts between different tasks
- Clear task identification
- Easy task switching

## 🔄 Workflow Examples

### Complete Feature Development

```bash
# 1. Initialize task
Input: FEAT-456, "Implement dark mode toggle"
Output: Branch mm/FEAT-456/dark-mode-toggle + PLAN-FEAT-456.md

# 2. Develop feature (follow PLAN-FEAT-456.md)
# ... implementation work ...

# 3. Review code
Input: "mm/FEAT-456/dark-mode-toggle" "main"
Output: REVIEW-FEAT-456.md

# 4. Finalize task
Input: FEAT-456, "Implement dark mode toggle"
Output: PR-FEAT-456.md + semantic commit strategy
```

### Bug Fix Workflow

```bash
# 1. Initialize bug fix
Input: BUG-789, "Fix login validation error"
Output: Branch mm/BUG-789/fix-login-validation + PLAN-BUG-789.md

# 2. Fix bug (follow plan)
# ... fix implementation ...

# 3. Review changes
Input: Auto-detection (current branch)
Output: REVIEW-BUG-789.md

# 4. Prepare PR
Input: BUG-789, "Fix login validation error"
Output: PR-BUG-789.md
```

## ⚙️ Configuration

### Branch Naming Pattern

```
mm/<task-code>/descriptive-name

Examples:
mm/FEAT-123/add-user-auth
mm/BUG-456/fix-validation
mm/CHORE-789/update-deps
```

### Semantic Commit Types

- `feat`: New features
- `fix`: Bug fixes
- `refactor`: Code restructuring
- `test`: Adding/updating tests
- `docs`: Documentation changes
- `chore`: Maintenance tasks
- `remove`: Removing code/files

## 🛡️ Safety Features

### Mode Enforcement

Each assistant operates in a specific mode with clear boundaries:

- **TASK INIT MODE**: Planning only, limited git operations
- **CODE REVIEW MODE**: Analysis only, read-only operations
- **TASK WRAP MODE**: Documentation only, no code changes

### Validation Requirements

- Always confirms working directory and project context
- Requires user confirmation for critical operations
- Uses absolute paths for file creation
- Prevents accidental overwrites

### Error Prevention

- Context validation before proceeding
- Working directory confirmation
- Branch existence verification
- Build and linting validation

## 📊 Generated Documentation

### PLAN-{TASK-CODE}.md Structure

```markdown
# Task Overview

# Technical Analysis

# Implementation Strategy

# Architecture Considerations

# Dependencies and Requirements

# Validation Checklist

# Agent Execution Rules

# Recommended Cursor Prompts
```

### REVIEW-{TASK-CODE}.md Structure

```markdown
# Summary (build status, files changed)

# Prioritized Issues (Critical/Major/Minor/Enhancement)

# Highlights (positive findings)
```

### PR-{TASK-CODE}.md Structure

```markdown
# Git Strategy (semantic commits)

# PR Description (with code review integration)

# Checklist items

# Demo and additional notes
```

## 🎯 Best Practices

### Task Initialization

- Provide clear, descriptive task descriptions
- Use consistent task codes
- Include relevant URLs or ticket links
- Specify base branch when not using default

### Code Review

- Run reviews before merging
- Address Critical and Major issues
- Use auto-detection for convenience
- Include task codes for better organization

### Task Finalization

- Ensure all tests pass before wrapping
- Review generated commit strategy
- Complete all checklist items
- Include demo information when relevant

## 🤝 Contributing

When modifying prompts:

1. Maintain the DRY principle (shared configuration)
2. Follow the established mode enforcement patterns
3. Preserve safety validations
4. Update documentation accordingly
5. Test with various input scenarios

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🆘 Troubleshooting

### Common Issues

**"Wrong project directory"**

- Ensure you're in the correct repository
- Confirm working directory with `pwd`

**"Branch already exists"**

- Check existing branches with `git branch -a`
- Use different descriptive names

**"Build/lint failures"**

- Address issues before proceeding
- Check tool availability (`npm`, `eslint`, etc.)

**"File overwrite warnings"**

- Different task codes prevent conflicts
- Confirm task code accuracy

### Support

For issues or questions:

1. Check the prompt documentation
2. Verify input format requirements
3. Ensure proper mode enforcement
4. Review error prevention guidelines
