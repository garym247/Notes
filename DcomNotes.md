When building COM Objects in Visual Studio, enable *Per-user
Redirection* so that objects can be registered for the current user,
rather than having to run Visual Studio in Administrator mode.

To enable *Per-user Redirection*
* Select the project
* Navigate to the *Properties->Linker->General* tab.

To see the COM objects registered by 32-bit/64-bit applications:
* C:\\Program Files (x86)\\Windows Kits\\8.1\\bin\\x86\\oleview.exe
* C:\\Program Files (x86)\\Windows Kits\\8.1\\bin\\x64\\oleview.exe

Run the above programs in Administrator mode, otherwise an error will be
reported.

To see the 32-bit component services, e.g. to view/modify the DCOM
security settings

`
MMC comexp.msc /32
`

To turn on DCOM error logging, follow these steps:
1.  Run regedit
2.  Go to HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft
3.  Locate the OLE registry key for the product, right-click.
4.  Select NEW -> DWORD, type ActivationFailureLoggingLevel, press ENTER, double-click the new key, and change its value to 1.
5.  Repeat step 4 for CallFailureLoggingLevel.
6.  Restart the program or service.
