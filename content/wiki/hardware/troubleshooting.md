---
date: '2026-01-02T21:04:21Z'
draft: false
title: 'Troubleshooting'
image: '/images/troubleshooting.webp'
tags: ["hardware","troubleshooting", "a+"]
---

This guide helps to identify and pinpoint common Hardware problems.

## Trouebleshooting Methodology

[CompTIA](https://www.comptia.org/) gives a step by step guide on how to troubleshoot any issue. You can find this guide in their latest A+ Exam Objectives as a prerequisite for the exam.

1. Identify the problem.
2. Establish a theory of probable cause (question the obvious).
   - Research knowledge base/internet, if applicable.
3. Test the theory to determine the cause.
4. Establish a plan of action to resolve the problem and implement the solution.
5. Verify full system functionality and, if applicable, implement preventative measures.
6. Document findings/lessons learned, actions, and outcomes.

### Deeper Thoughts.

Some of these steps might seem redundant or unnecessary (and certainly are sometimes) but for a deeper understanding what it can mean, here are my thoughts about when and why it is important to stick to this plan and when it makes sense to deviate.

#### 1. Identify the problem.

This step focuses on clearly defining what the issue actually is, not what might be causing it. For example, the problem is not “I forgot to turn on the power,” but rather “nothing happens when I try to turn on the PC.” While this distinction seems obvious, it’s a common area where technicians go wrong—especially when working with clients. Misunderstandings easily arise if assumptions are made about what the client means. Taking the time to ask questions, clarify symptoms, and restate the issue ensures that everyone agrees on what the real problem is before moving forward.

#### 2. Establish a theory of probable cause.

Once the problem is identified, the next step is to form a reasonable idea of what might be causing it. This often starts by questioning the obvious—such as checking connections, settings, or recent changes—before moving to more complex possibilities. At this stage, it’s not about proving the cause but about creating a starting point for investigation. Using resources like knowledge bases, documentation, or online forums can help you compare symptoms with known issues and refine your theory.

#### 3. Test the theory to determine the cause

After forming a theory, it must be tested to see if it actually explains the problem. This involves applying simple checks or changes to confirm whether the suspected cause is correct. If the theory doesn’t hold up, go back to step 2 and form a new one until the real cause is identified. The goal here is not to fix the issue just yet, but to be confident that you understand what’s behind it.

#### 4. Establish a plan of action to resolve the problem and implement the solution.
Once the root cause is confirmed, the next step is to decide how to fix it. Often there are multiple possible solutions, and it’s important to choose one that is effective while minimizing risk to the system and its data. Consider factors like downtime, cost, and potential side effects before proceeding. After selecting the best option, implement the solution carefully and document what you did so the process remains clear and repeatable.

> [!TIP]
> Sometimes the solution is as simple as turning on the power supply. In this case, step 4 is already done by step 3. But sometimes issues can be of larger scale. Maybe 100 Computers are affected, or a live system has an issue you troubleshooted on a test system. In these cases, the distinction between the two steps make total sense.


#### 5. Verify full system functionality and, if applicable, implement preventative measures.
After applying the solution, it’s essential to confirm that the system works completely as expected. Test all affected components to ensure the problem is fully resolved and nothing else was unintentionally impacted. If applicable, take steps to prevent the issue from recurring, such as applying updates, adjusting configurations, or educating the user. This ensures the fix is durable and reduces the likelihood of repeat problems.

> [!WARNING] 
> Ask the Client
> Again, working with clients isn't always easy. If another person brought in the issue, make sure **they** see the problem as resolved to avoid misunderstandings and unhappy customers.
> Let them test, and make sure they are happy.

#### 6. Document findings/lessons learned, actions, and outcomes.
Documentation is an ongoing part of troubleshooting, but this final step ensures everything is properly organized and clear. Record not only the final solution but also the theories tested—even those that turned out to be false—along with your reasoning and how you verified them. This creates a valuable reference for future issues, which may be similar but slightly different, and helps make subsequent troubleshooting faster and more accurate. Properly cleaned-up documentation preserves knowledge, supports continuous improvement, and ensures that lessons learned are accessible to others.

## Compatibility Checklist

- [ ] CPU socket is compatible with CPU
- [ ] Chipset is compatible with CPU
- [ ] Firmware version supports CPU (BIOS/UEFI)
- [ ] RAM speed matches motherboard and CPU (QVL)
- [ ] RAM sticks are installed in a compatible channel configuration
- [ ] RAM type is supported by CPU and MoBo (DDR version, ECC)
- [ ] RAM capacity is supported by MoBo and CPU (total and per slot)
- [ ] Power Supply supplies enough power
- [ ] Power Supply offers all necessary connectors
- [ ] VRMs supply enough power for the CPU
- [ ] Cooling is sufficient for the TDP
- [ ] GPU is not bottlenecked by CPU
- [ ] GPU is not bottlenecked by Display
- [ ] GPU supports display connections
- [ ] Display resolution and refresh rate is supported by GPU
- [ ] There are enough PCIe Lanes (check for lane sharing)
- [ ] PCIe version is supported
- [ ] You have Enough bays and connectors for SATA (some SATA get disabled if M.2 is used)
- [ ] M.2 supports NVMe (if required, some M.2 share laned with PCIe slots)
- [ ] Case has enough room and mounts for all components
- [ ] Airflow is good
- [ ] Firmware supports necessary features (VT-x, VT-d, AMD-V, IOMMU, SecureBoot, TPM)
- [ ] Drivers match the hardware and are up to date
- [ ] Check for Hardware requirements by your Software

## By Problem

### Overheating

Overheating of both, CPU and GPU, can have multiple causes. Check for:

 - **[High Load](./cooling.md#high-load)**
 - **[Dust Buildup](./cooling.md#dust-buildup)**
 - **[Dry Thermal Paste](./cooling.md#dry-thermal-paste)**
 - **[Bad Airways](./cooling.md#bad-airways)**
 - **[High Ambient Temperatures](./cooling.md#high-ambient-temperatures)**
 - **[Faulty Fans or Pump](./cooling.md#faulty-fans-or-pump)**
 - **[Case size](./cooling.md#case-size)**
