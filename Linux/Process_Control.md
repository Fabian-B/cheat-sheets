# Process Control
**PID: proces ID number**
The kernel assigns a unique number to every process. Most commands and system calls that manipulate processes require you to specify a PID.

PID's are assigned in order as processes are created.

**PPID: parent PID**
Neither UNIX nor Linox has a system call that initiates a new process running a particular program. It uses two steps, first clone an existing process and then exchange the program it is running for a new one. 

The original process is the parent the new one the child. The PPID is the PID of the parent.

**UID and EUID**
A precess's UID is the ID of the user that created it. It's a copy of the UID of the parent. Only the creator aka owner can manipulate a process.

The EUID is the "effective" user ID, an extra UID that determines what resources and files a process has permission to access.

**Niceness**
Used by the Kernel to determine what priority a process receives and thus how much CPU it can use.

**Process lifecycle**
A new proces is a clone of an existing process, this clone is made by the *fork* system call.

After the fork *exec* system call is used to start the new process.

init (or systemd) plays an important role in process management. A routine named *_exit* is called to notify the kernel that a process is ready to die.

Before a process can die the parent needs to ack this with a call to *wait*.
