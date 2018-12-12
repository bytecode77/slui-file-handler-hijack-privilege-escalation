# Slui File Handler Hijack LPE

| Exploit Information |                                   |
|:------------------- |:--------------------------------- |
| Publish Date        | 15.01.2018                        |
| Patched             | Windows 10 (17763)                |
| Target              | Microsoft Windows                 |
| exploit-db          | [44830](https://www.exploit-db.com/exploits/44830/) |
| CVE                 | N/A                               |
| Versions            | Windows 8-10, x86 and x64         |

## Description

slui.exe is an auto-elevated binary that is vulnerable to file handler
hijacking.

Read access to `HKCU\Software\Classes\exefile\shell\open` is performed upon
execution. Due to the registry key being accessible from user mode, an arbitrary
executable file can be injected.

This exploit is generally independent from programming language and bitness, as
no DLL injection or privileged file copy is needed. In addition, if default
system binaries suffice, file drops can be avoided altogether.

## Expected Result

When everything worked correctly, a cmd.exe should be spawned with high IL.

## Downloads

Compiled binaries:

[![](https://bytecode77.com/images/shared/fileicons/zip.png) SluiFileHandlerHijackLPE rev1 Binaries.zip](https://bytecode77.com/downloads/hacking/exploits/uac-bypass/SluiFileHandlerHijackLPE%20rev1%20Binaries.zip)

## Compiling from source

To compile from source, use Visual Studio 2017 Community edition. When installing, select all boxes for `Windows 10 SDK`, under the `Individual Components` tab. Then, when building the project, select the `Project` tab, then `Properties`. Then, under `General`, in the `SDK Version` option, select **10.0.15063.0**, and then build your project.

## Project Page

[![](https://bytecode77.com/images/shared/favicon16.png) bytecode77.com/hacking/exploits/uac-bypass/slui-file-handler-hijack-privilege-escalation](https://bytecode77.com/hacking/exploits/uac-bypass/slui-file-handler-hijack-privilege-escalation)
