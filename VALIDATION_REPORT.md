# ODM Validation Report

## RULES

1. **ALWAYS OVERWRITE** - This file is regenerated at the end of every session
2. **PRESERVE TEMPLATE** - Never overwrite the RULES, TEMPLATE, or WARNING sections above the separator
3. **SINGLE FILE** - Only one validation report exists (no history, no versions)
4. **LATEST ONLY** - This report always reflects the most recent session validation
5. **NUMBERED SECTIONS** - All sections are numbered 1-8 so you can verify nothing was skipped

## TEMPLATE

```markdown
# ODM v12 - End-of-Task Validation Report

**Date**: YYYY-MM-DD HH:MM:SS
**Session**: X.X

---

## 1. Git Commits Summary
- Commit message 1
- Commit message 2

---

## 2. File Changes Overview
```
Files changed, insertions, deletions
```

---

## 3. Session Summary
- **ADDED:** [New features/files]
- **CHANGED:** [Modified files with line numbers]
- **FIXED:** [Bug fixes with specific locations]
- **COMMIT:** [Brief technical summary]

---

## 4. Validation Status
- Guardian Security Checks: ✅ PASSED / ❌ FAILED
- File Analysis: ✅ COMPLETED
- Changelog Update: ✅ COMPLETED
- Validation Report: ✅ GENERATED

---

## 5. ODM AI Rules Compliance
- **Modular Design:** ✅ PASS / ⚠️ REVIEW NEEDED
- **Separation of Concerns:** ✅ PASS / ⚠️ REVIEW NEEDED
- **API Versioning:** ✅ PASS / N/A / ⚠️ REVIEW NEEDED
- **Error Handling:** ✅ PASS / ⚠️ REVIEW NEEDED
- **Testing:** ✅ PASS / ⚠️ REVIEW NEEDED
- **Boy Scout Rule:** ✅ PASS / ⚠️ REVIEW NEEDED

---

## 6. AI Self-Analysis
- **Confidence Level:** X/10
- **What Went Well:** [What the AI did well in this session]
- **What Needs Improvement:** [What needs fixing or could be better]
- **Merge Recommendation:** merge-now / fix-first / needs-review

---

## 7. Alignment Verification
- **Commits vs Changelog:** ✅ ALIGNED / ⚠️ MISALIGNED
- **Files vs Descriptions:** ✅ ALIGNED / ⚠️ MISALIGNED
- **Undocumented Changes:** ✅ NONE / ⚠️ FOUND

---

## 8. Deleted Files & Dependencies Analysis

### Deleted Files
✅ No files were deleted / ⚠️ WARNING: X file(s) deleted

### Removed Dependencies
✅ No dependencies removed / ⚠️ WARNING: Dependencies removed

---
```

## HOW IT WORKS

When `end.sh` runs, it will:
1. **Prompt for 8 categories of information** (numbered 1-8)
2. **Generate the new report** with current session data
3. **Overwrite everything BELOW the separator** with the new report
4. **Preserve everything ABOVE the separator** (RULES, TEMPLATE, WARNING)

## VERIFICATION CHECKLIST

After end.sh completes, verify the report has ALL 8 numbered sections:

- [ ] **Section 1:** Git Commits Summary
- [ ] **Section 2:** File Changes Overview
- [ ] **Section 3:** Session Summary
- [ ] **Section 4:** Validation Status
- [ ] **Section 5:** ODM AI Rules Compliance
- [ ] **Section 6:** AI Self-Analysis (NEW)
- [ ] **Section 7:** Alignment Verification (NEW)
- [ ] **Section 8:** Deleted Files & Dependencies Analysis

**If any section number is missing, the AI skipped a step!**

---

⚠️ **WARNING: DO NOT MODIFY ANYTHING ABOVE THIS LINE** ⚠️

**NO changes, edits, additions, or deletions are allowed above this warning.**
**This protects the RULES and TEMPLATE from being overwritten.**
**The content below this line will be completely replaced at the end of each session.**

---

## Latest Validation Report

[The latest validation report will be generated here by end.sh]

**Status:** No session completed yet. Run `bash .odm/end.sh` to generate the first validation report.
