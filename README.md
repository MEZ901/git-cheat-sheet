# git-cheat-sheet

## ROUTE

- [setup](#setup)
  - [set a name that is identifiable for credit when review version history](#set-a-name-that-is-identifiable-for-credit-when-review-version-history)
  - [set an email address that will be associated with each history marker](#set-an-email-address-that-will-be-associated-with-each-history-marker)
  - [set automatic command line coloring for Git for easy reviewing](#set-automatic-command-line-coloring-for-git-for-easy-reviewing)
- [setup and init](#setup-and-init)
  - [initialize an existing directory as a Git repository](#initialize-an-existing-directory-as-a-git-repository)
  - [retrieve an entire repository from a hosted location via URL](#retrieve-an-entire-repository-from-a-hosted-location-via-url)
- [stage and snapshot](#stage-and-snapshot)
  - [show modified files in working directory, staged for your next commit](#show-modified-files-in-working-directory-staged-for-your-next-commit)
  - [add a file as it looks now to your next commit (stage)](#add-a-file-as-it-looks-now-to-your-next-commit-stage)
  - [unstage a file while retaining the changes in working directory](#unstage-a-file-while-retaining-the-changes-in-working-directory)
  - [diff of what is changed but not staged](#diff-of-what-is-changed-but-not-staged)
  - [diff of what is staged but not yet commited](#diff-of-what-is-staged-but-not-yet-commited)
  - [commit your staged content as a new commit snapshot](#commit-your-staged-content-as-a-new-commit-snapshot)
- [branch and merge](#branch-and-merge)
- [inspect and compare](#inspect-and-compare)
- [tracking path changes](#tracking-path-changes)
- [ignoring patterns](#ignoring-patterns)
- [share and update](#share-and-update)
- [rewrite history](#rewrite-history)
- [temporary commits](#temporary-commits)

## SETUP
### set a name that is identifiable for credit when review version history
```bash
git config --global user.name “[firstname lastname]”
```
### set an email address that will be associated with each history marker
```bash
git config --global user.email “[valid-email]”
```
### set automatic command line coloring for Git for easy reviewing
```bash
git config --global color.ui auto
```
## SETUP AND INIT
### initialize an existing directory as a Git repository
```bash
git init
```
### retrieve an entire repository from a hosted location via URL
```bash
git clone [url]
```
## STAGE AND SNAPSHOT
### show modified files in working directory, staged for your next commit
```bash
git status
```
### add a file as it looks now to your next commit (stage)
```bash
git add [file]
```
### unstage a file while retaining the changes in working directory
```bash
git reset [file]
```
### diff of what is changed but not staged
```bash
git diff
```
### diff of what is staged but not yet commited
```bash
git diff --staged
```
### commit your staged content as a new commit snapshot
```bash
git commit -m “[descriptive message]”
```
## BRANCH AND MERGE
### list your branches. a * will appear next to the currently active branch
```bash
git branch
```
### create a new branch at the current commit
```bash
git branch [branch-name]
```
### switch to another branch and check it out into your working directory
```bash
git checkout
```
### merge the specified branch’s history into the current one
```bash
git merge [branch]
```
### show all commits in the current branch’s history
```bash
git log
```
## INSPECT AND COMPARE
### show the commit history for the currently active branch
```bash
git log
```
### show the commits on branchA that are not on branchB
```bash
git log branchB..branchA
```
### show the commits that changed file, even across renames
```bash
git log --follow [file]
```
### show the diff of what is in branchA that is not in branchB
```bash
git diff branchB...branchA
```
### show any object in Git in human-readable format
```bash
git show [SHA]
```
## TRACKING PATH CHANGES
### delete the file from project and stage the removal for commit
```bash
git rm [file]
```
### change an existing file path and stage the move
```bash
git mv [existing-path] [new-path]
```
### show all commit logs with indication of any paths that moved
```bash
git log --stat -M
```
## IGNORING PATTERNS
### Save a file with desired paterns as .gitignore with either direct string
matches or wildcard globs.
```bash
logs/
```
```bash
*.notes
```
```bash
pattern*/
```
### system wide ignore patern for all local repositories
```bash
git config --global core.excludesfile [file]
```
## SHARE AND UPDATE
### add a git URL as an alias
```bash
git remote add [alias] [url]
```
### fetch down all the branches from that Git remote
```bash
git fetch [alias]
```
### merge a remote branch into your current branch to bring it up to date
```bash
git merge [alias]/[branch]
```
### Transmit local branch commits to the remote repository branch
```bash
git push [alias] [branch]
```
### fetch and merge any commits from the tracking remote branch
```bash
git pull
```
## REWRITE HISTORY
### apply any commits of current branch ahead of specified one
```bash
git rebase [branch]
```
### clear staging area, rewrite working tree from specified commit
```bash
git reset --hard [commit]
```
## TEMPORARY COMMITS
### Save modified and staged changes
```bash
git stash
```
### list stack-order of stashed file changes
```bash
git stash list
```
### write working from top of stash stack
```bash
git stash pop
```
### discard the changes from top of stash stack
```bash
git stash drop
```
