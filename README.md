# SISTEM OPERASI
# Minggu ke-2 : Selasa, 25 Februari 2025

 
# Oleh :
# Mey Risa Handayani
# D3 Teknik Informatika (A) PENS LA
# NRP 3124521011

# Dosen Pengampu :
# Dr Ferry Astika Saputra ST, M.Sc
# NIP : 197708232001121002


# POLITEKNIK ELEKTRONIKA NEGERI SURABAYA
# PSDKU LAMONGAN
# TAHUN 2025


# Practice Exercises
## 1.1	What are the three main purposes of an operating system?
Answer :
•	Manage computer hardware: The operating system allocates and controls the computer's resources (CPU, memory, I/O devices). 
•	Provide a basis for application programs: It creates an environment where applications can run. 
•	Act as an intermediary between the user and the hardware: It simplifies the interaction between the user and the complex hardware.

## 1.2	We have stressed the need for an operating system to make efficient use of the computing hardware. When is it appropriate for the operating system to forsake this principle and to "waste" resources? Why is such a system not really wasteful?
Answer :
•	It's appropriate when it enhances user experience or system reliability. For example, a user-friendly graphical interface might use more resources than a command-line interface, but the improved usability justifies it. 
•	It's not truly wasteful because the goal is to optimize the overall system, which includes user satisfaction and reliability, not just raw hardware utilization.

## 1.3	What is the main difficulty that a programmer must overcome in writing an operating system for a real-time environment?
Answer : The main difficulty is ensuring that operations complete within strict time constraints. The operating system must guarantee timely responses to events.

## 1.4	Keeping in mind the various definitions of operating system, consider whether the operating system should include application such as web browsers and mails programs. Argue both that it should and that it should not, and support your answers.
Answer :
•	Should : Including applications can provide a more integrated and user-friendly experience. It can ensure compatibility and optimize performance.   

•	Should not : Including applications can bloat the operating system, making it larger and more complex. It can also limit user choice and create security vulnerabilities.

## 1.5	How does the distinction between kernel mode and user mode function as a rudimentary form of protection (security)?
Answer : Kernel mode allows the operating system to execute privileged instructions and access all hardware resources, while user mode restricts applications to a subset of instructions and memory. This prevents user programs from interfering with the operating system or other programs.

## 1.6	Which of the following instructions should be privileged?
a.	Set value of timer.
Answer : Yes
b.	Read the clock.
Answer : No
c.	Clear memory.
Answer : Yes
d.	Issue a trap instruction.
Answer : No
e.	Turn off interrupts.
Answer : Yes
f.	Modify entries in device-status table.
Answer : Yes
g.	Switch from user to kernel mode.
Answer : Yes
h.	Access 1/O device.
Answer : Yes

## 1.7	Some early computers protected the operating system by placing it in a memory partition two that could not be modified by either the user job or the operating system itself. Describe two difficulties that you think could arise with such a scheme.
Answer :
•	Limited flexibility: If the operating system needed to be updated or patched, it would be difficult to do so. 
•	Memory waste: If the operating system partition was too large, it would waste valuable memory. If it was too small, it might not be able to function properly.

## 1.8	Some CPUs provide for more than two modes of operation. What are two possible uses of these multiple modes?
Answer :
•	Virtualization: Additional modes can be used to create virtual machines, allowing multiple operating systems to run on the same hardware. 
•	Security: Different modes can be used to implement fine-grained access control, providing enhanced security.

## 1.9	Timers could be used to compute the current time. Provide a short description of how this could be accomplished.
Answer : A timer can generate interrupts at regular intervals. The operating system can maintain a counter that increments with each interrupt. By knowing the interval between interrupts, the operating system can calculate the current time.

## 1.10	Give two reasons why caches are useful. What problems do they solve? What problems do they cause? If a cache can be made as large as the device for which it is caching (for instance, a cache as large as a disk), why not make it that large and eliminate the device?
Answer :
•	Reasons for usefulness: Caches improve performance by storing frequently accessed data closer to the CPU. They solve the problem of slow memory access. 
•	Problems caused: Cache coherence (keeping multiple copies of data consistent) and increased hardware complexity. 
•	Why not eliminate the device: Caches are typically volatile (data is lost when power is turned off), while devices like disks provide persistent storage. Caches are also much more expensive per unit of storage.

