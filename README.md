
CreateProcessAsUser
===================

This uses the Win32 apis to:

1. Find the currently active user session
2. Spawn a new process in that session

This allows a process running in a different session (such as a windows service) to start a process with a graphical user interface that the user must see.

Note that the process must have the appropriate (admin) privileges for this to work correctly.

## Usage
### PowerShell
```PowerShell
Import-Module ".\ProcessExtensions.dll"
Start-ProcessExtensions "calc.exe"
```
### C#
```C#
using murrayju.ProcessExtensions;
// ...
ProcessExtensions oProc = new ProcessExtensions();
oProc.StartProcessAsCurrentUser("notepad.exe");
```
