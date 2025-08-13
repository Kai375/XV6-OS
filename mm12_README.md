# Project goal:

 To implements containers in `xv6` operating system in general and the implementation of the `pid namespace` in particular.

 Containers are isolated user spaces in operating systems like `xv6`.

 Container implementation is based on the management options of two resource spaces 
 
 that exist in this system - `namespace` and `mount namespace`.

 # Project discription:

 We have an `xv6` operating system that has added container support.
 
 We need to expand the system call from the previous project and adapt it to containers.

 If we try to run the system with the previous code, then we will get a compilation error:

 <img width="676" height="180" alt="Screenshot (2827)" src="https://github.com/user-attachments/assets/1c13f978-b00b-46b7-9bd4-43331377e8f4" />
 
 The reason for the error is that the structure `proc` (PCB of the process) has changed due to the addition of container support.

 Therefore, a system call was adapted and expanded and container awareness was added.

 Therefore, the system call from the previous project was adapted and expanded, and container awareness was added.

 Correct output should be like this:

 <img width="667" height="484" alt="Screenshot (2828)" src="https://github.com/user-attachments/assets/d6537245-1cad-493f-a3a4-af2d944fa4e1" />







 