## 1.11	Distinguish between the client-server and peer-to-peer models of dis-tributed systems.
Answer :
•	Client-server: A central server provides services to multiple clients. 
•	Peer-to-peer: All nodes in the system have equal capabilities and can act as both clients and servers.

## 1.12	How do clustered systems differ from multiprocessor systems? What is required for two machines belonging to a cluster to cooperate to provide a highly available service?
Answer :
•	Clustered systems: Consist of multiple independent computers connected by a network. 
•	Multiprocessor systems: Consist of multiple CPUs sharing a common memory. 
•	Requirements for cooperation: Shared storage, inter-process communication mechanisms, and failure detection mechanisms.

## 1.13	Consider a computing cluster consisting of two nodes running a database. Describe two ways in which the cluster software can manage access to the data on the disk. Discuss the benefits and disadvantages of each.
Answer :
•	Shared disk: Both nodes have direct access to the same disk. 
o	Benefits: Simpler implementation.
o	Disadvantages: Requires careful synchronization to avoid data corruption.
•	Distributed file system: Data is distributed across multiple disks, and the cluster software manages access.
o	Benefits: Improved fault tolerance and scalability.
o	Disadvantages: More complex implementation.

## 1.14	What is the purpose of interrupts? How does an interrupt differ from a trap? Can traps be generated intentionally by a user program? If so, for what purpose?
Answer :
•	Purpose of interrupts: To signal the CPU that an event has occurred, requiring attention. 
•	Interrupt vs. trap: Interrupts are generated by hardware, while traps are generated by software. 
•	Traps by user programs: Yes, for system calls or error handling.

## 1.15	Explain how the Linux kernel variables HZ and jiffies can be used to determine the number of seconds the system has been running since it was booted.
Answer : HZ represents the number of timer interrupts per second. Jiffies is a counter that increments with each interrupt. Dividing jiffies by HZ gives the number of seconds since boot.

## 1.16	Direct memory access is used for high-speed 1/O devices in order to avoid increasing the CPU's execution load.
a.	How does the CPU interface with the device to coordinate the transfer?
Answer : The CPU sets up the DMA controller with the memory address, data size, and transfer direction.

b.	How does the CPU know when the memory operations are com-plete?
Answer : The DMA controller generates an interrupt when the transfer is complete.

c.	The CPU is allowed to execute other programs while the DMA controller is transferring data. Does this process interfere with the execution of the user programs? If so, describe what forms of interference are caused.
Answer : Yes, it can interfere by causing memory bus contention.

## 1.17	Some computer systems do not provide a privileged mode of operation in hardware. Is it possible to construct a secure operating system for these computer systems? Give arguments both that it is and that it is not possible.
Answer :
•	Possible: Software-based protection mechanisms could be used, but they would be less efficient and more complex. 
•	Not possible: Without hardware support, it's difficult to prevent user programs from accessing privileged resources.

## 1.18	Many SMP systems have different levels of caches; one level is local to each processing core, and another level is shared among all processing cores. Why are caching systems designed this way?
Answer : Local caches provide fast access to frequently used data, while shared caches allow cores to share data and maintain cache coherence.

## 1.19	Rank the following storage systems from slowest to fastest:
a.	Hard-disk drives
b.	Registers
c.	Optical disk
d.	Main memory
e.	Nonvolatile memory
f.	Magnetic tapes
g.	Cache

Answer :
f. Magnetic tapes 
c. Optical disk 
a. Hard-disk drives
d. Main memory 
e. Nonvolatile memory 
g. Cache 
b. Registers

## 1.20	Consider an SMP system similar to the one shown in Figure 1.8. Illustrate with an example how data residing in memory could in fact have a different value in each of the local caches.
Answer : If two cores read the same memory location into their local caches and then one core modifies the data, the caches will have different values until a cache coherence mechanism updates them.

