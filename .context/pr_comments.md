# PR Review - Database migration rollback engine (by Meera)

## Reviewer: Amit Desai
---

**Overall:** Good foundation but critical bugs need fixing before merge.

### `migrationEngine.py`

> **Bug #1:** Rollback executes migrations in wrong order since it runs forward instead of reversing
> This is the higher priority fix. Check the logic carefully and compare against the design doc.

### `rollbackManager.py`

> **Bug #2:** Version tracking does not update after rollback so re-running applies wrong migration
> This is more subtle but will cause issues in production. Make sure to add a test case for this.

---

**Meera**
> Acknowledged. I have documented the issues for whoever picks this up.
