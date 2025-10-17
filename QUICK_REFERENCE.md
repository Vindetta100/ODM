# ODM v11.1 Quick Reference Guide

## What Changed?

### ✅ start.sh - NEW Section #5
**AI Rules Reading Reminder**

When you run `bash .odm/start.sh`, you'll now see:
```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
📚 AI: REQUIRED READING BEFORE STARTING WORK
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

⚠️  SESSION INDEPENDENCE PRINCIPLE: Start from zero trust

   MUST READ (in order):
   1. 📖 ARCHITECTURE.md
   2. 📋 .odm/odm_ai_rules.md
   3. 📝 CHANGELOG.md

   KEY RULES TO REMEMBER:
   • Modular Design: Single responsibility per module (< 300 lines)
   • Separation of Concerns: Never mix logic/data/presentation
   • API Versioning: Always use /api/v1/ prefixes
   • Zero-Trust Secrets: Never hardcode secrets
   • Testing: Maintain or improve test coverage
   • Boy Scout Rule: Leave code cleaner than you found it
```

---

### ✅ end.sh - NEW Section #7
**ODM AI Rules Compliance Checklist**

When you run `bash .odm/end.sh`, you'll be asked:

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
✅ ODM AI RULES COMPLIANCE CHECKLIST
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

1. 📦 MODULAR DESIGN
   Did you ensure all modules follow single responsibility?
   Are all files < 300 lines?
   [yes/no] > 

2. 🔀 SEPARATION OF CONCERNS
   Did you separate business logic, data access, and presentation?
   No mixing of auth/api/db/services/utils layers?
   [yes/no] > 

3. 🔗 API VERSIONING
   Did you use /api/v1/ prefixes for all API endpoints?
   [yes/no/not-applicable] > 

4. ⚠️  ERROR HANDLING
   Did you implement explicit try/catch with logging?
   Are error messages user-friendly (no internal exposure)?
   [yes/no] > 

5. 🧪 TESTING
   Did you maintain or improve test coverage?
   [yes/no] > 

6. 🏕️  BOY SCOUT RULE
   Did you leave the code cleaner than you found it?
   [yes/no] > 
```

---

### ✅ Validation Report - NEW Sections 5 & 6

**Section 5: ODM AI Rules Compliance**
```markdown
## 5. ODM AI Rules Compliance
- **Modular Design:** ✅ PASS
- **Separation of Concerns:** ✅ PASS
- **API Versioning:** N/A
- **Error Handling:** ✅ PASS
- **Testing:** ✅ PASS
- **Boy Scout Rule:** ✅ PASS
```

**Section 6: Deleted Files & Dependencies Analysis**
```markdown
## 6. Deleted Files & Dependencies Analysis

### Deleted Files
⚠️  WARNING: 2 file(s) were deleted in this session:
```
src/old_module.py
config/deprecated.yaml
```
**Action Required:** Verify these deletions were intentional.

### Removed Dependencies

#### Python (requirements.txt)
⚠️  WARNING: Dependencies removed from requirements.txt:
```
flask-cors==3.0.10
requests==2.28.0
```
**Action Required:** Verify these removals were intentional.

#### Node.js (package.json)
✅ No Node.js dependencies were removed.
```

---

## How to Use

### For AI Agents

**Every session start:**
1. Run `bash .odm/start.sh`
2. **READ** the three documents as instructed
3. Keep the 6 key rules in mind while coding

**Every session end:**
1. Run `bash .odm/end.sh`
2. Answer ARCHITECTURE.md update question
3. **Answer all 6 compliance questions honestly**
4. Provide session summary (ADDED, CHANGED, FIXED, COMMIT)
5. Review validation report warnings
6. Specify files to delete

**The validation report is saved to:** `.odm/reports/VALIDATION_REPORT.md`

---

## Key Benefits

### 🎯 Enforces Best Practices
- AI must read rules at every session start
- Checklist creates accountability at session end

### 🛡️ Catches Mistakes
- Deletion detection prevents accidental file/dependency removal
- Compliance warnings surface issues before commit

### 📊 Provides Audit Trail
- Validation report permanently records compliance status
- Can review adherence history across sessions

### 🔄 Creates Learning Loop
1. **Start:** Read rules → internalize principles
2. **Work:** Write code → apply principles
3. **End:** Verify adherence → reinforce learning
4. **Next session:** Repeat (Session Independence)

---

## What Didn't Change

✅ **guardian.sh** - No changes (still enforces secrets, testing, files)  
✅ **odm_ai_rules.md** - No changes (rules remain the same)  
✅ **ARCHITECTURE.md** - No changes (documentation unchanged)  
✅ **All other files** - Untouched

---

## Installation

### Option 1: Replace Files
```bash
# Backup current scripts
cp .odm/start.sh .odm/start.sh.backup
cp .odm/end.sh .odm/end.sh.backup

# Copy updated scripts
cp [updated-package]/.odm/start.sh .odm/start.sh
cp [updated-package]/.odm/end.sh .odm/end.sh

# Test
bash .odm/start.sh
bash .odm/end.sh
```

### Option 2: Extract Full Package
```bash
# Extract the updated ODM package
unzip odm-v11-updated.zip

# Copy to your repository
cp -r odm-v11-updated/.odm/* your-repo/.odm/

# Test
cd your-repo
bash .odm/start.sh
```

---

## Troubleshooting

**Q: Node.js dependency checking not working?**  
A: Install `jq`: `sudo apt-get install jq`

**Q: Deletion detection showing errors?**  
A: Requires git history. May not work in brand new repos.

**Q: Checklist questions not appearing?**  
A: Verify you're running the updated end.sh file.

---

## Summary

This update transforms ODM v11 from passive documentation into active enforcement:

- **Before:** AI might or might not read the rules
- **After:** AI MUST read rules at start AND verify compliance at end

- **Before:** No record of whether AI followed best practices
- **After:** Permanent audit trail in validation report

- **Before:** Accidental deletions might go unnoticed
- **After:** Explicit warnings for all deletions and dependency changes

**Result:** Consistent code quality, reduced technical debt, fewer production issues.

