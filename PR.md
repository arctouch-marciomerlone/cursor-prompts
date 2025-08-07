# Git Strategy

```bash
git add README.md task-init-assistant.txt code-review.txt task-wrapper.txt && git commit -m "feat: add ai task management assistant prompts" && \
git add . && git commit -m "docs: add comprehensive readme with usage instructions"
```

# PR Description

# [INIT] AI Task Management Assistant Prompts

## Changes Description

Initial repository setup with comprehensive AI assistant prompts for software development workflows. This includes three specialized assistants that work together to provide a complete development lifecycle from task initialization to code review and documentation.

**Ticket:** Initial commit - no external ticket

## Changelog

- **feat:** AI Task Management Assistant Prompts system
- **docs:** Comprehensive README with usage instructions and examples

## Key Changes

### Core Prompts

- `task-init-assistant.txt` - Task initialization with branch creation and planning
- `code-review.txt` - Comprehensive code analysis and review documentation
- `task-wrapper.txt` - Task finalization with PR preparation and documentation

### Documentation

- `README.md` - Complete usage guide with examples, workflows, and troubleshooting
- Detailed prompt documentation and configuration instructions
- Workflow examples for feature development and bug fixes

### Features

- **DRY Architecture**: Shared configuration sections across all prompts
- **Task Code Integration**: Filename patterns supporting parallel development
- **Mode Enforcement**: Clear boundaries and safety validations
- **Auto-Detection**: Intelligent branch and context detection
- **Comprehensive Analysis**: 13+ code review criteria with severity categorization

## Checklist

- [x] All prompt files are properly structured and follow DRY principles
- [x] README documentation is comprehensive and includes examples
- [x] File naming conventions are clearly documented
- [x] Safety features and mode enforcement are explained
- [x] Workflow examples are provided for common scenarios
- [x] Troubleshooting section addresses common issues
- [x] Best practices are documented for each assistant
- [x] Configuration options are clearly specified

## Demo

This is an initial repository setup. The demo would involve:

1. Using `task-init-assistant.txt` to initialize a new task
2. Following the generated plan for implementation
3. Running `code-review.txt` for analysis
4. Using `task-wrapper.txt` for final documentation

## Additional Notes

- All prompts support task code filename patterns (e.g., `PLAN-ABC-123.md`)
- Branch naming follows `mm/<task-code>/descriptive-name` pattern
- Semantic commit types are enforced: feat, fix, refactor, test, docs, chore, remove
- Each assistant operates in a specific mode with clear safety boundaries
- Auto-detection features reduce manual input while maintaining user control
- Generated documentation includes build status, linting results, and comprehensive analysis
