# PowerShell

[SS64: Automatic Variables](https://ss64.com/ps/syntax-automatic-variables.html)

```powershell
# constants
$True
$False
$NULL
$Error  # array of error object, most recent error is the first error
$StackTrace  #  stack trace for the most recent error
$Pwd  # full path of the current directory
$PSCommandPath  #  full path and file name of the script that is being run
$PSScriptRoot  # directory from which the script module is being executed

# arrays
$arr_var = @{
    a = "b"
    c = "d"
}

# output

Write-Host "Hello World!"

# not

!(statement)
-Not (statement)

# if-elseif-else

if (condition) {command_block}
elseif (condition) {command_block}
else {command_block}

# while

while (condition) {command_block}

# do-while

do {command_block} while (condition)

# for

for ($i=1; $i -le 10; $i++) {Write-Host $i}

# for each

foreach ($file In $files) {command_block}

# command line arguments (first thing in a ps-file)
# types are optional
param (
    [string]$price = 100,
    [string]$ComputerName = $env:computername,
    [string]$username = $(throw "-username is required."),
    [string]$password = $(Read-Host -asSecureString "Input password"),
    [switch]$SaveData = $false
)
```

## Comparison Operators

```powershell
 -eq             # Equal
 -ne             # Not equal
 -ge             # Greater than or equal
 -gt             # Greater than
 -lt             # Less than
 -le             # Less than or equal
 -like           # Wildcard comparison
 -notlike        # Wildcard comparison
 -match          # Regular expression comparison
 -notmatch       # Regular expression comparison
 -replace        # Replace operator
 -contains       # Containment operator
 -notcontains    # Containment operator
 -in             # Like –contains, but with the operands reversed.(PowerShell 3.0)
 -notin          # Like –notcontains, but with the operands reversed.(PowerShell 3.0)
```