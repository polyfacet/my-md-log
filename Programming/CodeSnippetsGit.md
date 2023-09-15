# Git commands and aliases
<div class='editDate'>Updated: 2023-09-15</div>
Collection of use full git commands and aliases

## Find the most frequently changed files
To find the most frequently changed files can be a part of find technical dept.
I.e. if a file (usually a class, in this exmaple an "Aras-method") frequently changed
and it is also is complex (E.g. Cyclomatic complex) it can be suspected to have a larger technical dept.

``` powershell
# Most changed (Aras) Method(s) files last 2 years
# Source: https://dev.to/augustohp/files-with-the-most-changes-on-git-repository-46l1
git log --since="2 year ago" --name-only --pretty="format:" | sed '/^\s*$/'d | sort | uniq -c | sort -r | grep Method | head -n 20
```

## Misc aliases 

``` powershell
# commit with add and message
git config --global alias.cm 'commit -am'

# Status short with branch name
git config --global alias.s "status -sb"

# A condensed/pretty log
git config --global alias.l "log --pretty=\"format:%Cblue%cr %Creset%s %Cblue%an %Cred%d %Cgreen%h\""

# The a condensed pretty Log of All Branches (including remotes)
# Useful to get a glance on what others are working with
git config --global alias.lab "l --branches=* --remotes=* --graph"

# Search commit messages
git config --global alias.find "log -i --pretty=\"format:%Cgreen%h %Cred%cr %Cblue%s %Cred%an\" --name-status --grep"
#Use: git find PLM-1628

# Logs "functional" changes. If conventional commits are applied, this filters out the changes
# that matters most from and end user perspective. Commit messages starting with feat/fix/cr
git config --global alias.ll "log --grep='^feat\|^fix\|^cr' --oneline"

# Run mergetodev when you are working with a "issue-branch"
# Rebases it against a pulled dev/main and then merges into dev/main
# When doing these we avoid merge commits, and get a straight development history line in dev/main 
git config --local alias.mergetodev "!git checkout dev/main && git pull && git checkout - && git rebase dev/main && git checkout - && git status -sb && git merge - && :"
```

## Advanded logs 

``` powershell
# List Added files last year within current directory
git log --since="1 year ago"  --pretty=oneline --name-status --diff-filter=A -- ./
```

## Using tags

``` powershell
# Find which tags a commit is included in.
# Useful for quick finding which version when a change was done (if tagging releases)
# Example: while using git log --grep="fix(ECO):" , to search fixes for ECO
git tag --contains f254f30
#
# v2.0.2
# v2.0.3
# I.e. the fix was implemented in v2.0.2
```
