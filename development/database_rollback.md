# ✅ SQL Transactions: COMMIT & ROLLBACK (Quick Reference)

***

## 🔹 What is a Transaction?

A **transaction** is a group of SQL operations treated as **one unit of work**.

It ensures:

* ✅ Either **all changes happen**
* ✅ Or **none of them happen**

***

## 🔹 COMMIT — Save Changes Permanently

```sql
COMMIT;
```

✅ Meaning:

* All changes made in the transaction are **saved permanently**
* You **cannot undo** them afterward

### Example

```sql
BEGIN;

UPDATE act_hi_varinst
SET text_ = 'new_user'
WHERE proc_inst_id_ = '123'
  AND name_ = 'createdUser';

COMMIT;
```

👉 After `COMMIT`, the new value is **final**

***

## 🔹 ROLLBACK — Undo Changes

```sql
ROLLBACK;
```

✅ Meaning:

* All changes made since `BEGIN` are **reverted**
* Database returns to the **previous state**

### Example

```sql
BEGIN;

UPDATE act_hi_varinst
SET text_ = 'wrong_value'
WHERE proc_inst_id_ = '123';

ROLLBACK;
```

👉 Result:

* ❌ Update is undone
* ✅ Data remains unchanged

***

## 🔹 Safe Update Workflow

```sql
BEGIN;

-- Step 1: Check current value
SELECT text_
FROM act_hi_varinst
WHERE proc_inst_id_ = '123'
  AND name_ = 'createdUser';

-- Step 2: Perform update
UPDATE act_hi_varinst
SET text_ = 'new_value'
WHERE proc_inst_id_ = '123'
  AND name_ = 'createdUser';

-- Step 3: Verify updated value
SELECT text_
FROM act_hi_varinst
WHERE proc_inst_id_ = '123'
  AND name_ = 'createdUser';

-- Step 4: Final decision
COMMIT;    -- ✅ if correct
-- or
ROLLBACK;  -- ❌ if wrong
```

***

## 🔹 Important Rules

### 1. COMMIT is final

* Once committed → ❌ cannot rollback
* Only way back = another update

***

### 2. ROLLBACK works only before COMMIT

* After commit → ❌ no undo possible

***

### 3. Transactions are session-based

* Your session → sees uncommitted changes ✅
* Other sessions → ❌ see changes only after COMMIT

***

### 4. Auto-commit mode (⚠️ important)

Many tools enable auto-commit:

* Each query is saved automatically
* `ROLLBACK` will NOT work

👉 Disable if needed (MySQL example):

```sql
SET autocommit = 0;
```

***

## 🔹 Simple Analogy

| Action   | Meaning            |
| -------- | ------------------ |
| BEGIN    | Start editing      |
| UPDATE   | Make changes       |
| COMMIT   | Save changes 💾    |
| ROLLBACK | Undo everything ↩️ |

***

## ✅ Best Practice

Always follow:

1. `BEGIN`
2. `SELECT` (check current data)
3. `UPDATE` / `DELETE`
4. `SELECT` (verify result)
5. `COMMIT` or `ROLLBACK`

***

💡 Tip: In production, always **preview with SELECT and COUNT(\*) before updating** to avoid mistakes.

***
