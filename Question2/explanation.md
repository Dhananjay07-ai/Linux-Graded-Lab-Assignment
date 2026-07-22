Question 2: Process Monitoring and Zombie Prevention
Objective

The objective is to create child processes using fork(), monitor their execution, prevent zombie processes, and terminate unresponsive processes using signals.

fork()

The fork() system call creates a new child process. After fork() executes, both the parent and child continue execution from the next instruction.

The child process receives a return value of 0, while the parent process receives the process ID of the newly created child.

Process Monitoring

The parent process monitors its child processes using waitpid().

The WNOHANG option allows the parent to check whether a child has finished without becoming permanently blocked while waiting.

This allows the parent to continue monitoring other processes.

waitpid()

When a child process terminates, the parent must collect its exit status using waitpid().

This removes the terminated child from the process table and prevents it from becoming a zombie process.

Signals

The kill() system call is used to send signals to processes.

SIGTERM is first sent to request a graceful termination. If a process does not respond, SIGKILL can be used to forcefully terminate it.

Unresponsive Process

One child process is intentionally made to run continuously to simulate an unresponsive process.

The parent detects that this child has not completed and sends a termination signal.

How the Concepts Work Together

The parent creates child processes using fork().

It then monitors their execution using waitpid().

When a child completes, the parent collects its exit status so that the child does not become a zombie.

If a child becomes unresponsive, the parent uses signals such as SIGTERM to terminate it.

Finally, the parent waits for and reaps all remaining child processes.

Result

The program successfully created multiple child processes, monitored their execution, terminated an unresponsive child, and prevented zombie processes using waitpid().
