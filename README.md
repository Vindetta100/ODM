# ODM - Organized Development Method

**Version:** 11.2 (Simplified Structure & Safe Upgrades)  
**Status:** Production Ready  
**License:** MIT

---

## Overview

ODM (Organized Development Method) is a comprehensive development protocol designed for AI-driven software development. It provides automated validation, compliance enforcement, and session management to ensure consistent code quality and architectural integrity across all development sessions.

### Key Features

✅ **Session Independence** - AI reads project documentation at every session start  
✅ **Automated Compliance Checking** - Interactive checklist verifies adherence to development rules  
✅ **Deletion Detection** - Tracks and warns about deleted files and dependencies  
✅ **Security Enforcement** - Guardian checks for hardcoded secrets and security violations  
✅ **Test Coverage Validation** - Ensures test coverage meets project thresholds  
✅ **Audit Trail** - Generates comprehensive validation reports for every session  
✅ **Language Agnostic** - Supports Python, Node.js, Rust, Go, and more

---

## Quick Start

### Installation

1. **Clone this repository:**
   ```bash
   git clone https://github.com/Vindetta100/ODM.git
   cd ODM
   ```

2. **Copy to your project:**
   ```bash
   cp -r .odm /path/to/your/project/
   cp ARCHITECTURE.md /path/to/your/project/  # Template
   cp CHANGELOG.md /path/to/your/project/     # Template
   ```

3. **Configure for your project:**
   ```bash
   cd /path/to/your/project
   # Edit .odm/odm.yaml to match your tech stack
   # Edit ARCHITECTURE.md to document your project
   ```

### Usage

**Start a development session:**
```bash
bash .odm/start.sh
```
- Syncs with remote repository
- Shows latest changelog and commits
- **Reminds AI to read critical documentation**
- Displays 6 key ODM rules

**End a development session:**
```bash
bash .odm/end.sh
```
- Runs Guardian security checks
- Analyzes file changes
- Prompts for ARCHITECTURE.md updates
- **Verifies ODM compliance (6 questions)**
- Collects session summary
- **Generates enhanced validation report**
- Updates CHANGELOG.md
- Commits and pushes changes

---

## What's New in v11.2

### 🔄 Simplified Structure & Safe Upgrades

**File organization improvements:**
- Moved `odm_ai_rules.md` to root (easier to find and edit)
- Moved `VALIDATION_REPORT.md` to root (single file, always overwrites)
- Removed `.odm/reports/` folder (no more clutter)

**New upgrade mechanism:**
- Added `upgrade.sh` script for safe ODM upgrades
- Automatic backup of project-specific files
- Preserves ARCHITECTURE.md, CHANGELOG.md, odm_ai_rules.md, etc.
- Only upgrades core scripts (start.sh, end.sh)
- See [UPGRADE_GUIDE.md](UPGRADE_GUIDE.md) for details

---

## What's New in v11.1

### 🎯 AI Rules Enforcement

**start.sh now explicitly instructs AI to:**
- Read ARCHITECTURE.md (single source of truth)
- Read odm_ai_rules.md (development rules)
- Review CHANGELOG.md (recent context)
- Remember 6 key ODM rules

**end.sh now includes:**
- 6-question ODM compliance checklist
- Enhanced validation report with compliance results
- Deletion detection for files and dependencies

### 📊 Enhanced Validation Report

**New Section 5: ODM AI Rules Compliance**
```markdown
- Modular Design: ✅ PASS / ⚠️ REVIEW NEEDED
- Separation of Concerns: ✅ PASS / ⚠️ REVIEW NEEDED
- API Versioning: ✅ PASS / N/A / ⚠️ REVIEW NEEDED
- Error Handling: ✅ PASS / ⚠️ REVIEW NEEDED
- Testing: ✅ PASS / ⚠️ REVIEW NEEDED
- Boy Scout Rule: ✅ PASS / ⚠️ REVIEW NEEDED
```

**New Section 6: Deleted Files & Dependencies Analysis**
- Lists all deleted files with warnings
- Tracks removed Python dependencies (requirements.txt)
- Tracks removed Node.js dependencies (package.json)
- Provides actionable warnings

---

## The 6 Core ODM Rules

### 1. 📦 Modular Design
- Single responsibility per module
- Keep files under 300 lines
- Clear separation of concerns

### 2. 🔀 Separation of Concerns
- Never mix business logic, data access, and presentation
- Separate layers: auth/api/db/services/utils

### 3. 🔗 API Versioning
- Always use `/api/v1/` prefixes
- RESTful methods
- Consistent error responses

### 4. ⚠️ Error Handling
- Explicit try/catch with logging
- User-friendly error messages
- Never expose internal details

### 5. 🧪 Testing
- Maintain or improve test coverage
- Unit tests for all modules
- Integration tests for critical paths

### 6. 🏕️ Boy Scout Rule
- Leave code cleaner than you found it
- Refactor confusing code
- Document complex decisions

---

## Repository Structure

```
ODM/
├── .odm/
│   ├── start.sh              # Session start script
│   ├── end.sh                # Session end script
│   ├── guardian.sh           # Security and validation checks
│   ├── upgrade.sh            # Upgrade script
│   └── odm.yaml              # Project configuration
├── ARCHITECTURE.md           # Project architecture documentation
├── CHANGELOG.md              # Session changelog
├── odm_ai_rules.md           # Development rules for AI
├── VALIDATION_REPORT.md      # Latest validation report (single file)
├── README.md                 # This file
├── UPGRADE_GUIDE.md          # Upgrade instructions
├── UPDATE_CHANGELOG.md       # Detailed change log for v11.1
├── QUICK_REFERENCE.md        # Quick start guide
└── IMPLEMENTATION_SUMMARY.md # Implementation details
```

