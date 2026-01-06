---
date: '2026-01-02T21:04:55Z'
draft: true
title: 'PSUs'
image: '/images/psus.webp'
tags: ["hardware","psus", "a+"]
---

A **Power Supply Unit (PSU)** converts **alternating current (AC)** from the wall outlet (commonly 110–120 V in North America or 220–240 V in most of Europe/Asia) into **direct current (DC)** voltages required by computer components.

> [!WARNING]
> PSUs deal with 110-240 V AC and contain large capacitors that can hold this power for hours. Although Power Supplies can be damaged internally, and it might be tempting to open them, remember that even unplugged PSUs can deliver **severe shocks**, **burns**, or **worse**. They can also be a hazard for your surroundings and cause **fire** and **explosions** if not handled with care.
> Only trained professionals should open them in a safe environment.


## Functionality

### Input

In the past, PSUs came with a switch between 110V and 220V. If you forget to set this switch, bad things could happen. Nowadays, most PSUs come with Active Power Factor Correction (APFC). APFC automatically detects the input voltage and prevents you from these mistakes.

### Rectification

A rectification circuit converts AC to unregulated DC.

### Filtering

Capacitors and coils smooth and clean the DC for a steady output. Power spikes can damage the PC components slowly. Cheap or used power supplies can cheap out here and result in premature failure of connected components.

### Output Rails

The PSU delivers rectified, and cleaned output in various voltages for different components. These seperately regulated voltage output lines are called rails.

 - **+12 V** → CPUs, GPUs, fans, drives
 - **+5 V** → legacy devices, USB power
 - **+3.3 V** → RAM, chipset, low-voltage logic
 - **+5 VSB (standby)** → powers features like wake-on-LAN, even when the PC is "off"

> [!TIP]
> The standard size is **ATX**. For smaller cases, **SFX** is a common size designed for SFF/mini-ITX cases.

## Connectors
A PSU connects to the different components of a computer through various cables. These can be **modular** (detachable) or **soldered** (fixed).

 -  **Non-modular** → All cables are permanently attached.
   - usually cheaper
   - arguably slightly more efficient (practically not noticable)
   - more messy if you don’t need every cable.  
 - **semi-modular** → essential cables attached, others modular
   - cables for e.g. CPU, RAM, Motherboard are attached
   - cables for e.g. fans, and drives can be attached modularily
   - usually a great sweet spot
 - **fully modular** → Every cable is detachable
   - easy cable management
   - easy cable replacement
  
> [!WARNING]
> With **modular** PSUs, you can change the cables if one is broken. However, make sure to always use **original** cables. The pinning is not standardized and people regularly fry their components by using a third party vendor's cobles.

### Common Connectors

#### ATX 24-pin
The 24-pin (sometimes 20+4-pin) connector is the main motherboard connector, provides all base voltages for the Motherboard, and the Memory.

TODO: image

#### CPU 4+4 pin (EPS Connector)

The CPU 4+4 pin connector is sometimes called EPS (EPS12V) because it first appeared in the Entry-Level Power Supply (EPS) specification, originally for servers and workstations. That specification standardized an 8-pin 12 V CPU connector.

On modern consumer PSUs, it’s usually split into 4+4 so it can also fit into older boards that only had a 4-pin CPU power socket.

The 4+4 Connector supplies 12V to the **Voltage Regulation Modules (VRM)** of the motherboard. VRMs regulate that voltage even further to match the **CPUs** demand.

TODO: image

#### PCIe 6+2 pin

Used for **GPUs**. The 6-pin delivers up to **75 W**, and the optional 2-pin raises it to **150 W**.  

Some GPUs require two of these, or use the more modern ATX 3.0 standard.

TODO: image

#### PCIe 12+4 pin (ATX 3.0 / Gen 5)

The new GPU connector. Supports up to **600 W** in a single cable with four additional sense pins for communication.

TODO: image

#### SATA power

SATA power connectors are thin connectors used for **drives**, and **accessories** like RGB controllers.

TODO: image

#### Molex

Molex connectors are used for more **fans**, older drives and some legacy peripherals. They are rarely needed today.

TODO: image

## Wattage

The wattage rating of a PSU defines its **maximum power output** across all rails combined. Choosing the right wattage is crucial:

- Too little → system crashes, shutdowns, or unstable operation.  
- Too much → wasted money and slightly lower efficiency.  

The right amount depends on your system’s **maximum load** and **future plans**.  


### System requirements
Every part of your computer draws power. How much exactly depends on the load of the part. However, knowing the **maximum (sum of all parts)** that might be drawn gives us a good estimation on how much wattage we should plan for.

### Efficiency and Headroom

PSUs are most efficient at **40-60% load** and should therefore stay in this range. Adding another **~20-30% headroom** on top of the maximum draw wattage should put you into that range.

### Future Proofing

If you plan for heavy upgrades (e.g. swapping the GPU for a much better later on), then plan ahead and buy more wattage in the first place.

## Energy Efficiency

Not all the power drawn from the wall is delivered to the PC — some is lost as **heat** inside the PSU. 

Higher efficiency means
 - less loss in heat
 - lower electricity bills
 - less heat and noise due to fans spinning
 - longer PSU lifespan

### 80 Plus Certification

The **80 Plus** efficiency rating measures how much power is effectively delivered.


TODO: table here


## Redundant PSU

You will rarely see a redundant PSU in a PC, because PSUs aren't exactly the most likely thing to fail throughout the lifespan of a Computer. But if guaranteed uptime is what you seek, especially in servers, redundant PSUs are a thing.

A redundant PSU is essentially **two PSUs** combined to one set of output rails with **hot-swappability**. You also plug **two powerchords** in (one for each unit). You can plug these into different circuits to reduce downtime.