# Week 1: Introduction

### What are the three main purposes of an operating system?

The three main purposes of an operating system are to 1) allocate hardware resources fairly/efficiently, 2) to create a convenient environment for the development and execution of programs, and 3) to secure the hardware from being abused or damaged.

### Keeping in mind the various definitions of operating system, consider whether the operating system should include applications such as web browsers and mail programs. Argue both that it should and that it should not, and support your answers.

An operating system *should* include apps such as web browsers and mail programs because one definition of an operating system is "everything that a vendor ships." Vendors such as Apple and Microsoft ship their products with built-in Web browsers and mail apps; thus, they can be considered part of an operating system. 

An operating system *should not* include apps such as Web browsers and mail apps because the more conventional definition of an OS is the kernel only.

### How does the distinction between kernel mode and user mode function as a rudimentary form of protection (security) system?

The distinction functions as a rudimentary form of security/protection because it keeps users from tampering with the operating system (and accidentally destroying important parts of it).

### Some CPUs provide for more than two modes of operation. What are two possible uses of these multiple modes?

Multi-mode CPUs can run many operating systems at the same time, and can thus enable a single computer to run a variety of different programs.

### Timers could be used to compute the current time. Provide a short description of how this could be accomplished.

The program can set a timer for a future time, go to sleep, get awakened by an interrupt, and update its state to reflect the number of interrupts it has gotten thus far. Repeat this process to continually update the timer.

### Give two reasons why caches are useful. What problems do they solve? What problems do they cause? If a cache can be made as large as the device for which it is caching (for instance, a cache as large as a disk), why not make it that large and eliminate the device?

Caches are useful when 2+ components need to exchange data and perform transfers at different speeds. A cache acts as a buffer of intermediate speed between the components. This way, the faster component can find the data it needs without having to wait for the slower cache. 

One problem that caches cause is that the data in it could be inconsistent with the data in the components, especially if the cache is being used with a multiprocessor system. A cache could replace an equally-sized component, but the cache would have to have equal state-saving capacity and not cost too much.

### What is the purpose of interrupts? How does an interrupt differ from a trap? Can traps be generated intentionally by a user program? If so, for what purpose?

Interrupts exist to control system flow and execution. Interrupts are *hardware-generated* state changes and traps are *software-generated* state changes. Traps can be generated intentionally by user programs, usually to catch errors or to make system calls. 

### Some computer systems do not provide a privileged mode of operation in hardware. Is it possible to construct a secure operating system for these computer systems? Give arguments both that it is and that it is not possible.

It is possible to construct a secure operating system for computer systems that do not provide a privileged mode of operation in hardware, but it would certainly be very difficult. In order to make such a system secure, all code must be verified by the operating system before being run, which is expensive.

### Describe some of the challenges of designing operating systems for mobile devices compared with designing operating systems for traditional PCs.

Challenges of designing operating systems for mobile devices rather than traditional PCs include having to manage memory and consumption more carefully.

## Identify several advantages and several disadvantages of open-source operating systems. Include the types of people who would find each aspect to be an advantage or a disadvantage.

Open-source operating systems allow developers to build upon existing software to solve their specific problems at hand, rather than having to build a proprietary new system from scratch. It also allows anyone with a bright mind to contribute. Often, developers with a passion for "social coding" and collaboration can be seen contributing to such endeavors.

Being open source means that anyone can see your code. Developers working on open source projects will have their work openly criticized. Those with concern for embarrassment or reputation-harming would find this aspect to be a disadvantage -- although, in my personal opinion, learning from constructive criticism is the fastest way to grow and become a better dev. :)
