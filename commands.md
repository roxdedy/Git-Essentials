# Essential Git Commands

Practical day-to-day commands for professional workflows. Selected for frequency and utility.

## Setup & Configuration

| Command                                | Description               | Example                                           |
| -------------------------------------- | ------------------------- | ------------------------------------------------- |
| git config --global user.name "Name"   | Set global author name    | git config --global user.name "Jane Doe"          |
| git config --global user.email "email" | Set global author email   | git config --global user.email "jane@example.com" |
| git init                               | Initialize new repository | git init                                          |
| git clone <url>                        | Clone remote repository   | git clone https://github.com/user/repo.git        |

## Local Workflow

| Command                 | Description               | Example                                 |
| ----------------------- | ------------------------- | --------------------------------------- |
| git status              | Show working tree status  | git status                              |
| git add <file>          | Stage file(s)             | git add src/index.js                    |
| git add -p              | Stage hunks interactively | git add -p                              |
| git commit -m "message" | Commit staged changes     | git commit -m "fix: resolve null check" |
| git diff                | Show unstaged changes     | git diff                                |
| git diff --staged       | Show staged changes       | git diff --staged                       |

## Stashing Changes

| Command                     | Description                               | Example                                  |
| --------------------------- | ----------------------------------------- | ---------------------------------------- |
| git stash                   | Stash tracked staged and unstaged changes | git stash                                |
| git stash -u                | Include untracked files                   | git stash -u                             |
| git stash -a                | Include untracked and ignored files       | git stash -a                             |
| git stash push -m "message" | Stash with descriptive message            | git stash push -m "WIP: login form"      |
| git stash list              | List all stashes                          | git stash list                           |
| git stash apply             | Apply latest stash (keep in stack)        | git stash apply                          |
| git stash apply stash@{2}   | Apply specific stash                      | git stash apply stash@{2}                |
| git stash pop               | Apply latest and remove from stack        | git stash pop                            |
| git stash drop stash@{1}    | Delete specific stash                     | git stash drop stash@{1}                 |
| git stash clear             | Delete all stashes                        | git stash clear                          |
| git stash branch <name>     | Create branch from stash                  | git stash branch feature/login stash@{1} |

## Branching & Merging

| Command              | Description                | Example                     |
| -------------------- | -------------------------- | --------------------------- |
| git branch           | List branches              | git branch                  |
| git branch <name>    | Create branch              | git branch feature/login    |
| git switch <branch>  | Switch branch              | git switch main             |
| git switch -c <name> | Create and switch branch   | git switch -c feature/login |
| git merge <branch>   | Merge branch into current  | git merge feature/login     |
| git rebase <branch>  | Rebase current onto branch | git rebase main             |

## Remote Operations

| Command                     | Description                                                | Example                          |
| --------------------------- | ---------------------------------------------------------- | -------------------------------- |
| git remote -v               | List remotes                                               | git remote -v                    |
| git fetch                   | Fetch remote changes                                       | git fetch                        |
| git pull                    | Fetch and integrate (merge or rebase, depending on config) | git pull                         |
| git push                    | Push commits to remote                                     | git push                         |
| git push -u origin <branch> | Push and set upstream                                      | git push -u origin feature/login |

## Tagging Releases

| Command                          | Description                        | Example                               |
| -------------------------------- | ---------------------------------- | ------------------------------------- |
| git tag                          | List all tags                      | git tag                               |
| git tag <name>                   | Create lightweight tag             | git tag v1.2.0                        |
| git tag -a <name> -m "message"   | Create annotated tag (recommended) | git tag -a v1.2.0 -m "Release 1.2.0"  |
| git tag -s <name> -m "message"   | Create signed tag (GPG)            | git tag -s v1.2.0 -m "Signed release" |
| git push origin <tag>            | Push specific tag                  | git push origin v1.2.0                |
| git push origin --tags           | Push all tags                      | git push origin --tags                |
| git tag -d <tag>                 | Delete local tag                   | git tag -d v1.2.0                     |
| git push origin :refs/tags/<tag> | Delete remote tag                  | git push origin :refs/tags/v1.2.0     |

## Cherry-Picking Commits

| Command                              | Description                       | Example                             |
| ------------------------------------ | --------------------------------- | ----------------------------------- |
| git cherry-pick <commit>             | Apply a single commit             | git cherry-pick a1b2c3d             |
| git cherry-pick <commit1>..<commit2> | Apply a range                     | git cherry-pick main~3..main~1      |
| git cherry-pick -x <commit>          | Record original commit in message | git cherry-pick -x a1b2c3d          |
| git cherry-pick --no-commit <commit> | Apply without committing          | git cherry-pick --no-commit a1b2c3d |
| git cherry-pick --continue           | Continue after conflict           | git cherry-pick --continue          |
| git cherry-pick --abort              | Abort on conflict                 | git cherry-pick --abort             |

## Reverting Commits

| Command                         | Description                     | Example                        |
| ------------------------------- | ------------------------------- | ------------------------------ |
| git revert <commit>             | Undo a single commit            | git revert a1b2c3d             |
| git revert <commit1>..<commit2> | Revert a range                  | git revert main~3..main~1      |
| git revert --no-commit <commit> | Apply revert without committing | git revert --no-commit a1b2c3d |
| git revert -m <parent> <merge>  | Revert a merge commit           | git revert -m 1 HEAD           |
| git revert --continue           | Continue after conflict         | git revert --continue          |
| git revert --abort              | Abort on conflict               | git revert --abort             |

## Resetting History

| Command                    | Description                                   | Example                    |
| -------------------------- | --------------------------------------------- | -------------------------- |
| git reset --soft <commit>  | Move HEAD, keep staging/working               | git reset --soft HEAD~1    |
| git reset --mixed <commit> | Move HEAD and staging, keep working           | git reset HEAD~1           |
| git reset --hard <commit>  | Move HEAD, staging, and working (destructive) | git reset --hard HEAD~1    |
| git reset --hard ORIG_HEAD | Recover after destructive reset               | git reset --hard ORIG_HEAD |

Note: `ORIG_HEAD` is only available after certain operations (e.g., merge, rebase, reset).

## Reflog Recovery

| Command                | Description                     | Example                   |
| ---------------------- | ------------------------------- | ------------------------- |
| git reflog             | Show recent HEAD movements      | git reflog                |
| git reflog <branch>    | Show reflog for specific branch | git reflog main           |
| git reset --hard <ref> | Recover to reflog entry         | git reset --hard HEAD@{3} |

## Inspection & Recovery (core)

| Command            | Description             | Example                  |
| ------------------ | ----------------------- | ------------------------ |
| git log            | Show commit history     | git log                  |
| git log --oneline  | Compact history         | git log --oneline        |
| git restore <file> | Discard changes in file | git restore src/index.js |

Notes:

- Prefer `git switch` and `git restore` (modern Git) over older `checkout` variants.
- Use `revert` for public commits; `reset` only for local/unpushed history.
- Rebase vs merge is team-dependent.
- Run `git status` frequently.

References: Official Git documentation.
