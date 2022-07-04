---
description: Malware techniques uses to obfuscate the true intent
---

# Windows

Windows malware techniques to obfuscate the true intent of the software.

### Unpacking

Most malware comes packed one way or the other, where the true software get unpacked during runtime, making static analysis harder.

```
VirtucalAlloc(Ex)
VirtualProtect(Ex)
WriteProcessMemory
CreateProcessInternalW
NtResumeThread
```

### Evasion techniques

#### Dynamic loading API

Some malware author will load libraries dynamic in real time using the _LoadLibraryA_ to find the nesscarry API needed for the software to run.

#### Process hollowing

Carves out the virtual memory of a process, which memory of the software then get written with the payload.

```
List of running processes
    CreatToolhelp32Snapshot or EnumProcesses
Lunch process with suspended flag
    CreateProcesss 
Hollow out the virtual memory of a process
    NtUnmapViewOfSection or ZwUnmapViewOfSection
Allocates memory space in the child process for the injected coded
    VirtualAlloc(Ex)
Inject code into the newly allocated memory of the child process
    WriteProcessMemory
Resume the process to run the code. 
    ResumeThread
```

#### Code injection

inject code into it own process or another process.

```
List of running processes
    CreatToolhelp32Snapshot or EnumProcesses
Open handle to target processes
    OpenProcess
Allocates memory space in the child process for the injected coded
    VirtualAlloc(Ex)
Inject code into the newly allocated memory of the child process
    WriteProcessMemory
Resumes the process to run the code.
    CreateRemoteThread
```

#### Processes iteration

Method within assembly to iterate over the current running processes.

```
List of running processes
    CreatToolhelp32Snapshot or EnumProcesses
Get the first processes from the list returned by CreateToolhelp32Snapshot
    Process32FirstW
Get the next process in the list
    Process32NextW
```

#### Virtualprotect manipulation

It is common to set the new memory to location protection to RWX\[40], Another way it first set the protection level to RW\[04] and once the code have been written change the protection again to RX\[20] to avoid AV detection

### Anti-debugging

#### Getting Process Environment block (PEB)

fs: \[30] = PEB\
Allows the program to get access to the PEB which can be used for multiple things e.g. checking if IsDebugging enabled

````
mov eax, fs[30]
mov eax [eax+2]
test eax,eax
````

### Resources

[malapi](https://malapi.io/)