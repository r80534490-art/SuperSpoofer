# SuperSpoofer

SuperSpoofer is a small C++ project that shows how to create a new process while pretending that it was started by a different parent process. This trick is called PPID spoofing. Attackers sometimes use it to hide their tracks; here it is used for educational purposes.

How it works

The program looks through the list of running processes to find the process ID (PID) of a chosen parent. By default it looks for brave.exe, but you can change this in the code.

It builds a special STARTUPINFOEX structure and sets the PROC_THREAD_ATTRIBUTE_PARENT_PROCESS attribute to the handle of the chosen parent process.

It then calls CreateProcessW with these attributes to start a new process (cmd.exe by default) with a spoofed parent.

How to build and run

Open the project in Visual Studio.

Make sure the parentProcessName string in main.cpp matches the process you want to spoof.

Build the project (compile as x64 if your system is 64‑bit).

Run the generated executable. A Command Prompt window should appear, but its parent will be reported as the spoofed process.

Requirements

Windows 10 or newer.

Visual Studio with the Windows SDK.
