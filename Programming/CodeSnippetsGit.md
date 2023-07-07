# Git commands and aliases
<div class='editDate'>Updated: 2023-03-03</div>
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

# Search commit messages
git config --global alias.find "log -i --pretty=\"format:%Cgreen%h %Cred%cr %Cblue%s %Cred%an\" --name-status --grep"
#Use: git find PLM-1628

# Logs "functional" changes. If conventional commits are applied, this filters out the changes
# that matters most from and end user perspective. Commit messages starting with feat/fix/cr
git config --global alias.ll "log --grep='^feat\|^fix\|^cr' --oneline"
```
