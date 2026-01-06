---
date: '2026-01-03T11:32:21Z'
draft: true
title: 'CPUs'
image: '/images/cpus.webp'
tags: ["hardware","cpus", "a+"]
---

The **Central Processing Unit (CPU)** is the heart (or brain) of a computer. It is responsible for executing programs and coordinating all other parts of the system. Every calculation, decision, and data movement ultimately passes through the CPU.

## What a CPU Does Internally

At its core, a CPU repeatedly performs the **fetch–decode–execute** cycle:

1. Fetch an instruction from memory  
2. Decode what the instruction means  
3. Execute the operation  
4. Write the result back  

To do this efficiently, the CPU consists of several key components:

- **Clock** – synchronizes all operations
- **Control Unit (CU)** – coordinates instruction execution
- **Arithmetic Logic Unit (ALU)** – performs calculations and logic
- **Registers** – ultra-fast internal storage
- **Caches** – reduce memory access latency
- **Bus system** – connects CPU to memory and peripherals

All modern CPU optimizations build on these fundamentals.


## ISA

Computers ultimately operate on zeros and ones. These binary values are grouped into **machine instructions**, which the CPU can decode and execute. A program is simply a sequence of such instructions stored in memory.

The **Instruction Set Architecture (ISA)** defines:
- which instructions exist (e.g. add, load, jump)
- how these instructions are encoded as binary
- which registers exist
- how memory is accessed

In other words, the ISA is the *contract* between software and hardware.

Depending on the architecture, instructions can have different sizes:
- Many **RISC** architectures use fixed-size instructions (typically **32 bit**, sometimes **16 bit** compressed)
- **x86** uses variable-length instructions (from **1 to 15 bytes**)

Programs compiled for one ISA cannot run on another ISA without emulation or translation. However, CPUs that implement the same ISA can usually run the same programs unchanged.

> [!TIP]
> If you want to learn more about ISA and how CPUs work internally, learn assembly. Writing assembly means directly working with a CPUs ISA and it is simpler to learn than most people assume.

### CISC and RISC

Early computers had very limited and expensive memory. To reduce program size and simplify programming, some architectures introduced **complex instructions** capable of performing multiple operations at once. These designs are known as **Complex Instruction Set Computers (CISC)**. The most prominent example is **x86**, used by Intel and AMD.

As CPUs evolved, engineers discovered that complex instructions:
- are difficult to decode efficiently
- consume more power
- limit pipelining and parallel execution

This led to the development of **Reduced Instruction Set Computers (RISC)** in the 1980s. RISC architectures focus on:
- simple, predictable instructions
- efficient pipelining
- heavy reliance on compiler optimization

### ARM and RISC-V

The most widely used RISC architecture today is **ARM (Advanced RISC Machine)**.  
Arm Holdings develops the ISA and licenses it to other companies, which design their own CPUs based on it. Manufacturing is typically outsourced to specialized foundries.

ARM is heavily used in:
- smartphones
- embedded devices (TVs, cameras, routers)
- increasingly in PCs and servers due to high energy efficiency

Another important RISC architecture is **RISC-V**. It is an open and extensible ISA widely used in education and research. While you may not see it in the wild, it is an important part of computer sciense today.

### x86/x64/amd

Modern Intel and AMD CPUS are still backward compatible with the processor **Intel 8086** from *1978*. Of course modern CPUs have many more instructions and are way more powerful, but they still have the basic instructions of the olt chips and, therefore, can run these old programs. Because of this compatibility, the ISA is called **x86**.

Although Intel invented the x86 architecture and had the copyright, **AMD** stole the architecture and started producing replacement chips. When Intel sued AND for the copyright infringement, IBM put pressure on Intel, as IBM had a huge demand for x86 CPUs that Intel alone could not manage. So, Intel and AMD worked out an agreement.

The original x86 architecture was **16bit**, Intel later added **32bit** capabilities. When it came to inventing **64bit** however, AMD took the initiative and invented the modern architecture we use and love today. This is also why you rarely see **x86** anymore, but rather the AMD terms **x64** or **amd_64** (which is the same). However, those architectures still base on the old x86 architecture and are still compatible with the Intel 8086 processor.

This long backward compatibility is a major reason why x86 remains dominant in desktop and server environments.

## Clock Speed and Benchmarks

CPUs require a clock to synchronize operations. A clock speed of **4 GHz** means the CPU performs **4 billion clock cycles per second**. This does not mean it executes 4 billion instructions per second, as many instructions require multiple cycles.

Higher clock speed generally improves performance, but it is only one factor. Architecture efficiency, instruction decoding, memory access, and cache behavior are equally important.

Because raw specifications are misleading, performance is usually evaluated using **benchmarks**. Sites like [PassMark](https://www.cpubenchmark.net/) provide general-purpose comparisons and price-to-performance metrics.

However, general benchmarks do not reflect all workloads. For example, CPUs with large 3D caches may perform exceptionally well in games while scoring lower in productivity benchmarks.

If you have a **specific use case** (gaming, AI, data science, virtualization), targeted benchmarks and specialized reviews are far more useful.

## Cores

Modern CPUs contain multiple **cores**, each capable of executing instructions independently. A core is essentially the internals of a CPU copied for parallel execution.

- More cores improve performance for parallel workloads
- Single-threaded applications benefit less from additional cores
- Performance depends heavily on software design

Not all programs scale well across many cores, which is why high core counts are not always beneficial.

Some wordings we use:

| # Cores | Term        |
| ------- | ----        |
| 1       | Single-Core |
| 2       | Dual-Core   |
| 4       | Quad-Core   |
| 8       | Octa-Core   |
| 16      | Hexa-Core   |


## Cache
Accessing main memory (RAM) is slow compared to CPU speeds (1000+ CPU cycles to access data). To reduce latency, CPUs use caches:

- **L1 cache** – very small, extremely fast (1-5 CPU cycles), per core
- **L2 cache** – larger, slightly slower (10-20 CPU cycles)
- **L3 cache** – slow (30-50 CPU cycles), shared across cores

Technologies like **3D V-Cache** increase cache capacity, significantly improving performance in cache-sensitive workloads such as gaming.

TODO: image

## Extensions

Modern CPUs include specialized features for certain workloads:

- **Pipelining** – overlapping instruction stages to increase throughput
- **SIMD / vector extensions** – process multiple data elements at once
- **Virtualization extensions** – efficient virtual machines (Intel VT-x, AMD-V)
- **Security extensions** – memory protection and isolation

These features can dramatically improve performance for the right workload.

## Heat and Power

CPUs generate heat due to electrical resistance and transistor switching. **TDP (Thermal Design Power)** describes the expected heat output under sustained load. The higher the heat output, the more cooling you need and the more power you loose. CPUs may be built with **Turbo frequencies**  which provide temporary boosts if you are willing to accept higher temperatures and power consumptions. If you want to go even beyond the turbo frequencies, you can also **overclock** the CPU. When overclocking, you put a lot more power and stress on the CPU, which can damage or kill it. You can get a lot more performance with overclocking, but also risk your computer if you are not cautious.

Thermal and power limits often determine real-world performance more than specifications. This is one reason why mobile devices typically perform worse for the same money. Special mobile CPUs are optimized for the power and thermal constrains.

## Summary

A CPU is far more than clock speed and core count. Performance depends on:

- architecture and ISA
- cache hierarchy
- parallelism
- power and thermal limits
- workload characteristics
- much more

Benchmarks are useful for general comparisons, but choosing the *right* CPU requires understanding how it will be used. For specialized workloads, following dedicated review sites and content creators is the best way to make an informed decision.