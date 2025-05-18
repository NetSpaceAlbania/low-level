# Low-Level Programming and Systems Syllabus

An applied, project‑driven course outline that teaches C programming, compiler construction, computer architecture, and security fundamentals through real‑world exercises and hands‑on labs.

## Beginner

### Core Topics:

- **Binary/Hexadecimal Math**: Number systems and binary arithmetic (two’s complement, overflow, bitwise operations)[1].
- **Binary Codes:** Various methods for representing data in binary form, including BCD, Gray Code, ASCII, EBCDIC, error-detecting/correcting codes etc.
- **CPU Fundamentals**: Basic CPU components (ALU, registers, control unit) [2]. Understand how instructions are fetched/executed.
- **Memory Basics**: Memory hierarchy overview (registers, cache, RAM, disk) and addressing [3]. Endianness and simple caching concepts.
- **C Programming Foundations**: Syntax, data types, control flow, functions. Practice pointers and simple data structures.
- **Intro to Assembly**: Simple assembly language via a student-friendly ISA (e.g. MIPS). Learn how C constructs (loops, function calls) map to assembly instructions.
- **Tools**: Introduction to using a compiler (gcc/clang), debugger (gdb), and simple simulators (like MARS for MIPS).

### Practical Exercises / Projects:

- Convert numbers between binary, hex, and decimal by hand and write a C program to verify results.
- Write simple C programs manipulating bits (e.g. swapping variables without temp, bit masks).
- Implement basic logical circuits in code (e.g. bitwise calculator or adders) to see ALU operations in
software.
- Compile and run a “Hello, World!” in C, then inspect the generated assembly.
- Write a small MIPS assembly program (e.g. sum an array) and run it in a simulator.

### Suggestions:

- Study digital logic basics: gates, truth tables, and simple combinational/sequential circuits.
- Read about computer organization (Patterson & Hennessy’s Computer Organization and Design).
- Explore how number representation (binary, hex, two’s complement) works in hardware.
- Understand the von Neumann architecture and fetch–execute cycle.

### Suggested Resources

- Digital Circuit Analysis and Design with Simulink Modeling and Introduction to CPLDs and FPGAs (Second Edition) by Steven T. Karris (only chapter 1-5)
- The C Programming Language (Kernighan & Ritchie) for C fundamentals.
- C How to Program: With Case Studies in Applications and Systems Programming, Global Edition 9th Edition [4]
- Computer Organization and Embedded Systems 6th Edition by Carl Hamacher [13]
- Computer Systems: A Programmer’s Perspective (Bryant & O’Hallaron) – great for linking C code to machine/
assembly [2] [3].
- CS:APP slides or video lectures (covers binary, data representation, assembly).
- Online tutorials on binary math (e.g. Neso Academy, Khan Academy, etc...) and basic logic gates.
- Patterson & Hennessy – first chapters for CPU/memory basics.
- Interactive MIPS environments (MARS or QtSpim) for assembly practice.
- Beej’s Guides

## Intermediate

### Core Topics:

- **Advanced C Programming:** Dynamic memory allocation, pointers and references, recursion, structs and
arrays, bitwise manipulation. Basics of multi-threading and signals.
- **Assembly Language:** x86-64 assembly (or ARM) – register usage, calling conventions, stack management,
function prologues/epilogues. Write and debug small routines in assembly.
- **Compilers:** Understand the compilation process (preprocessing, compilation, assembly, linking).
Introduction to writing simple lexers/parsers (e.g. with Flex/Bison) or interpreter for a tiny language.
- **Computer Architecture:** CPU pipelining basics, simple cache behavior, instruction set concepts.
- **Operating Systems:** Processes vs. threads, scheduling fundamentals, basic memory management
(paging, virtual memory concept) [5] [6]. File I/O and interrupts at a basic level.
- **Networking in C:** Socket programming with TCP/UDP; understanding client-server model. (Example:
simple chat program using BSD sockets) [7].
- **Embedded Systems (Basics):** Microcontroller fundamentals – how a CPU is integrated with I/O, timers,
ADC/DAC, interrupts [8]. (Blink an LED, read a sensor).
- **Security & Exploitation Basics:** Understand common C vulnerabilities (buffer overflow, format string). Try
simple C exercises that prevent/trigger overflows to see effects.