## 1.21	Discuss, with examples, how the problem of maintaining coherence of cached data manifests itself in the following processing environments:
a.	Single-processor systems
Answer : In single-processor systems, cache coherence is mainly a concern when I/O operations are involved. For example, if the processor modifies data in the cache and then an I/O operation reads the same data from memory, the I/O operation might read stale data if the cache has not been written back to memory.
b.	Multiprocessor systems
Answer : In multiprocessor systems, cache coherence is critical because multiple processors can have copies of the same data in their local caches. If one processor modifies the data in its cache, the other processors' caches must be updated to ensure that they have a consistent view of the data. An example of this is two cores running the same thread and reading the same variable from memory. If one thread changes the variable, the other thread must see the change.
c.	Distributed systems
Answer : In distributed systems, cache coherence is even more complex because data can be cached on multiple machines. For example, in a distributed file system, multiple clients might cache the same file blocks. If one client modifies a block, the other clients must be notified of the change.

## 1.22	Describe a mechanism for enforcing memory protection in order to prevent a program from modifying the memory associated with other programs.
Answer : A common mechanism is to use a hardware memory management unit (MMU). The MMU translates virtual addresses generated by programs to physical addresses in memory. The operating system sets access permissions for each page of memory, and the MMU enforces these permissions. If a program tries to access memory that it does not have permission to access, the MMU raises an error.

## 1.23	Which network configuration-LAN or WAN-would best suit the fol-lowing environments?
a.	A campus student union.
Answer : A LAN (Local Area Network) would be most appropriate because a campus student union is typically located in a geographically limited area.
b.	Several campus locations across a statewide university system
Answer : A WAN (Wide Area Network) would be most appropriate because the campus locations are spread out over a wide geographical area.
c.	A neighborhood
Answer : A LAN or local area network would be best.

## 1.24	Describe some of the challenges of designing operating systems for mobile devices compared with designing operating systems for tradi-tional PCs.
Answer :
•	Mobile devices have limited resources, such as processing power, memory, and storage space. Operating systems for mobile devices must be resource-efficient.
•	Mobile devices have a wide range of hardware capabilities, such as touch screens, GPS, and accelerometers. Operating systems for mobile devices must support a variety of hardware capabilities.
•	Mobile devices are often used in a variety of network environments, such as cellular network
•	Security: Mobile devices often store sensitive data, such as personal information and financial data. Operating systems for mobile devices must be secure to protect this data.

## 1.25	What are some advantages of peer-to-peer systems over client-server systems?
Answer :
•	Scalability: Peer-to-peer systems can scale to a large number of nodes.
•	 Resilience: Peer-to-peer systems are resilient to failures because they do not have a central point of failure.
•	 Cost: Peer-to-peer systems can be less expensive than client-server systems because they do not require a central server.

## 1.26	Describe some distributed applications that would be appropriate for a peer-to-peer system.
Answer :
•	File sharing: Peer-to-peer systems can be used to share large files, such as music and video files.
•	 Distributed computing: Peer-to-peer systems can be used to distribute computing tasks across multiple nodes.
•	 Communication: Peer-to-peer systems can be used for communication applications, such as video chat and video conferencing.

## 1.27	Identify several advantages and several disadvantages of open-source operating systems. Identify the types of people who would find each aspect to be an advantage or a disadvantage.
Answer :
•	Advantages: 
o	 Cost: Open-source operating systems are often free to use.
o	 Flexibility: Open-source operating systems can be modified to meet the specific needs of users.
o	 Community: Open-source operating systems often have a large community of developers and users who can provide support.

•	Disadvantages: 
o	 Compatibility: Open-source operating systems may not be compatible with all hardware and software.
o	 Support: Open-source operating systems may not have the same level of support as proprietary operating systems.
o	Ease of use: Some open-source operating systems may be more difficult to use than proprietary operating systems.

Types of people who would find each aspect to be an advantage or a disadvantage:
•	Budget-minded users might find the cost to be an advantage.
•	Users who need flexibility might find the flexibility to be an advantage.
•	Users who need support might find the lack of support to be a disadvantage.
•	Non-technical users might find the ease of use to be a disadvantage.
