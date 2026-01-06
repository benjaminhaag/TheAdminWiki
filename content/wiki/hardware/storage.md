---
date: '2026-01-03T11:35:29Z'
draft: true
title: 'Storage'
image: '/images/storage.webp'
tags: ["hardware","storage", "a+"]
---

Storage devices can be built into the computer or externally plugged in. They consist of large amounts of non-volatile memory, allowing to permanently (with limits) store data. They do not need a consistent source of power to keep said data stored.

## Capacity

The most important metric of storage devices is the capacity, or how much data it can hold. However, this is also the most confusing metric.

When talking about storage device capacity, we talk in **bytes (B)**, where **1B = 8 bit (b)** (one bit can hold exactly one of two values: **0 or 1**). Since storage devices can hold huge amounts of data, the unit _byte_ quickly becomes impractical. Consequently, units like Kilobyte, Megabyte, and so on are used instead. However, here is where thinks get complicated.

Because bytes are addressed using the binary system, manufacturers used to produce memory and mass storage in sizes that are powers of two. This way, the entire address bus is used. This also means, 1000 Bytes doesn't make a lot of sense and instead they put in 1024. This also affected how kilobytes and megabytes were historically used. **1kB = 1024B**, **1MB = 1024kB**, and so on. However, things have changed and manufacturers now use the International System of Units (SI) where **1kB = 1000B**. This can cause confusion, because Systems like Windows still use the old standard and show e.g. a 1TB drive as 931GB.

Because of this confusion, the International Electrotechnical Commission (IEC) defined a new, independant standard that defined **1 kibibyte(KiB) = 1024B**, **1 mebibyte(MiB) = 1024KiB** and so on. Linux uses this and shows a 1TB drive as 931GiB.

> [!NOTE]
> To further stir up confusion, RAM is still produced in binary and still uses the old system where **1GB = 1024MB**.

---

## Connection Standards

The standards **Advanced Technology Attachment (ATA)** and **Small Computer System Interface (SCSI)** define how Software and Drives can communicate with each other. This includes commands, connectors, and cables.


| **Interface\Feature** | **Usage**       | **Speed** |
| --------------------- | --------------- | --------- |
| **PATA**              | old PCs         | 133 MB/s  |
| **SCSI**              | old servers     | 320 MB/s  |
| **SATA**              | modern PCs      | 6 Gb/s    |
| **SAS**               | modern servers  | 22.5 Gb/s |
| **eSATA**             | external drives | 6 Gb/s    |
| **iSCSI**             | ethernet        | ethernet  |


### ATA

In the early days, ATA defined a wide bus called **ribbon cable** with 40 (later 80) wires that parallelly transferred the data back and forth. This standard was also known as **Parallel ATA (PATA)** or **Integrated Drive Electronics (IDE)** for marketing purposes. PATA could reach a speed of up to **133 MB/s**

Later, PATA got replaced by **Serial ATA (SATA)** or **Advanced Host Controller Interface (AHCI)**. While it might sound counter-intuitive that a serial connection is faster than parallel, the tight timing necessary for multiple bits to arrive at the same time actually slow things down. SATA comes with a staggering speed of up to **6 Gb/s**.

Additionally to the improved speed, the SATA standard also introduced new features like
 - **query native block size** (discussed in the next section)
 - **Native Command Queuing (NCQ)** that allows the drive to reorder commands to reduce mechanical latency, 
 - **hot swapping**
and many more features necessary in a modern environment.

> [!NOTE]
> If you use a very old drive or OS, you can still go into the UEFI/BIOS settings and set the mode to IDE instead of AHCI.

### SCSI

**Small Computer System Interface (SCSI)** is a competing standard to ATA. However, while ATA is more popular in Workstations and PCs, SCSI is more popular in server and enterprice systems. Speeds for Parallel SCSI were up to **320 MB/s** while the modern **Serial Attached SCSI (SAS)** can reach up to **22.5 Gb/s**.

### Logical Block Addressing (LBA)

Every drive is different. To address bytes Optical Media uses Tracks and Sectors, Hard Drives use Head, Sector, and Cylinder, while SSDs use Pages and Blocks. Furthermore, Sectors and blocks can be of different sizes like 512, 1024, or 4096 bytes. 

To unify addressing of bytes **Logical Block Addressing (LBA)** was introduced. It provides **blocks** independant from the underlying technology. For compatibility reasons, blocks are always **512 bytes** by default. However, with AHCI, the Operating System can query the actual block size and enable native communication for much higher performance.

LBA is provided by the Drive's firmware and serves as a standard interface that the computer can talk to. For optical media, the disk reader provides LBA functionality. LBA is defined by ATA (version 2+), as well as SCSI.

Thanks to LBA, Drives of any technology *"Just Work"*. However, sometimes drivers are required to leverage the full performance potential of the drive.

> [!NOTE]
> Before ATA-2, older ATA used Cylinder-Head-Sector (CHS) addressing instead. While CHS is still part of ATA, SATA on the other hand discarded this legacy feature.

### eSATA

**eSATA** was a standard for external drives. However, with USB getting better and better, eSATA got obsolete before it could take off.

### iSCSI

**internet Small Computer System Interface (iSCSI)** is a protocol used over an **Ethernet** Network to provide data to a remote system. iSCSI introduces challenges, because the **speed** and **delay** depend on the underlying ethernet technoloy.

---

## TODO:

 - [Optical Media](optical.md)
 - [Hard Drives](hdd.md)
 - [Solid State Drives](ssd.md)
 - [Removable Drives](removable.md)