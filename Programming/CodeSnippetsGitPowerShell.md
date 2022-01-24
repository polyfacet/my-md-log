# Code Snippets
<div class='editDate'>Updated: 2022-01-24</div>

Some code snippets I don't frequently enough to remember but needs every know an then.
- [Code Snippets](#code-snippets)
    - [List file changes from a specific date in git (with filters)](#list-file-changes-from-a-specific-date-in-git-with-filters)
      - [Output Result](#output-result)
    - [Restart a service on remote server with other credentials](#restart-a-service-on-remote-server-with-other-credentials)
    - [List lastest modfied files "like" in a directory](#list-lastest-modfied-files-like-in-a-directory)
    - [Repeat a command every X seconds](#repeat-a-command-every-x-seconds)
    - [Get My Public IP](#get-my-public-ip)

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

### Restart a service on remote server with other credentials
Example:
 - Computer Name = acme-dev
 - Service Name = AcmeSuperService 

``` powershell
# Start powershell with other credentials 
#(Close the powershell (ps) that opened the new "other cred." ps,
# otherwise the new ps will not be repsonsive for some unknown reason)
start powershell -credential ""
# Get Service on computer "like"
Get-Service -Name "AcmeSuper*" -ComputerName acme-dev | Select Name
# Restart service on computer  "like"
Get-Service -Name "AcmeSuper*" -ComputerName acme-dev | Restart-Service
```

### List lastest modfied files "like" in a directory

``` powershell
# List 10 latest modified files starting with "Error" in current folder 
Get-ChildItem -File -Path "Error*" -ErrorAction SilentlyContinue |  Sort LastWriteTime -Descending | Select-Object -First 10 LastWriteTime,Name
# or
Get-ChildItem -File -Path "Error*" -ErrorAction SilentlyContinue |  Sort LastWriteTime -Descending | Select-Object -First 10 LastWriteTime,Name | Format-Table -Wrap
```

Output example:
``` powershell
LastWriteTime       Name
-------------       ----
2022-01-17 11:30:17 ERROR_MY_SyncUrlRelation.log
2022-01-17 08:16:54 ERROR_MY_ShareRequest_GetValidations.log
2022-01-11 16:20:04 ERROR_MY_GetEcoValidations.log
2021-12-13 13:00:53 ERROR_MY_PartMoveFacility_Generic.log
2021-12-13 07:38:56 ERROR_MY_PartGetValidations.log
2021-12-09 10:34:16 ERROR_MY_SetAcquisitionFromErp.log
2021-12-07 10:23:14 ERROR_MY_RemoveFraGroups.log
2021-12-07 09:08:27 ERROR_MY_GeneratePartStructureReport.log
2021-12-02 10:28:57 ERROR_MY_EcoGetPartBomDiff.log
2021-11-16 12:49:24 ERROR_MY_GetHelp.log
```


### Repeat a command every X seconds

``` powershell
# To count the files (recursivliy) in a directory
dir . *.* -recurse | measure | % Count
# To repeat it every 10 second
cls; while ($true) { dir . *.* -recurse | measure | % Count; start-sleep -seconds 10; }
```

### Get My Public IP 

``` powershell
(Invoke-WebRequest -uri "http://ifconfig.me/ip").Content
```