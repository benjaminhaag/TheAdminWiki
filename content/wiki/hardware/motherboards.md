---
date: '2026-01-03T11:32:53Z'
draft: true
title: 'Motherboards'
image: '/images/mobos.webp'
tags: ["hardware","motherboards", "a+"]
---

The **motherboard (MoBo)** *(also called mainboard)* is the central backbone of a computer system. While the CPU performs calculations and the RAM stores data, the motherboard physically holds all components together, electrically connects them, and defines how they communicate. A system can only be as capable, stable, and expandable as its motherboard allows.

## What Is a Motherboard?

At a high level, the motherboard:

 - Physically mounts all core components
 - Electrically connects and coordinates them
 - Distributes power to CPU, RAM, and peripherals
 - Provides firmware to start the system

Without a motherboard, the individual components of a computer cannot function as a system.

### Quarz Crystal

Older motherboard came with electronical timers. Modern motherboards provide a quarts crystal. This crystar gives the tick to synchronize all components and usually operates at **100-500MHz**. RAM multiplies this speed using [DDR](./memory.md#ddr) technology. CPUs feed the base clock into **Phase-Locked Loops** to multiply that clock up to the Gigaherz they need.

## CPU Compatibility

The motherboard defines which PCUs can be used by providing a certain **CPU Socket**, **Chipset**, and **Voltage Regulator Modules (VRMs)**. The later one mostly determines if and how much you can overclock the CPU, but the CPU Socket must be physically compatible with the CPU, otherwise the CPU simply does not fit. The Chipset gets released alongside a CPU generation and might be compatible with multiple CPUs that share tha same socket, but not necessarily all of them. The Chipset holds firmware, configurations, and information for interoperability between CPU and other components.

> [!TIP]
> Although this might sound like a lot of work and research, you can simplify everything by selecting the CPU first and then search for motherboard with compatible chipsets (e.g. on [PCPartPicker](https://pcpartpicker.com/)).

### Socket Types

Sockets differ between Intel and AMD, but also between processor production lines and generations. Typical form factors are:

 - **Land Grid Array (LGA)** - pins are on the motherboard, the CPU has lands as counterparts. Mainly used by Intel, but recently adopted by AMD with the AM5 socket.
 - **Pin Grid Array (PGA)** - pins are on the CPU, holes on the motherboard. (Older) AMD CPUs used this socket type
 - **Ball Grid Array (BGA)** - especially mobile and laptop CPUs use BGA. Here, the CPU has soldering led balls that get heatet whet mounted. BGA is used to permanently solder the CPU for better connectivity.

### Multisocket

Especially server hardware might offer **Multisocket Motherboards** where you can mount multiple CPUs at once to let them operate in tandem.

## Chipset

Historically, motherbeards hosted two chipsets - **Northbridge** and **Southbridge**. The northbridge is responsible to coordinate the communication between RAM and CPU. The Southbridge is responsible to coordinate the communication with the rest of the system (Graphics Card, USB, Drives, Network, Audio, everithing else). Nowadays, the northbridge became a bottleneck between the RAM and the CPU, so CPU manufacturers moved the northbridge into the CPU. Therefore, the chipset is mainly the southbridge on the motherboard.

The chipset defines the capabilities of the system. If the southbridge does not implement USB3.0, there will not be a working USB3.0 on the system. Therefore, when choosing the Motherboard, make sure it is compatible with your needs such as:

 - maximum RAM
 - type of RAM (DDR3, DDR4, ECC,...)
 - number of graphics cards
 - PCIE lanes (x1, x4, x8, x16)
 - USB protocols
 - WiFi
 - number of drives
 - types of drives (M.2, NVMe, SATA, HotSwapping)

> [!TIP]
> When you use [PCPartPicker](https://pcpartpicker.com/), you can select your CPU to filter incompatible motherboard, and then select what connections you want and how many. This way you can see what motherboards you can choose from.

## Form Factors

Motherboards come in different form factors to fit all kinds of needs. The important part is to know how much room you have for your build. A mini PC should not use a standard ATX motherboard. Also for choosing the right case it is important to know the size of your board.

| Form Factor | Size (mm)  | Typical Use            |
| ----------- | ---------- | ---------------------- |
| E-ATX       | ~305 × 330 | Workstations / Servers |
| ATX         | 305 × 244  | Desktops               |
| Micro-ATX   | 244 × 244  | Compact desktops       |
| Mini-ITX    | 170 × 170  | Small form factor      |
| Nano-ITX    | 120 × 120  | Embedded systems       |

> [!TIP]
> Motherboards should not be mounted directly onto the case, but with a little bit of offset. Usually cases already have standoffs built in or come with htem. However, if not, make sure to plan for some extra space. Since cases are metal, it can be fatal if the back of the motherboard touches the case and shorts some components.

## BIOS/UEFI

Every motherboard contains firmware that initializes the system and starts the boot process. Traditionally this firmware was called the **BIOS (Basic Input/Output System)**. Modern systems use **UEFI (Unified Extensible Firmware Interface)**, which replaces and extends the old BIOS concept.

The firmware is stored on a flash memory chip directly on the motherboard.

BIOS/UEFI is responsible for:
 - Initializing CPU, RAM, chipset, and peripherals
 - Performing POST (Power-On Self Test)
 - Providing hardware configuration menus
 - Selecting and launching the bootloader
 - Handing control over to the operating system

Without functional firmware, a system cannot boot.

The BIOS/UEFI is tightly coupled to the motherboard, as it needs to be compatible. Therefore, choosing the right motherboard also influences the capabilities of the BIOS/UEFI. If you have special requirements, such as RAID configurations, research which BIOS/UEFI supports them.

> [!WARNING]
> You can update the BIOS/UEFI, but this carries a huge risk. If something goes wrong, your motherboard renders unusable. Some motherboards come with a bockup chip to bail you out if you broke the firmware, but I would still only update if absolutely necessary.

## RAM

The motherboard dictates what RAM you need. It provides and limits:

 - number of RAM slots
 - supported form factor (DIMM, SO-DIMM)
 - channel configuration (single, dual, quad)
 - maximum amount
 - supported speeds

> [!WARNING]
> Although a high end motherboard might support higher RAM speeds than the CPU you choose, that doesn't mean its a good idea to do so. The RAM speed of the CPU and Motherboard should match, or you should look for a cheaper alternative.

> [!TIP]
> With modern CPUS and XMP/EXPO, you can use higher rated RAM speeds than officially supported, as it gets overclocked by default. Just make sure the RAM-CPU combination is tested and stable. Officially tested combinations are listed in **Qualified Vendor Lists (QLVs)**, but other sources like your favourite tech website or content creators are just as good.

## I/O shield

Every motherboard has its own connectors out to the user. To make sure (almost) every case is compatible, a standardized I/O shield keeps the standard rectangular form on the top-left of the motherboard, while providing cut outs to the provided connectors.

> [!TIP]
> Most I/O shields are standardized, but some builds like mini computers provide alternative sizes.

## TPM, HSM

**Trusted Platform Modules (TPMs)** and **Hardware Security Modules (HSMs)** are special hardware to support cryptographic security on devices. While TPMs are typically used on consumer devices, HSMs are typically used on server hardware.

### TPM

A **Trusted Platform Module (TPM)** is a security component used to store cryptographic keys and perform security-related operations.

TPMs are used for:
 - disk encryption (e.g. BitLocker)
 - secure boot
 - device identity
 - OS integrity checks

Modern operating systems increasingly require TPM support for advanced security features.

### HSM

An **HSM (Hardware Security Module)** is a more advanced and specialized security device. Compared to TPMs, HSMs:
 - offer stronger isolation
 - support higher cryptographic workloads
 - are commonly used in enterprise environments

HSMs are typically separate PCIe cards or external appliances. They are rarely integrated into consumer motherboards and used for:
 - certificate authorities
 - key management systems
 - high-security environments