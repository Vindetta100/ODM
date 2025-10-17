# ODM v11 - Official Development Methodology

**Version**: 11.0  
**Date**: October 15, 2025  
**Purpose**: Simplified development workflow with automated changelog and file cleanup

## What's Included

- `.odm/start.sh` - Session initialization script
- `.odm/end.sh` - Task completion script with file cleanup
- `.odm/odm.yaml` - ODM configuration file
- `.odm/odm_ai_rules.md` - AI agent rules and guidelines
- `.pre-commit-config.yaml` - Pre-commit hooks configuration

## Quick Start

### 1. Extract to Your Project

```bash
# Extract this package to your project's root directory
unzip odm-v11.zip -d /path/to/your/project
```

### 2. Install Pre-commit Hooks

```bash
pip install pre-commit
pre-commit install
```

### 3. Configure .odm/odm.yaml

Edit `.odm/odm.yaml` to match your project structure:

```yaml
paths:
  sourceDirs: ["src/", "lib/", "app/"]  # Your source directories
  critical: ["README.md", "CHANGELOG.md"]  # Critical files
```

### 4. Set Up CHANGELOG.md

Create a `CHANGELOG.md` file in your project root with this structure:

```markdown
# Changelog

## RULES

1. **APPEND ONLY** - Never edit or remove existing entries
2. **NO MODIFICATIONS** - Only add new sessions at the top under "Recent Sessions"
3. **USE TEMPLATE** - Follow the exact format below for each session
4. **BE SPECIFIC** - Include file names and line numbers where applicable

## TEMPLATE

\`\`\`markdown
### Session X.X (YYYY-MM-DD)

- **ADDED:** [New features/files]
- **CHANGED:** [Modified files with line numbers]
- **FIXED:** [Bug fixes with specific locations]
- **COMMIT:** [Brief technical summary]
\`\`\`

---

⚠️ **WARNING: DO NOT MODIFY ANYTHING ABOVE THIS LINE** ⚠️

**NO changes, edits, additions, or deletions are allowed above this warning.**
**This protects the RULES and TEMPLATE from being overwritten.**
**Only add new session entries below in the "Recent Sessions" section.**

---

## Recent Sessions

[Your sessions will be added here]
```

## Usage

### Starting a New Session

At the beginning of each new chat/development session:

```bash
bash .odm/start.sh
```

**What it does:**
- Syncs with remote repository
- Shows latest changelog entry
- Displays recent commits
- Shows current status

### Ending a Session

When completing work:

```bash
bash .odm/end.sh
```

**What it does:**
1. Runs validation checks
2. Lists all new files created
3. Detects cleanup candidates (temp files, backups)
4. Prompts for session information
5. Allows you to specify files to delete
6. Updates CHANGELOG.md automatically
7. Commits all changes
8. Pushes to remote

## Features

### Automated File Cleanup

The `end.sh` script automatically detects potential cleanup candidates:
- `*_test.*`, `*_backup.*`, `*_old.*`, `*_temp.*`
- `*.tmp`, `*.bak`, `*~`, `*.swp`
- `.DS_Store`

You'll be prompted to specify which files to delete.

### Protected CHANGELOG

The CHANGELOG.md has a protected section at the top with rules and template. The warning line prevents accidental modifications to these critical sections.

### Pre-commit Hooks

Automated quality checks before every commit:
- Trailing whitespace removal
- End-of-file fixing
- YAML validation
- Large file detection
- Secret detection (prevents credential leaks)
- Black (Python formatting)
- Flake8 (Python linting)

## Session Numbering

Format: `X.Y`
- **X** = Major phase (1, 2, 3, etc.)
- **Y** = Session within that phase (0, 1, 2, etc.)

Examples:
- `1.0` - First session of Phase 1
- `1.1` - Second session of Phase 1
- `2.0` - First session of Phase 2

## Customization

### .odm/odm.yaml

Customize for your project:

```yaml
version: "11.0"
projectMode: "enterprise"

test:
  testCmd: "npm test"  # or "pytest" for Python
  coverageCmd: "npm run coverage"

paths:
  reportDir: ".odm/reports"
  sourceDirs: ["src/", "lib/", "app/"]

deployment:
  remoteName: "origin"
  mainBranch: "main"

integrity:
  fileGlobs: ["*.py", "*.md", "*.json", "*.js", "*.ts", "*.rs"]
  critical: ["README.md", "CHANGELOG.md", ".odm/odm.yaml"]
```

### Pre-commit Hooks

Edit `.pre-commit-config.yaml` to add or remove hooks based on your tech stack.

## Tech Stack Agnostic

ODM v11 works with any technology stack. The scripts adapt to your project's specific requirements.

## Requirements

- Git
- Bash
- Python 3.x (for pre-commit)
- pip

## Support

For issues or questions, refer to the ODM documentation in your project's `docs/` directory.

---

**ODM v11** - Keeping your development workflow clean and organized.