### Practical Exercises / Projects:

- **C Projects:** Build a custom memory allocator (like a simple malloc) or data structure (linked list, hash table)
in C.
- **Compiler Mini-Project:** Write a simple expression evaluator or calculator that lexes/parses input (using
tools or manual). Generate corresponding output. Additionaly Infix, Prefix, and Postfix Notations evaluator or convertor.
- **Assembly Challenges:** Use gdb to step through assembly, write an assembly routine (e.g. compute
factorial) and call it from C.
- **Network Programming:** Create a client-server application (e.g. file transfer or chat). Use threads or
select() for concurrency.
- **Embedded HW Exercises:** Program a microcontroller or Raspberry Pi bare-metal: e.g. toggle GPIOs, use a
timer interrupt, read an analog sensor. Experiment by reading datasheets and writing C to configure
hardware.
- **Exploitation Labs:** On an isolated system, compile a vulnerable C program (with stack-based buffer) and
use a debugger to overwrite return addresses. Observe how flow changes etc [9].
- **Reverse Engineering:** Use tools like Ghidra or objdump to disassemble a small compiled program and
make sense of its assembly.

### Suggestions:

- Deepen understanding of operating systems (use OSTEP or Tanenbaum). Study scheduling algorithms and
why virtual memory is needed.
- Learn about network protocols (TCP/IP stack) and how data flows across layers.
- Study compiler design (grammars, finite automata, parsing algorithms) from standard texts (e.g. the
“Dragon Book” by Aho/Sethi/Ullman).
- Learn about common exploitation mitigations (stack canaries, DEP/ASLR) and basic reverse-engineering
techniques.


