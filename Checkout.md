# Git Evolution: The Transition from `checkout` to `switch` and `restore`

In older versions of Git, the `checkout` command was a **"Swiss Army Knife"** — it did too many unrelated tasks, which often led to confusion.

To simplify the workflow, Git introduced two specialized commands:

- `git switch`
- `git restore`

---

## 1. The Legacy Command: `git checkout` (The "All-in-One")

Before the update, `checkout` was used for two completely different purposes:

### Branch Management
Moving between branches or creating new ones.

### File Recovery
Discarding local changes or restoring files from a specific commit.

### The Problem

If you had a **branch named `main`** and a **file named `main`**, Git could get confused about what you actually wanted to do.

---

# 2. The New Dedicated Commands (The Modern Way)

## A. `git switch` — Purpose: Navigating Branches

This command is strictly for **moving between branches**.  
It is safer and more intuitive.

### Switch to an existing branch

```bash
git switch <branch-name>

```
Create and switch to a new branch
git switch -c <new-branch-name>

-c stands for Create

B. git restore — Purpose: Undoing Changes

This command is specialized for manipulating your working tree and the staging area.

Discard local changes in a file
git restore <file-name>

Returns the file to its last committed state.

Unstage a file (Undo git add)
git restore --staged <file-name>

Moves the file out of the staged area back to your workspace.

Why should you use the new commands?
Clarity

The command names (switch, restore) explicitly describe what they do.

Safety

git switch prevents you from accidentally overwriting files while moving between branches.

Simplicity

You no longer need to remember complex flags or hacky ways to unstage files (like using reset).