---

## Documentation

### For Users
- **[QUICK_REFERENCE.md](QUICK_REFERENCE.md)** - Quick start guide with examples
- **[IMPLEMENTATION_SUMMARY.md](IMPLEMENTATION_SUMMARY.md)** - Complete implementation details

### For Developers
- **[UPDATE_CHANGELOG.md](UPDATE_CHANGELOG.md)** - Detailed technical change log
- **[odm_ai_rules.md](odm_ai_rules.md)** - AI development rules

### Templates
- **[ARCHITECTURE.md](ARCHITECTURE.md)** - Project architecture template
- **[CHANGELOG.md](CHANGELOG.md)** - Session changelog template

---

## The ODM Workflow

```
┌─────────────────────────────────────────────────────────┐
│  1. START SESSION                                       │
│     bash .odm/start.sh                                  │
│     → AI reads ARCHITECTURE.md                          │
│     → AI reads odm_ai_rules.md                          │
│     → AI sees 6 key rules                               │
└─────────────────────────────────────────────────────────┘
                          ↓
┌─────────────────────────────────────────────────────────┐
│  2. DEVELOPMENT WORK                                    │
│     → AI writes code                                    │
│     → AI applies ODM principles                         │
│     → Guardian checks run automatically                 │
└─────────────────────────────────────────────────────────┘
                          ↓
┌─────────────────────────────────────────────────────────┐
│  3. END SESSION                                         │
│     bash .odm/end.sh                                    │
│     → Guardian security checks                          │
│     → File change analysis                              │
│     → ARCHITECTURE.md update check                      │
│     → ODM compliance checklist (6 questions)            │
│     → Session summary collection                        │
│     → Validation report generation                      │
│     → CHANGELOG update                                  │
│     → Git commit and push                               │
└─────────────────────────────────────────────────────────┘
                          ↓
┌─────────────────────────────────────────────────────────┐
│  4. NEXT SESSION (Session Independence)                │
│     → Process repeats from step 1                       │
│     → AI reads rules again (no memory from last time)   │
└─────────────────────────────────────────────────────────┘
```

---

## Configuration

### odm.yaml

Configure ODM for your project:

```yaml
project:
  name: "Your Project Name"
  version: "1.0.0"

paths:
  sourceDirs:
    - "src"
    - "lib"
  
test:
  command: "pytest"
  coverageCmd: "pytest --cov=src --cov-report=term --cov-fail-under=80"

guardian:
  secretPatterns:
    - 'password.*=.*"[^"]{8,}"'
    - 'secret.*=.*"[^"]{8,}"'
    - 'key.*=.*"[^"]{8,}"'
```

---

## Requirements

### Required
- Bash shell (any recent version)
- Git (for version control and deletion detection)

### Optional
- `jq` (for Node.js dependency checking)
  - Install: `sudo apt-get install jq` (Ubuntu/Debian)
  - Install: `brew install jq` (macOS)

---

## Language Support

ODM is language-agnostic and supports:

- **Python** - pytest, black, flake8
- **Node.js** - jest/mocha, prettier, eslint
- **Rust** - cargo test, cargo fmt, clippy
- **Go** - go test, gofmt, golint
- **Others** - Easily configurable via odm.yaml

---

## Benefits

### Before ODM
❌ Inconsistent code quality across sessions  
❌ AI might skip best practices  
❌ No audit trail of compliance  
❌ Accidental deletions go unnoticed  
❌ Technical debt accumulates  

### After ODM
✅ Consistent code quality enforced  
✅ AI follows best practices every session  
✅ Complete audit trail in validation reports  
✅ Deletion warnings prevent mistakes  
✅ Technical debt minimized  

---

## Contributing

This repository is designed to evolve based on real-world usage. If you find a flaw or have an improvement:

1. **Open an issue** describing the problem or enhancement
2. **Submit a pull request** with your proposed changes
3. **Document the reasoning** behind the change

We refine the protocol every time we discover an improvement opportunity.

---

## Version History

### v11.2 (Current)
- Moved `odm_ai_rules.md` to root for easier access
- Moved `VALIDATION_REPORT.md` to root (single file, overwrites)
- Removed `.odm/reports/` folder
- Added `upgrade.sh` for safe ODM upgrades
- Added `UPGRADE_GUIDE.md` with comprehensive upgrade instructions
- Updated all references in scripts and documentation

### v11.1
- Added AI rules enforcement at session start
- Added ODM compliance checklist at session end
- Enhanced validation report with compliance results
- Added deletion detection for files and dependencies
- Improved documentation and quick reference guides

### v11.0
- Initial public release
- Guardian security checks
- Session management (start.sh, end.sh)
- ARCHITECTURE.md and CHANGELOG.md integration
- Language-agnostic tooling support

---

## License

MIT License - See LICENSE file for details

---

## Links

- **Repository:** https://github.com/Vindetta100/ODM
- **Issues:** https://github.com/Vindetta100/ODM/issues
- **Discussions:** https://github.com/Vindetta100/ODM/discussions

---

## Support

For questions, issues, or feature requests:
- Open an issue on GitHub
- Check existing documentation in the repository
- Review QUICK_REFERENCE.md for common use cases

---

**Built for AI-driven development. Refined through continuous iteration.**