#### Embedded Systems Example (Motorola 68HC11):
![Block diagram of the Motorola 68HC11 microcontroller architecture](https://github.com/user-attachments/assets/77a19d2d-baa5-4635-a602-998ff90ee052)

_Block diagram of the Motorola 68HC11 microcontroller architecture._ 

This diagram shows the integrated components of an 8-bit microcontroller: CPU core, on-chip RAM/ROM, timers, analog-to-digital converter
(ADC), I/O ports, interrupt logic, etc. Embedded programming courses use such diagrams to teach how C/assembly code controls hardware.
For instance, students practice toggling PORTA pins or reading the ADC via specific memory-mapped registers [8]. By writing C code that
configures timers and interrupts, learners see how software drives hardware peripherals. These hands-on tasks reinforce how low-level 
code interacts with CPU registers and on-chip devices [8].

### Suggested Resources:

- Computer Architecture: A Quantitative Approach (The Morgan Kaufmann Series in Computer Architecture and Design) 6th or 7th Edition by John L. Hennessy (Author), David A. Patterson (Author), Christos Kozyrakis (Author) [10]
- Extreme C: Taking you to the limit in Concurrency, OOP, and the most advanced capabilities of C by Kamran Amini
- Computer Systems: A Programmer’s Perspective (Chapters on linking, virtual memory, IO).
- Beej’s Guide to Network Programming (https://beej.us/guide/bgnet/) [7].
- Modern Binary Exploitation course materials (RPISEC) – covers buffer overflows, shellcoding, format strings [11]
- Crafting a Compiler or online compilers courses (e.g. Stanford/UMN).
- Unix Network Programming (Stevens) or online tutorials on sockets.
- Embedded: Embedded Systems: Introduction to ARM Cortex-M Microcontrollers (Valvano) [8]. Arduino or
Raspberry Pi “bare metal” tutorials.
- Secure Coding: CERT C Secure Coding Standard (or “Secure Coding in C/C++” by Seacord).

## Advanced

### Core Topics:

- **Advanced C & Systems Programming:** Low-level I/O (memory-mapped registers), POSIX threads, locks,
advanced use of gcc extensions (inline assembly, vector intrinsics). Optimization and profiling.
- **Deep Assembly & Architecture:** In-depth x86-64 (or ARM) microarchitecture: cache hierarchies, branch
prediction, SIMD instructions. Writing complex functions in assembly.
- **Compiler Internals:** Build or extend a real compiler (e.g. code generation and optimization phases).
Understand intermediate representations and optimization techniques.
- **Operating System Internals:** Kernel design (interrupt handling, system call implementation), advanced
scheduling (real-time, multi-core), virtual memory details, file system implementation.
- **Advanced Networking:** Implement parts of network protocols (raw sockets, packet parsing), understand
TCP state machine, build custom protocol or use libraries like libpcap.
- **Reverse Engineering & Exploitation:** Identify and exploit complex vulnerabilities (heap overflows, returnoriented programming, format-string exploits). Use advanced tools (IDA Pro, Ghidra) for disassembly/
decompilation.
- **Embedded Systems (Advanced):** Real-time operating systems (RTOS), low-level driver development, baremetal multi-threading (using interrupts and context switching). Hardware prototyping (e.g. using FPGA or
custom boards).
- **Security:** Study secure-by-design principles, cryptography basics for low-level systems, formal methods
(type-safe languages, verification).

### Practical Exercises / Projects:

- **Operating System Project:** Write a simple OS kernel or bootloader. Implement context switching, basic
scheduler, or virtual memory manager.
- **Advanced Exploitation:** Set up CTF-style challenges (e.g. create a custom vulnerable binary) and practice
writing exploits (overflow payloads, shellcode injection) [11].
- **Reverse-Engineering Challenge:** Take a compiled program (without source) and use tools to recover its
logic, patch it, or detect hidden functionality.
- **Networking Implementation:** Write a packet sniffer or implement a simple transport protocol. Modify
the Linux kernel (e.g. add a system call or network hook).
- **Embedded Real-Time Project:** Develop firmware for a microcontroller with real-time constraints (use
RTOS or bare-metal scheduling). Interface multiple sensors/actuators (e.g. motor control via PWM).
- **Security Audit:** Review and fix insecure C code (e.g. eliminate unsafe functions). Implement safeguards
like stack canaries manually or by using compiler flags.
- **Compiler Optimization:** Add an optimization pass to an open-source compiler (e.g. LLVM) and measure
performance gains.

### Suggestions:

- Advanced computer architecture (Tomasulo algorithm, superscalar, multicore coherence).
- File system and I/O device theory in OS (journaling, DMA).
- Protocol theory and formal verification for security.
- Real-time systems theory (deadlines, interrupt latency).

#### Embedded Systems Example (Intel 80C517):

![Block diagram of an Intel 80C517 microcontroller (an enhanced 8051) showing CPU, RAM/ROM, timers, serial channels, ADC, and I/O ports.](https://github.com/user-attachments/assets/68a91835-b154-48f7-aeea-2e0e48eecc15)

_Block diagram of an Intel 80C517 microcontroller (an enhanced 8051) showing CPU, RAM/ROM, timers, serial channels, ADC, and I/O ports._

In this diagram, blue blocks denote new or enhanced modules (e.g. 10-bit
ADC, serial channel 0/1), and yellow shows larger memory. Advanced embedded study covers such modern
microcontrollers: understanding their register maps and peripherals lets programmers control real-time
tasks. For example, reading an analog sensor on the 80C517 involves configuring its ADC registers and
handling the conversion interrupt. Mastery of these on-chip features (register structure, memory, CPU,
peripherals) is crucial for embedded design [12]. In advanced projects, students may write firmware (in C/
assembly) that sets up timers and serial links, illustrating the deep connection between code and hardware
on such systems [12]. 

### Suggested Resources:

- Hacking: The Art of Exploitation (No Starch) – deep dive into C pitfalls and exploitation.
- Practical Reverse Engineering or IDA Pro Book for reversing malware/binaries.
- Practical Malware Analysis: The Hands-On Guide to Dissecting Malicious Software 1st Edition by Michael Sikorski (Author), Andrew Honig (Author)
- RPISEC MBE course materials and companion videos on advanced exploits [11].
- Linux Kernel Development (Robert Love) or Understanding the Linux Kernel.
- ARM Cortex or RISC-V documentation for embedded CPU internals.
- CERT C/C++ Secure Coding Standard.
- Online courses: MIT’s 6.828 Operating System Engineering, 6.172 Performance Engineering.

## References 

Official documentation (ISO C standard, processor manuals), classic textbooks, and well-known
open-course materials were used to guide this syllabus. All recommended texts are authoritative sources
(e.g. Patterson & Hennessy on computer design, Arpaci-Dusseau on OS [5] [6], Valvano on embedded
systems [8] [12], Stevens on networking, etc.

1. [CSC 531 Syllabus - California State University, Dominguez Hills](https://www.csudh.edu/Assets/csudh-sites/csc/docs/syllbi/CSC531_syllabus.pdf#:~:text=Boolean%20algebra%2C%20logic%20equations%2C%20binary,operation%2C%20memory%20devices)

2. [Introduction to Computer Systems Section 02 - San Jose State University](https://www.sjsu.edu/cs/docs/fall24_syllabi/Introduction_to_Computer_Systems_Section_02_CS_47_Fall_2024.pdf#:~:text=1,registers%2C%20ALU%29%2C%20memory%2C%20buses)

3. [Unit 6: The Memory Hierarchy | CS301: Computer Architecture - Saylor Academy](https://learn.saylor.org/course/view.php?id=71&section=43#:~:text=performance%20and%20identifies%20different%20cache,How)

4. [CEN 110 - C PROGRAMMING | Epoka University](https://eis.epoka.edu.al/curricula/syllabus/14283/1/3#:~:text=C%20%2B%2B%20How%20to%20Program%207th%20Edition%2C%20DEITEL%20%26%20DEITEL)

5. [CSCI 4061: Introduction to Operating Systems - University of Minnesota](https://www-users.cse.umn.edu/~kauffman/4061/syllabus.html#:~:text=,coordinate%20between%20processes%2C%20manage%20memory)

6. [Operating Systems: Three Easy Pieces - University of Wisconsin](https://pages.cs.wisc.edu/~remzi/OSTEP/#:~:text=centered%20around%20three%20conceptual%20pieces,maybe%20not%20so%20fun)

7. [Beej's Guide to Network Programming](https://beej.us/guide/bgnet/#:~:text=Hello%2C%20one%20and%20all%21%20This,Unix%2C%20Linux%2C%20and%20even%20Windows)

8. [EECS 3100 - Embedded Systems Course Syllabus - University of Toledo](https://www.utoledo.edu/engineering/electrical-engineering-computer-science/current-students/syllabi/eecs-3100-microsystems-design.html#:~:text=Microcontroller%20interfacing%2C%20assembly%20and%20C,and%20embedded%20system%20debugging%20techniques)

9. [Cybersecurity Syllabus - Buffer Overflow - GitHub (4GeeksAcademy)](https://github.com/4GeeksAcademy/cybersecurity-syllabus/blob/main/07-pentesting-red-team/buffer-overflow.md#:~:text=Attackers%20exploit%20buffer%20overflow%20problems,gain%20access%20to%20IT%20systems)

10. [CEN 583 - ADVANCED COMPUTER ARCHITECTURE | Epoka University](https://eis.epoka.edu.al/curricula/syllabus/21120/1/87#:~:text=Computer%20Architecture%2C%20A%20Quantitative%20Approach%22%2C%20John%20Hennessy%2C%20David%20Patterson%2C%20Morgan%20Kaufmann)

11. [Modern Binary Exploitation Course Materials - RPISEC - GitHub](https://github.com/RPISEC/MBE#:~:text=04%20Intro%20to%20Memory%20Corruption,Vulnerabilities%20Format%20strings%2C%20DTOR%2FGOT%20overwrites)

12. [EECS 3100 - Embedded Systems Course Syllabus - University of Toledo](https://www.utoledo.edu/engineering/electrical-engineering-computer-science/current-students/syllabi/eecs-3100-microsystems-design.html#:~:text=1,CPU%20features%2C%20and%20peripheral%20subsystems)

13. [CEN 219 - COMPUTER ORGANIZATION | Epoka University](https://eis.epoka.edu.al/curricula/syllabus/13417/1/3#:~:text=Carl%20Hamacher%2C%20Zvonko%20Vranesic%2C%20Safwat%20Zaky%20and%20Naraig%20Manjikian%2C%20%E2%80%9CComputer%20Organization%20and%20Embedded%20Systems%E2%80%9D%2C%20Sixth%20Edition%2C%20McGraw%2C%20Hill%2C%202012.)
