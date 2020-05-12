# GIT

Head points to last commit unless you move it.
Tons of commits and some branching here if you want to play with the commits and move head around.

### Basics

#### Logs
```
git log
git show
git log --oneline --graph --decorate --all
```
#### List files
```
git ls-files
```
### Express commit
```
git commit -am”commit message” (add and commit in one line)
```
### Un-add file
```
git reset HEAD README.md (un-add README)
```
### undo changes/reset README back to what’s on head
```
git checkout HEAD README.md 
```
(undo changes/reset README back to what’s on head)

### Reset git (don’t do this)

XXXXXX rm -rf .git XXXXX to get rid of git tracking
```
git log --oneline --graph --decorate --all
```
- 8b95026 (HEAD -> master) Updating README
- 563a1bb Adding a LICENSE file and README to repo

### Alias

#### Add an alias
```
git config --global alias.hist "log --oneline --graph --all"
```
#### Using alias
```
git hist
git hist <file name>
```
### List all configuration
```
git config --global --list
```
### Renaming files
```
git mv example.txt demo.txt
```
(File is staged, you will need to commit)

### Removing files
```
git rm demo.txt
```
(Change is staged, you will need to commit)

### Add all updates
```
git add -A
```
#### Note: all update adding/removing/updating of files

(File is staged, you will need to commit)

### Git diff and difftool (p4merge in my case see install below)
```
git diff
git difftool
git difftool <filename>
git difftool <branch name> <branch name>
CMD + Q to quit
```
### Branches

#### List branches
```
git branch
```
#### New branch
```
git checkout -b <branch name>
```
#### Merge branch

Switch to destination branch then
```
git merge <source branch>
```
#### Delete branch
```
git branch -d <branch name>
```
#### to use difftool between branches
```
git difftool <branch name> <branch name>
```
### Merge conflicts

```
  git mergetool 
  then resolve conflict in mergetool
  git commit -m “resolved conflict”
```

Download P4Merge: https://www.perforce.com/downloads/helix#clients

Run only the P4V client

Configure P4Merge as Diff Tool in Git:
```
git config --global diff.tool p4merge
git config --global difftool.p4merge.path "/Applications/p4merge.app/Contents/MacOS/p4merge"
git config --global difftool.prompt false
```
Configure P4Merge as Merge Tool in Git:
```
git config --global merge.tool p4merge
git config --global mergetool.p4merge.path "/Applications/p4merge.app/Contents/MacOS/p4merge"
git config --global mergetool.prompt false
```
### Tag

#### Add tag
```
git tag -a v1.0 -m "Release 1.0"
```
#### List tags
```
git tag --list
```
#### Tag details
```
git show v1.0
```
### Stash
```
git stash
git stash list
```
### Reset
```
git reset <commit id> —soft
git reset <commit id> —mixed
git reset <commit id> —hard
```
### Go back in history
```
git reflog
```
Will see last commands and can reset back to where we were
### remote repo

#### See remote repo
```
git remote -v
```
#### Set remote repo
```
git remote add origin git@github.com:xxxxxxx
```
  Then push master
```
git push -u origin master.
```
#### Update remote repo
```
git remote set-url origin git@github.com:xxxxxxx
```
#### Show oright
```
git remote show origin
```
