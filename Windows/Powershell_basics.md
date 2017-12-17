# Powershell basics

##### Operating Powershell
* CTRL + C quits almost anything
* Arrow left and right move the cursor to the left or right
* Arrow L or R + CTRL moves one word at a time
* Home to get to the beginning of a line
* End to get to the end of a line
* Backspace deletes a character to the left
* Del erases to the right
* Esc deletes the entire line
* CTRL + home of end deletes from the current position to the left or right respectively
* Type '#' and any number of letters from a previous command, then TAB one or more times to see all commands that contained the keyword.
* Use up and down arrow keys to go back and forth in your command history
* TAB as usual makes Powershell attempt to finish you command
* '*' wildcard for all characters
* '?' wildcard for one character
* '$' defines a variable
* '@' defines an array
* '=' assigns a value
* ' ' Single quotes are used to print literal text
* " " Double quotes ensures variables in the text will be filled in.
* '#' To comment a single line
* '<#...#>' to comment multiple lines

##### Simple commands

* `dir` lists all files and directories
* `get-process` shows all running processes
* `cls` clears content of the console window
* `Show-Command Get-ChildItem` makes a window pop up to help fill in the parameters.
* `Get-Alias` gives an summary of the aliasses.
* `Clear-Host` clears the screen
* 

Piping uses the vertical bar (`|`). The results of the command to the left of the pipe symbol are then fed into the command on the right side of the pipe symbol.
* `>` redirects the result of a command to a file.

##### More complicated commands

```Get-ChildItem -Path C:\Windows\System32 -Filter *.exe -Recurse```

Shows all files (Get-ChildItem) in the folder “System32” (-Path) ending in “.exe” (-Filter), also does this for al subdirectories (-Recurse)

`Parameter-Confirm`
Shows a pop-up that asks if you want to continue the operation

`[string] $input = Read-Host`
Reads the user input and saves it in the String variable 'input'

`[string] output = $input.ToUpper()`
Convert input to capitals and save in the string 'output'

`[int] $numberOfChars = $input.Length`
Count the number of characters.

`$woorden = $invoer.Split(' ')`
Split a String based on the spaces it contains

`$people = @{Jenny=38;Bart=36;Nico=8;Kristel=6;Fleur=4}`
A hashtable of people with their age.

`$personen.Values`
Shows the hashtable

##### Conditionals and control flow
The If conditional
```
If(condition)
{
action to perform
    
}
elseif(condition)
{
action
}
else
{
action
}
```

Possible parameters
* `-eq` equals to
* `-lt` smaller than
* `-gt` greater than
* `-le` smaller than or equal
* `-ge` greater than or equal
* `-like` similar to
 
The Switch conditional
```
Switch($number)
{
1 {action}
2 {action}
3 {action}
default {action}
}
```

The Do loop
```
Do{action} until(condition)
```

The For loop
```
For(condition){action} 
```
The Foreach loop
```
Foreach(itemINset){action} 
```
##### Functions
```
Function *name*($arg1,$arg2)
{
    action;
    return $output
}
```

##### Scripting

Schrijf een script om de gebruiker naar zijn naam te vragen en of hij vervolgens naar nu.nl wil. Maak voor deze functie gebruik van start iexplore http://www.nu.nl

```
cls
$naam = Read-Host "Hallo, wat is je naam?"
function browser-openen
{
    start iexplorehttp://www.nu.nl
}
Write-Host "Hallo $naam, wil je naar nu.nl?"
$lezen= Read-host "Ja(J), Nee(N)"
if( ($lezen -eq"J") -or ($lezen -eq"Ja") )
{
browser-openen
}
else
{
Write-Host "He, wat jammer!"
}
```

Write a script to see if a file exists
```
cls
$ChkFile= Read-host "Geef pad in om te checken"
$FileExists= Test-Path $ChkFile
If ($FileExists-eq$True) {
Write-Host "$ChkFilebestaat.`n"
}
Else { 
Write-Host "$ChkFilebestaatniet.`n"
}
```

Ask a color to the user and set it as fontcolor
```
$kleur= Read-Host "`n`nSelecteereenkleurcode(1 t/m 7)"
cls
Switch ($kleur)
{ 
1 {Write-Host -ForegroundColorRed  "`n De gekozenkleuris rood. `n"}
2 {Write-Host -ForegroundColorBlue "`n De gekozenkleuris blauw.`n"} 
3 {Write-Host -ForegroundColorGreen "`n De gekozen kleur is groen.`n"} 4 {Write-Host -ForegroundColorYellow"`n De gekozen kleur is geel.`n"} 
5 {Write-Host -ForegroundColorGray "`n De gekozen kleur is grijs.`n"} 
6 {Write-Host -ForegroundColorCyan"`n De gekozen kleur is cyaan.`n"}
7 {Write-Host -ForegroundColorMagenta "`n De gekozen kleur is magenta.`n"}
default {Write-Host -BackGroundColorYellow-ForegroundColorRed "`n Geen geldige kleurcode gekozen.`n"}
}
```

