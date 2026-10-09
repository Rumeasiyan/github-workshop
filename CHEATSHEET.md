# Git and GitHub in VS Code: cheatsheet

**Command Palette:** `Ctrl+Shift+P` (`Cmd+Shift+P` on a Mac). **Terminal:** `` Ctrl+` ``. **Source Control:** the branch icon on the left.

## Every day

| I want to | In VS Code |
|---|---|
| See what I changed | **Source Control**: click a file to see the diff |
| See the history | **Source Control > Graph**, or right-click a file > **Open Timeline** |
| Get the latest | Switch to `main` (bottom left), then **Sync Changes** |
| Start work on an issue | **GitHub** view > Issues > **Start Working on Issue** |
| Make a branch | Bottom left branch name > **Create new branch** |
| Save a change | **+** to stage, write the message, **Commit** |
| Send it to GitHub | **Sync Changes** (or **Publish Branch** the first time) |
| Open a pull request | **GitHub** view > **Create Pull Request**, write `Closes #12`, add reviewers |
| Review a PR | **GitHub** view > Waiting for my review > open > comment, **Make a suggestion**, Approve |

## Conflicts

1. VS Code marks the file with **!**. Open it > **Resolve in Merge Editor**.
2. Left: theirs. Right: yours. Bottom: the result.
3. Choose **Accept Incoming**, **Accept Current**, or **Accept Combination**, or edit the result by hand.
4. **Complete Merge**, then commit and Sync.

## Undo

| Situation | In VS Code |
|---|---|
| Throw away my edits to a file | Right-click > **Discard Changes** |
| Throw away one part only | In the diff, the arrow beside it (**Revert Block**) |
| Take a file out of the basket | The **-** beside it |
| Fix the last commit (not synced) | Stage the fix > Command Palette > **Git: Commit Staged (Amend)** |
| Undo the last commit, keep the work | Command Palette > **Git: Undo Last Commit** |
| Undo something **others already have** | Graph > right-click the commit > **Revert Commit**, or terminal `git revert <id>` |
| "I lost a commit!" | Terminal: `git reflog`, then `git reset --hard HEAD@{n}` |
| Park unfinished work | Source Control `...` > **Stash**; later **Pop Latest Stash** |
| Take one commit from another branch | Command Palette > **Git: Cherry Pick...** |
| Tidy my branch's commits before the PR | Terminal: `git rebase -i main` (the list opens in VS Code: `pick`, `fixup`, `reword`) |
| Find which change broke something | Terminal: `git bisect start`, `git bisect bad`, `git bisect good <tag>`, check each step, `git bisect reset` |

## Rules of the team

- **Never commit to `main`.** Branch, PR, review, squash merge.
- **One issue, one branch, one small PR.** Link it with `Closes #n`.
- **A review means reading the whole change.** Ask why, point at lines, use suggestions.
- **Never commit passwords, keys or real people's data.** Put private files in `.gitignore`. Leaked something? Tell the Office at once.
- **Commit message:** what changed in under about 50 characters, then why.

## Versions

A release is a frozen, named version. The number goes up in steps:

- **1.0.1:** a small fix;
- **1.1.0:** something added;
- **2.0.0:** a big change.

On GitHub: **Releases** > **Draft a new release** > a new tag > **Generate release notes** > **Publish**.
