# Day 24 – Advanced Git

---

## 🔹 Task 1 – Git Merge

### Fast-Forward Merge
- Happens when main branch has not moved ahead.
- Git just moves the branch pointer forward.
- No new merge commit is created.

Command:
```bash
git merge feature-branch
```
### Merge Commit
  - Happens when both branches have new commits.
  - Git creates a new merge commit.
  - History shows branch structure.
### Merge Conflict
  - Happens when same line is changed in both branches.
  - Git cannot decide which change to keep.
  - We must resolve manually.

#### After resolving:
`
git add .
git commit -m "resolve conflict"
`
##  🔹 Task 2 – Git Rebase
### What Rebase Does
  - Takes commits from feature branch.
  - Replays them on top of main.
  - Creates clean linear history.
  - Rewrites commit hashes.

#### Command:

`git rebase main`

Merge vs Rebase

Merge:
  - Keeps branch structure.
  - Creates merge commit.

Rebase:
  - Cleaner history.
  -No merge commit.

Changes commit history.

Important Rule

Never rebase commits that are already pushed and shared.

### 🔹 Task 3 – Squash Merge
#### What Squash Does
  - Combines multiple commits into one.
  - Keeps main branch clean.

#### Command:

`git merge --squash feature-branch
git commit -m "final feature commit"
`

#### Trade-off:
_- Cleaner history.
 - But detailed commits are lost.

### 🔹 Task 4 – Git Stash

#### What is Stash?
  - Temporarily saves uncommitted changes.
  - Lets you switch branches safely.

Commands:

```
git stash
git stash list
git stash apply
git stash pop
```

Difference:
- apply → keeps stash
- pop → removes stash

### 🔹 Task 5 – Cherry Pick
#### What is Cherry-Pick?
  -Copies a specific commit to another branch.

Command:

```
git cherry-pick <commit-hash>
```

Used for:
  -  Hotfix
  - Backporting fixes

Risk:
  - Conflicts

Duplicate commits if not careful

Useful Command
```
git log --oneline --graph --all
```
