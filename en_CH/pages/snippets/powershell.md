# PowerShell

[SS64: Automatic Variables](https://ss64.com/ps/syntax-automatic-variables.html)

```powershell
# constants
$True
$False
$NULL
$Error          # array of error object, most recent error is the first error
$StackTrace     # stack trace for the most recent error
$Pwd            # full path of the current directory
$PSCommandPath  # full path and file name of the script that is being run
$PSScriptRoot   # directory from which the script module is being executed

# array
# [SS64: Arrays](https://ss64.com/ps/syntax-arrays.html)
$arr_var = 123, "a", "bc"
$arr_var = @(123, "a", "bc")

# dictionary
# [SS64: Hash Tables](https://ss64.com/ps/syntax-hash-tables.html)
$hash_table = @{
    "a" = "value of a"
    "b" = "value of b"
}
$hash_table.add("c", "value of c")
$hash_table.set_item("a", "new value of a")
$has_table.remove("b")


# output
Write-Host "Hello World!"

# if-elseif-else
if (condition) {command_block}
elseif (condition) {command_block}
else {command_block}

# loops
continue
break

while (condition) {command_block}

do {command_block} while (condition)

for ($i=1; $i -le 10; $i++) {Write-Host $i}

foreach ($file In $files) {command_block}

# command line arguments (first thing in a ps-file)
# types are optional
param (
    [string]$price = 100,
    [string]$ComputerName = $env:computername,
    [string]$username = $(throw "-username is required."),  # this!
    [string]$password = $(Read-Host -asSecureString "Input password"),
    [switch]$SaveData = $false
)

# Try {...} Catch {...} Finally {...}
# [SS64: try](https://ss64.com/ps/try.html)
try {command_block}
catch [[error_type][',' error_type]*] {command_block}
finally {command_block}

# Comparison Operators
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
    # perform a Case-Sensitive comparison just prefix any of the above with "c"

# Types
    -is     # Is of a type
    -isnot  # Is not of a type
    -as     # As a type, no error if conversion fails

# Logical operators
    -and    # Logical And
    -or     # Logical Or
    -xor    # Logical exclusive Or
    -not    # Logical not
    !       # Logical not
```