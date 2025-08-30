# Linux-Process-API-fork-wait-exec-
Ex02-Linux Process API-fork(), wait(), exec()
# Ex02-OS-Linux-Process API - fork(), wait(), exec()
Operating systems Lab exercise


# AIM:
To write C Program that uses Linux Process API - fork(), wait(), exec()

# DESIGN STEPS:

### Step 1:

Navigate to any Linux environment installed on the system or installed inside a virtual environment like virtual box/vmware or online linux JSLinux (https://bellard.org/jslinux/vm.html?url=alpine-x86.cfg&mem=192) or docker.

### Step 2:

Write the C Program using Linux Process API - fork(), wait(), exec()

### Step 3:

Test the C Program for the desired output. 

# PROGRAM:
 Developed by : NENTHRANJI S
 Register Number : 212224040216

# C Program to print process ID and parent Process ID using Linux API system calls
~~~
 #include <stdio.h>
 #include <sys/types.h>
 #include <unistd.h>
 int main(void)
 {
 //variable to store calling function's process id
 pid_t process_id;
 //variable to store parent function's process id
 pid_t p_process_id;
 //getpid() - will return process id of calling function
 process_id = getpid();
 //getppid() - will return process id of parent function
 p_process_id = getppid();
 //printing the process ids
 //printing the process ids
 printf("The process id: %d\n",process_id);
 printf("The process id of parent function: %d\n",p_process_id);
 return 0;
}
~~~
# OUTPUT
<img width="1342" height="888" alt="Screenshot 2025-08-30 174851" src="https://github.com/user-attachments/assets/8445f3dd-b57e-4148-992e-68c331b781ed" />

#  C Program to create new process using Linux API system calls fork() and exit()
~~~
 #include <stdio.h>
 #include<stdlib.h>
 int main()
 { int pid; 
pid=fork(); 
if(pid == 0) 
{ printf("Iam child my pid is %d\n",getpid()); 
printf("My parent pid is:%d\n",getppid()); 
exit(0); } 
else{ 
printf("I am parent, my pid is %d\n",getpid()); 
sleep(100); 
exit(0);} 
}
~~~
# OUTPUT
<img width="1678" height="437" alt="Screenshot 2025-08-30 174915" src="https://github.com/user-attachments/assets/21120b9f-8ac3-48e5-af79-e08ff7d31ed8" />

#  C Program to execute Linux system commands using Linux API system calls exec() family
~~~
 #include <unistd.h>
 #include <stdio.h>
 #include <stdlib.h>
 int main()
 {
 printf("Running ps with execlp\n");
 execlp("ps", "ps", "ax", NULL);
 printf("Done.\n");
 exit(0);
 }
~~~
# OUTPUT
<img width="1691" height="451" alt="Screenshot 2025-08-30 174930" src="https://github.com/user-attachments/assets/26eff6d2-d347-4f4f-a457-bd496fbd6bf6" />

# RESULT:
The programs are executed successfully.
