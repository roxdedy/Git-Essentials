# Quick Repository Setup

This document covers the minimum steps required to initialize or clone a Git repository and make a first commit. It is not a Git tutorial.

## One-Time Global Configuration

Run once per machine (or user account).

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
git config --global init.defaultBranch main
git config --global color.ui true          # Enable colored output for better readability
```

### Optional: Edit config file directly

To open your global Git configuration file in your default editor:

```bash
git config --global --edit
```

## Create a New Repository

```bash
git init
git status                  # verify empty repository
echo "# Project Title" >> README.md
git add README.md
git commit -m "Initial commit"
```

## Clone an Existing Repository

```bash
git clone https://github.com/username/repo.git
cd repo
git status                  # verify clean working tree
```

## Make a First Commit (in an existing repository)

```bash
git status                  # see current changes
git add <files>             # or git add . to stage everything
git commit -m "Descriptive commit message"
```

## Amend the Last Commit (local only)

Use only on commits that have **not** been pushed to a shared branch.

```bash
# Fix message or add forgotten changes to the last commit
git add <forgotten-files>   # if needed
git commit --amend --no-edit   # Keep current message
# or
git commit --amend             # Opens editor to edit message
```

**Warning**: Never amend commits already pushed to shared branches (use `git revert` instead).

## Optional Configuration (team-dependent)

```bash
# Set preferred editor (examples)
git config --global core.editor "code --wait"      # VS Code
git config --global core.editor "vim"              # Vim
git config --global core.editor "nano"             # Nano

# Basic line ending handling (common on cross-platform teams)
git config --global core.autocrlf input            # macOS/Linux recommendation
# git config --global core.autocrlf true           # Windows alternative
```

Notes:

- Use HTTPS or SSH URLs depending on your authentication setup.
- Commit messages should follow the guidelines in [commit-messages.md](./commit-messages.md).
- Advanced workflows (branching, remotes, tagging, etc.) are covered in [commands.md](./commands.md).
