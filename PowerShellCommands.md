
# Commands

```Get-Alias```
* Lists all the aliases for the cmdlets

```Get-Command```
* Lists the available cmdlets.

`Get-ChildItem`
* Lists contents of a directory (e.g. equivalent to ls in Unix)

```Get-Host```
* Returns system version for PowerShell host, e.g. version

```Get-ExecutionPolicy```
* todo

```Set-ExecutionPolicy RemoteSigned -Scope CurrentUser -Confirm```
* todo

```$env:computername```
* Returns the computer name.

```netsh http show urlacl```
* Network shell command

$PSVersionTable.PSVersion



# Select-String

`Select-String` is the PowerShell equivalent of grep.

Options

```Pattern 'HELLO' ```\
```CaseSensitive```\
```SimpleMatch```


Examples:

```Get-Command | Select-String -Pattern "Az" -SimpleMatch```

* Lists all the cmdlets with “az” (any case) in them.

```Get-Command | Select-String -Pattern "^Az"```
* Lists all the cmdlets that start with “az” (any case).

```Get-Command | Select-String -Pattern "Instance$"```
* Lists all the cmdlets that end with “Instance” (any case).

```Get-Command | Select-String -Pattern "^Get.*Instance$"``` 
* Lists all the cmdlets that start with “Get” and end with “Instance” (with 0 or more  characters in between).

# Select-Object

Examples:

 `Get-Host | Select-Object Version`




Get-AzContext




C:\Users\garym\OneDrive\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1


CTRL + SHIFT + , to edit your settings.json
