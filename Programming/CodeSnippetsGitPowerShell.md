# Code Snippets
<p class='editDate'>Created: 2021-11-10-</p>

Some code snippets I don't frequently enough to remember but needs every know an then.


### List file changes from a specific date in git (with filters)
```powershell
# Example name git_file_changes_baseline.ps1
# Usage: .\git_file_changes_baseline.ps1 "2021-11-01 13:00"
param($FROM_DATE)

$PATH_INCLUDES = ".md" # We only want to see the changes in markdown files
if ($FROM_DATE) {
    "From date: $FROM_DATE"
}
else {
    # If no date provided in input, get it from baseline.txt file
    $FROM_DATE = Get-Content .\baseline.txt -First 1
    "From file: $FROM_DATE"
}
"Added" # "Filter md(modified,deleted,renamed)
git log --name-status --pretty="" --after=$FROM_DATE --diff-filter="mdr" |findstr $PATH_INCLUDES
"Modified:" # "Filter md(added,deleted,renamed)
git log --name-status --pretty="" --after=$FROM_DATE --diff-filter="adr" |findstr $PATH_INCLUDES
```

#### Output Result
``` powershell
PS C:\Users\hille\Development\my-md-log\scripts> .\git_file_changes_baseline.ps1 "2021-11-09"

From date: 2021-11-09
Added
A       Programming/CodeSnippetsGitPowerShell.md
Modfied:
M       README.md
```
