---
date: '2026-01-03T11:35:51Z'
draft: true
title: 'GPUs'
image: '/images/gpus.webp'
tags: ["hardware","gpus", "a+"]
---

The **Graphics Processing Unit (GPU)** is a specialized processor designed to handle large amounts of data in parallel. It is a processor optimized for executing the same instruction on many data elements at once. Instead of a handful of cores operating independantly, it consists of thousands of smaller compute units that execute the same instructions in parallel. This makes it ideal for tasks such as:
 - drawing pixels to a screen
 - transforming 3D geometry
 - shading and lighting calculations
 - video encoding and decoding
 - matrix and vector math

While its original purpose was rendering graphics, modern GPUs are also used for general-purpose computing, scientific workloads, machine learning, artificial intelligence, and video processing.

In a modern computer system, the GPU works alongside the CPU. The CPU focuses on logic, control flow, and sequential tasks, while the GPU excels at massively parallel operations on large datasets.

## Video Memory (VRAM)

GPUs use their own dedicated memory called **Video RAM (VRAM)**. This is especially important since transfering data from the RAM to the GPU takes a lot of time. VRAM allows the GPU to access memory quickly. More VRAM makes the GPU more expensive, however if you have too little VRAM the CPU has to constantly load data to the GPU, resulting in slower prosessing and lagging games. The amount of memory needed depends on the use-case and games you play.

## Integrated and Discrete/Dedicated GPUs

**Integrated GPUS (iGPU)** are built into the CPU and use the system RAM. This drastically lowers power consumption and is the standard for mobile devices. However, gaming laptops typically come with an integrated GPU for power saving and a dedicated GPU for gaming.

**Discrete/Dedicated GPUs (dGPU)** are the typical video cards or graphic cards you know. They are connected via PCIe and have much better performance.

> [!NOTE]
> Although for gaming a GPU is recommended, some games that are not video heavy like Minecraft work on iGPUs just fine.

## Benchmarking

Similar to CPUs, there are metrics like core count, clock speed, [TDP](./cpus.md#heat-and-power), and more, however, we are typically interested in benchmarks. General purpose benchmarks are provided by [VideocardBenchmark](https://www.videocardbenchmark.net/), but you can also look for benchmarks on the games and use-cases you typically have.

## Chips vs Cards

**NVIDIA**, **AMD**, and, since recently, **Intel** produce GPU chips. However, you rarely buy videocards from them. Other producers like **ASUS**, **MSI**, **Gigabyte**, **ASRock** (to name a few) use GPU chips from the big providers and solder them on their own video cards.

## Display Connection

A consideration when chosing a video card is the available connections. While modern video cards mainly come with DisplayPort and maybe HDMI, there are numerous more possible connections. Especially on older or specialised cards:

 - **Video Graphics Array (VGA)** analog connection, mainly legacy and obsolete
 - **Digital Visual Interface (DVI)** comes in multible variations, served as a digital alternative to VGA
 - **High-Definition Multimedia Interface (HDMI)** is a digital interface that can keep up with high resolutions and refresh rates, and therefore replaced VGA and DVI by now. It also supports audio.
 - **DisplayPort** provides even Higher throughput, and is preferred over HDMI, but didn't fully replace it (yet)
 - **USB-C** really is display port over USB. It is mainly seen in compact systems like mini PCs and mobile devices.

TODO: elaborate more on different DVI variations