Windows Usage Skills Manual
===

[TOC]

## Logout User

> For some situation, one could not find the logout button. By using the cmd line `rundll32.exe user32.dll,LockWorkStation` can easily switch to the winxp login screen.

## UoN Usage

> Since one cannot install the software on campus computers, therefore, to use portable software seems a compromized solution.

### set path environment

Just use the `set path="%path%;C:\Users\xxxx\"` to modify the temporary path parameter. Or use the command `setx path "%path%;C:\Users\xxxx\` to change it. However, I failed to use `setx` & I do not know why.

Here, to backup the campus windows path environment as following:
```
C:\Program Files\Common Files\Microsoft Shared\Windows Live;C:\Program Files (x86)\Common Files\Microsoft Shared\Windows Live;C:\Program Files\Haskell\bin;C:\Program Files\Haskell Platform\7.10.2-a\lib\extralibs\bin;C:\Program Files\Haskell Platform\7.10.2-a\bin;c:\cygwin\bin;C:\ProgramData\Oracle\Java\javapath;C:\WINDOWS\system32;C:\WINDOWS;C:\WINDOWS\System32\Wbem;C:\WINDOWS\System32\WindowsPowerShell\v1.0\;C:\WINDOWS\System32\WindowsPowerShell\v1.0\;C:\Program Files\Haskell Platform\7.10.2-a\mingw\bin;C:\Program Files (x86)\Microsoft Application Virtualization Client;C:\Program Files (x86)\Windows Kits\8.1\Windows Performance Toolkit\;C:\Program Files\Microsoft SQL Server\110\Tools\Binn\;C:\Program Files (x86)\Microsoft SDKs\TypeScript\1.0\;C:\Program Files\Microsoft SQL Server\120\Tools\Binn\;C:\Program Files\MATLAB\R2015a\runtime\win64;C:\Program Files\MATLAB\R2015a\bin;C:\Program Files (x86)\Windows Live\Shared;C:\Program Files (x86)\QT Lite\QTSystem;C:\Users\psxbw1\AppData\Local\Box\Box Edit\;C:\Users\psxbw1\
```