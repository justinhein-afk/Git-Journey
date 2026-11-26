# Git & GitHub Crash Course — Command Reference

Source: [freeCodeCamp.org — Git & GitHub Crash Course for Beginners (2026)](https://youtu.be/mAFoROnOfHs)

Commands are deduplicated and grouped in course order. Timestamps link to the relevant lessons. Replace placeholders such as `<file>` and `<commit-id>` with actual values. Compiled from the published chapters, [transcript](https://pickscribe.com/v/mAFoROnOfHs) and [timestamped summary](https://videohighlight.com/v/mAFoROnOfHs); exact on-screen invocations could not be independently verified. Examples normalize syntax and filenames where necessary.

## 1. Setup and repositories ([10:41](https://youtu.be/mAFoROnOfHs?t=641))

| Command | Purpose |
| --- | --- |
| `git --version` | Check installed Git version. |
| `git init` | Initialize a repository in the current directory. |
| `git clone <repository-url>` | Download a repository and its history. |
| `git status` | Inspect staged, unstaged and untracked changes. |

## 2. Staging ([21:43](https://youtu.be/mAFoROnOfHs?t=1303))

| Command | Purpose |
| --- | --- |
| `git add 1.txt` | Stage one file. |
| `git add 1.txt 2.txt` | Stage selected files. |
| `git add my_folder/3.txt` | Stage a file in a subdirectory. |
| `git add my_folder/` | Stage changes under a directory. |
| `git add .` | Stage changes under the current directory, including deletions. |
| `git add -A` | Stage all repository changes. |
| `git add --all` | Long form of `git add -A`. |
| `git add *` | Stage paths matching the shell wildcard; may miss hidden or deleted paths. |
| `git add *.txt` | Stage matching text files. |
| `git reset` | Unstage changes without discarding working files. |

> Use uppercase `-A`, not lowercase `-a` with `git add`.

## 3. Commits and identity ([30:22](https://youtu.be/mAFoROnOfHs?t=1822))

| Command | Purpose |
| --- | --- |
| `git commit -m "Your message"` | Record staged changes. |
| `git config --global user.email "you@example.com"` | Configure your email. |
| `git config --global user.name "Your Name"` | Configure your author name. |
| `git config --local user.email "you@example.com"` | Set email for this repository only. |
| `git config --local user.name "Your Name"` | Set name for this repository only. |
| `git reset HEAD~1` | Undo the latest local commit, retaining its changes unstaged. |

## 4. Removing files ([35:32](https://youtu.be/mAFoROnOfHs?t=2132))

| Command | Purpose |
| --- | --- |
| `git rm 1.txt` | Delete a tracked file and stage its deletion. |
| `git rm -f 1.txt` | Force removal, potentially losing edits. |
| `git rm --cached 1.txt` | Stage removal from Git tracking while retaining the local file. |
| `git rm -r my_folder/` | Recursively remove tracked files in a directory. |
| `git reset --hard` | Reset tracked files and index to HEAD, discarding uncommitted tracked changes. |

## 5. History ([39:50](https://youtu.be/mAFoROnOfHs?t=2390))

| Command | Purpose |
| --- | --- |
| `git log` | Show commit history. |
| `git log --oneline` | Display compact commit history. |

## 6. Branches and merging ([40:58](https://youtu.be/mAFoROnOfHs?t=2458))

| Command | Purpose |
| --- | --- |
| `git branch` | List local branches. |
| `git branch development` | Create a development branch. |
| `git branch staging` | Create a staging branch. |
| `git branch feature` | Create a feature branch. |
| `git checkout development` | Switch to development. |
| `git checkout staging` | Switch to staging. |
| `git checkout main` | Switch to main. |
| `git checkout feature` | Switch to the feature branch. |
| `git merge main` | Merge main into the current branch. |
| `git merge development` | Merge development into the current branch. |
| `git merge staging` | Merge staging into the current branch. |

### Merge conflicts ([47:43](https://youtu.be/mAFoROnOfHs?t=2863))

After manually resolving conflicting files, stage and commit the resolution:

```bash
git status
git add .
git commit -m "Resolve merge conflict"
```

## 7. Inspecting previous versions ([52:13](https://youtu.be/mAFoROnOfHs?t=3133))

| Command | Purpose |
| --- | --- |
| `git checkout <commit-id>` | Inspect a historical snapshot (detached HEAD). |
| `git checkout main` | Return to main. |
| `git diff <commit-id-1> <commit-id-2>` | Compare two snapshots, from the first to the second. |

## 8. Remote repositories ([55:50](https://youtu.be/mAFoROnOfHs?t=3350))

| Command | Purpose |
| --- | --- |
| `git push origin main` | Upload main to origin. |
| `git push origin staging` | Upload staging to origin. |
| `git push origin development` | Upload development to origin. |
| `git fetch` | Retrieve remote updates without integrating them into the current branch. |
| `git pull` | Fetch and integrate remote updates. |

## 9. Restoring files ([1:00:24](https://youtu.be/mAFoROnOfHs?t=3624))

| Command | Purpose |
| --- | --- |
| `git restore <file>` | Discard unstaged edits to a tracked file. |
| `git restore <directory>` | Restore tracked files in a directory. |
| `git restore .` | Discard unstaged tracked edits under the current directory. |
| `git restore --staged <file>` | Unstage a file without discarding working edits. |
| `git restore --staged .` | Unstage changes under the current directory. |

## 10. Stashing ([1:03:16](https://youtu.be/mAFoROnOfHs?t=3796))

| Command | Purpose |
| --- | --- |
| `git stash` | Temporarily save staged and unstaged tracked changes. |
| `git stash list` | List saved stashes. |
| `git stash pop` | Apply latest stash and remove it if successful. |
| `git stash apply` | Apply latest stash without removing it. |
| `git stash pop "stash@{0}"` | Pop a selected stash. |
| `git stash apply "stash@{0}"` | Apply a selected stash while retaining it. |

## 11. Reverting and rebasing ([1:09:47](https://youtu.be/mAFoROnOfHs?t=4187))

| Command | Purpose |
| --- | --- |
| `git revert <commit-id>` | Create a new commit reversing an earlier commit. |
| `git rebase main` | Replay current branch commits onto main. |

Avoid rebasing shared history without coordination. Prefer revert over reset when undoing a published commit. Review changes before running destructive commands such as `git reset --hard` or `git restore .`.

## 12. Pull requests ([1:16:48](https://youtu.be/mAFoROnOfHs?t=4608))

The course demonstrates pull requests using GitHub's web interface, rather than a Git CLI command.

## Appendix: Non-Git terminal commands from the lesson

| Command | Purpose |
| --- | --- |
| `cd <directory>` | Change directory. |
| `cd ..` | Move to parent directory. |
| `pwd` | Print current directory. |
| `mkdir <directory>` | Create a directory. |
| `touch <file>` | Create an empty file if absent. |
| `ls` | List files. |
| `ls -a` | Include hidden files. |
| `ls -la` | Detailed listing including hidden files. |
| `:wq` | Save and exit Vim (not a shell command). |

Official reference: <https://git-scm.com/docs>
