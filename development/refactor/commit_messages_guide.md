# 📝 Commit Message Guide

A good commit message should answer:

- **What changed?**
- **Why did it change?** (optional in body)
- **Can someone understand this after 6 months?**

---

<details>
<summary><strong>📌 Commit Message Format</strong></summary>

```text
<type>: <short description>

[optional body]

[optional footer]
```

Example:

```text
feat: add process instance purge API

Add an admin endpoint to permanently remove runtime and
historical data for orphaned process instances.

The endpoint is restricted to administrators and performs
validation before cleanup.
```

</details>

---

# Commit Types

<details>
<summary><strong>✨ feat - New Feature</strong></summary>

Use when introducing new functionality.

Examples:

```text
feat: add JWT authentication

feat: support CSV export

feat: implement websocket notifications

feat: add Redis cache layer

feat: allow bulk rule deletion

feat: add process purge API

feat: support dark mode

feat: introduce role-based authorization
```

</details>

---

<details>
<summary><strong>🐞 fix - Bug Fix</strong></summary>

Use when correcting incorrect behavior.

Examples:

```text
fix: prevent null pointer during login

fix: handle empty request body

fix: resolve memory leak in scheduler

fix: avoid duplicate process deletion

fix: correct timezone conversion

fix: validate invalid email address

fix: retry database connection on timeout

fix: prevent race condition during deployment
```

</details>

---

<details>
<summary><strong>♻️ refactor - Code Improvement</strong></summary>

No functionality changes.

Examples:

```text
refactor: simplify authentication service

refactor: extract validation into helper class

refactor: replace nested loops with hashmap lookup

refactor: split large controller into smaller services

refactor: improve dependency injection

refactor: remove duplicated business logic
```

</details>

---

<details>
<summary><strong>⚡ perf - Performance Improvement</strong></summary>

Examples:

```text
perf: reduce database queries

perf: optimize Redis serialization

perf: improve query execution time

perf: cache frequently accessed rules

perf: reduce API response latency

perf: batch insert audit records
```

</details>

---

<details>
<summary><strong>🧪 test - Testing</strong></summary>

Examples:

```text
test: add unit tests for user service

test: cover process cleanup edge cases

test: add integration tests for authentication

test: increase repository test coverage

test: mock Kafka producer
```

</details>

---

<details>
<summary><strong>📚 docs - Documentation</strong></summary>

Examples:

```text
docs: update installation guide

docs: add API examples

docs: improve README

docs: document environment variables

docs: explain deployment process
```

</details>

---

<details>
<summary><strong>🔧 chore - Maintenance</strong></summary>

Examples:

```text
chore: update dependencies

chore: remove unused imports

chore: upgrade Java version

chore: clean build artifacts

chore: rename configuration files

chore: update editorconfig
```

</details>

---

<details>
<summary><strong>🏗 build - Build System</strong></summary>

Examples:

```text
build: upgrade Gradle

build: migrate Maven plugins

build: update Docker image

build: configure artifact publishing
```

</details>

---

<details>
<summary><strong>🚀 ci - Continuous Integration</strong></summary>

Examples:

```text
ci: add GitHub Actions workflow

ci: improve deployment pipeline

ci: enable code coverage

ci: cache Gradle dependencies

ci: fix Jenkins pipeline
```

</details>

---

<details>
<summary><strong>🎨 style - Formatting Only</strong></summary>

Examples:

```text
style: apply code formatter

style: fix indentation

style: reorder imports

style: remove trailing whitespace
```

</details>

---

<details>
<summary><strong>⏪ revert - Revert Changes</strong></summary>

Examples:

```text
revert: revert websocket implementation

revert: undo authentication changes

revert: rollback cache optimization
```

</details>

---

# Examples by Scenario

<details>
<summary><strong>🐛 Bug Fixes</strong></summary>

```text
fix: prevent duplicate user creation

fix: resolve login timeout

fix: handle null workflow definition

fix: correct SQL pagination

fix: avoid deadlock during cleanup
```

</details>

---

<details>
<summary><strong>✨ Features</strong></summary>

```text
feat: add user profile page

feat: implement email notifications

feat: support bulk upload

feat: add GraphQL endpoint

feat: introduce activity dashboard
```

</details>

---

<details>
<summary><strong>♻️ Refactoring</strong></summary>

```text
refactor: extract notification service

refactor: simplify rule validation

refactor: improve package structure

refactor: replace switch with strategy pattern

refactor: split service into smaller components
```

</details>

---

# Writing Good Commit Messages

✅ Good

```text
fix: prevent duplicate process deletion

feat: add rule export endpoint

refactor: simplify cache initialization

perf: reduce database calls during login

docs: document Docker setup
```

❌ Bad

```text
fixed

changes

done

update

misc

bug

working

new code

final final

latest
```

---

# Use Imperative Mood

Write as if completing the sentence:

> This commit will...

✅

```text
fix: remove duplicate records

feat: add pagination

refactor: simplify validation

docs: update README
```

❌

```text
fixed duplicate records

added pagination

refactored validation

updated README
```

---

# Commit Body

Use a body when the reason isn't obvious.

```text
fix: prevent duplicate process deletion

A race condition allowed multiple delete requests to
execute simultaneously.

Use a database lock to ensure only one cleanup operation
runs per process instance.
```

---

# Footer

Useful for issue tracking.

```text
fix: handle invalid token

Closes #143
```

```text
feat: add websocket support

Refs #89
```

---

# Tips

- Keep the title under **72 characters**
- One commit = One logical change
- Explain **what** changed
- Use the body for **why**
- Prefer clarity over cleverness
- Follow Conventional Commits consistently

---

# Quick Cheat Sheet

| Type | Purpose |
|------|---------|
| feat | New feature |
| fix | Bug fix |
| refactor | Internal code improvement |
| perf | Performance optimization |
| docs | Documentation |
| test | Tests |
| style | Formatting only |
| chore | Maintenance |
| build | Build system |
| ci | CI/CD |
| revert | Undo previous commit |
