# Project goal:

Adding a new system command called `ps` that prints the status of processes in the system.

# Project discription: 

When running `xv6` and trying to run `ps` via the CLI, we get:

<img width="632" height="127" alt="Screenshot (2830)" src="https://github.com/user-attachments/assets/2edda2df-24ab-41a8-97d8-35105576983d" />

The reason for the error is that the ps command does not exist on the system.

After adding the command, the result of running it should be:

<img width="628" height="175" alt="Screenshot (2831)" src="https://github.com/user-attachments/assets/f219b7a3-118d-4ade-afbd-96f4b6b5c482" />

So we will add the necessary system call and the ps system command (after adding it, it will appear among the system commands).

In order for `ps` to do its job, an appropriate system call needs to be added, but in this project, the `syscall.h` file *must not be modified*.

Therefore, in order to succeed in this project without the ability to change `syscall.h`, you'll need to understand the role and 

meaning of the relevant data structure in `syscall.c` file and how to *circumvent* the given limitation.

In addition, a change (addition) was made to the usys.S file, which contains an example of a change made as a "manual" addition of a FORK

system call. We will proceed in a similar manner to add a new system call.

In the syscall.h file, there is a note regarding the FORK system call that simulates the current state of the project - when it is not 

possible to change the contents of the file.

# Note:

* It is important to note that the limitation is only intended to facilitate understanding and is not an acceptable way to introduce changes

  to the system code.

* To print the PPID field, you need to find it in the process's PCB - `struct proc` in the `proc.h` file, the field name is different, it can be

  easily found according to the comments.

* Note that the printed PPID field of INIT *should be 0* (see second image) even though the field holding the PPID in the PCB has a different

   number, we assume that the father of the first process in user space has PID = 0, this is implemented in this project and we also provide

   a way to identify the INIT process. The rest of the PPIDs in the field are correct.

* Existing processes created in the system are printed, with no rows that do not reflect existing processes in the process table.

* For simplicity and consistency of output, any process that is not in a true RUNING state is printed as SLEEPING (meaning NOT RUNING).


