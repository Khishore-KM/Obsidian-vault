It is the main layer between the OS and the underlying computer hardware, and it helps 
with tasks such as process and memory management , file systems, device control and 
networking.
The BIOS loads the bootloader which further loads the kernel into the computer memory
This transfers control to the kernel which then loads other OS components and complete the system startup and make control available for the users.

![[Pasted image 20230620144853.png]]

Purpose of a KERNEL:
                         It provides interfaces needed for users and applications to interact with the computer.
                         It launches and manages the application.
                         It manages the underlying system and the hardware devices.

## Device Drivers:
A key part of kernel operation is communication with hardware devices inside and outside of the physical computer.
The OS is not capable of interacting with every possible device of the internet.
Kernels rely on device drivers to add kernel support to specialized devices.
When OS is installed , This installation adds device drivers for any specific devices detected within the computer.
There are two types of device drivers kernel or user:


##### Kernel device driver
this is a generic driver which is loaded along with the OS.
These are suited for small categories of major hardware devices.

##### User device driver
These are the drivers added by the user for adhoc devices like sound systems, plug and play devices etc.

##### Kernel mode:
Kernel mode refers to the processor mode that enables software to have full and unrestricted access to the system and its resources. The OS kernel and kernel drivers, such as the file system driver, are loaded into protected memory space and operate in this highly privileged kernel mode.


##### User mode:
This mode enables user based applications to run such as video game to load and execute the program.
These user mode applications are less privileged and cannot access the system resources directly.


##### Types of Kernels:
								- MicroKernel.
								- Monolithic Kernel.


##### Microkernel:
Microkernel have all their services in the kernel address space, it uses message passing and sends data packets signals and functions to the correct processes.
Microkernels are more flexible then monolithic kernels the user can modify service address etc.
Micro kernels are isolated hence these kernels are more secure than monolithic kernels

##### Monolithic Kernels:
Monolithic kernels are larger than microkernels because they house both kernel and user in the same space.
Monolithic kernel uses faster system call communication protocol than microkernels to execute processes between hardware and software.

##### Hybrid kernels:
Apple developed the XNU OS kernel in 1996 as a hybrid of the Mach and Berkeley Software Distribution ([BSD](https://www.techtarget.com/searchdatacenter/definition/BSD-Berkeley-Software-Distribution)) kernels and paired it with an Objective-C application programming interface or API. Because it is a combination of the monolithic kernel and microkernel, it has increased modularity, and parts of the OS gain memory protection.

