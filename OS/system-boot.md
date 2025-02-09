# System Boot

- The process of starting the operating system by loading the kernal is called booting.
- On most computer a bootstrap program is used to load the kernel.
- The program is read only memory as RAM is in unknown state at the time of booting and ROM is convenient as it cannot be infected
- After bootstrap program has started the kernel is loaded into RAM and executed. After thsi point the system is said to be running

## Booting Process

- Power-on self-test (POST) is a test that checks the hardware components of the computer to ensure that they are working correctly.

  - BIOS/UEFI performs this test on hardware components such as the CPU, RAM, and motherboard.

- Booloader Execution is the process of loading the kernel into RAM and executing it.

  - It is loaded from the boot sector of the hard disk or from a bootable device such as a USB flash drive or a CD/DVD.

- Kernal Loading is the process of loading the kernel into RAM and executing it. - Essential drivers are initialized and the kernel is ready to run.

- Init/Systemd is the first process that is executed by the kernel.

  - It reads system config and starts other background processes.

- User Login is the process of logging into the system.
  - It is the first process that is executed by the user.
  - It loads the user's environment and starts the shell.
