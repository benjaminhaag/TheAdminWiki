---
date: '2026-01-02T21:04:50Z'
draft: true
title: 'Cooling'
image: '/images/cooling.webp'
tags: ["hardware","cooling", "a+"]
---

Modern computers generate a lot of heat. Every time electricity flows through a component, some of that electrical energy is converted into heat. The components most prone to extensive heat generation are **CPU**, **GPU**, and **PSU**.

It is common for components to get pretty warm. In fact, most components start peaking at around **~40 °C (100 °F)**. Typical operation temperatures are:

 - **CPU:** ~40-90 °C (100-190 °F)
 - **GPU:** ~35-85 °C (95-185 °F)
 - **PSU:** ~40-60 °C (100-140 °F)

The exact ranges are specified by the manufacturer. When a component exceeds these temperatures, it protects itself by:

 - **Thermal throttling** - The component slows itself down to reduce power consumption and heat output. This keeps the temperature from rising further but reduces performance.
 - **Emergency shutdown** - If throttling isn't enough and the temperature keeps climbing, the system will shut down completely.

Tp avoid triggering both mechanisms and therefore retain optimal performance, you need proper **cooling**

## Passive vs Active Cooling

There are passive and active cooling. **Passive cooling**, entirely relies on the fact that heat eventually radiates away on its own. To support this process, **heat spreaders** and **heat sinks** increase the surface to speed up the process. This is enough for smaller components like low-energy CPUs (like in the raspberry PI) or Memory / Storage.

**Active cooling** further supports heat transportation by using **fans** to actively move air across the hot surface, or, even better transporting heat away using **liquids**.

## Heat Spreader

> [!WARNING]
> **PSUs** and **GPUs** should only be opened by professionals! PSUs contain dangerous electrical components, GPUs are fragile and can easily be broken!

**PSUs** and **GPUs** usually come with preinstalled fans for cooling. **PSUs** typically don't get too hot, and **GPUs** usually have adequate air cooling from factory. **CPUs** on the other hand commonly come without proper cooling installed. Instead, CPUs (more precisely _CPU dies_) come in a metal casing that acts as a so-called **heat spreader**. Heat spreaders use the same concept as heat sinks by increasing the surface area of the CPU, so that proper cooling mechanisms can pick up the heat more efficiently.

TODO: image

GPUs also have such heat spreaders. If you open the GPU you can install custom cooling on it to improve performance.

## Heat Sink

**Heat sinks** are metal constructs of various size that sit on top of a **heat spreader**. They take heat from the heat spreader and distribute on a much larger surface area.

TODO: image

## Air Cooling

Air cooling works with the principle of **fans** pulling **cool air** into the system, the air picking up **heat** from the **heat sink** and pushing **warm air** out of the system.

TODO: image

## Liquid Cooling

With liquid cooling, a **heat block** is attached to the **heat spreader** to pick up the heat. **Pumps** pump **liquid (coolant)**, often **distilled water**, through the heatblock to the **radiator**. The radiator is similar to the **heat sink** in air cooling and additional **fans** transfer the heat away.

The main advantage with liquid cooling is the fact that the radiator is not as limited in space, since it does not need to be mounted on the CPU itself. With correct fan configuration, it additionally can be placed with direct access to cool (room temperature) air, compared to heat sinks using warmer air from inside the case. Consequently, liquid cooling has the potential to cool components much more efficiently.

### Closed Loops / All in one (AIO)

**AIOs** are prebuilt liquid coolers where the pump, tubing, and radiator are sealed together. They’re maintenance-free and easy to install, making them the most popular liquid cooling option for desktops.

### Open Loops / Custom Loops

Custom loops use separate components — pump, reservoir, tubing, and radiator — that you assemble yourself. They offer the best performance and flexibility (can be used to cool CPU, GPU, RAM, even storage), but require maintenance and are more expensive.

> [!WARNING]
> If you make a mistake and the cooling breaks, water get's all over your components. Although it is cool do build your own custom loop, be careful.

### Reservoir

If you decide for custom loops, you will want to add a **liquid reservoir**. These can **ease maintainance** and **reduce air bubbles** in the system.

## Heat Pipes & Vapor Chambers

**Heat Pipes** are **sealed** copper or aluminum pipes filled with liquid. They don't have a pump like liquid cooling. Instead, they rely on the effect that **liquid** picks up heat and becomes vapor. The **vapor** floats to the top where the heat gets taken away. The vapor then cools down, becomes a liquid, flows down again and cools the system. Heat Pipes are built into many modern **Heat sinks**

**Vapor Chambers** work on the same principle, but are flattened and optimized to work in small space like **GPUs** and **Laptops**.

## Thermal Paste

The surfaces of **heat spreaders** and **heat sinks** can feel very smooth, but microscopically, there are **very rough**. This roughness decreases the contact between both, therefore reduces heat conductivity and consequently drastically brings down the efficiency of the coolor.

**Thermal paste** fills these microscopic gabs to **maximize thermal conductivity**.

Thermal paste can vary in
 - **viscosity**
   - low viscosity (runny) → easy to spread, but messy to apply
   - high viscosity (thick) → easy to apply, might cause air pockets
 - **Conductivity**
   - Standord → ~4-8 W/m*K
   - High Perfarmance → ~10-15 W/m*K
   - Liquid metal → 40-80+ W/m*K (can cause damage to components!)
 - **Consistency**
   - Ceramic-based → no electrical conductivity, safe, cheap, decent performance
   - Metal/Oxide based → slightly conductive, better performance
   - Liquid Metal → best performance, electrically conductive (dangerous)

> [!TIP]
> Thermal paste can dry out over time. For PCs and servers, a reapplication every **2-5 years** is good practice. For labpots, reapplying every **6-12 months** is recommended due to higher temperatures and worse cooling in mobile devices.

> [!WARNING]
> **Metal and oxide based** thermal paste (silver, carbon, diamond particles) as well as **Liquid Metal** can conduct electricity and, if spilled, damage components.

> [!WARNING]
> **Liquid Metal** thermal paste (gassium alloys) can **corrode aluminum** and must only be used with **copper** and **nickel** cooling components.

## Thermal Pads

Thermal pads serve the same purpose as thermal paste. However, they are **easier to apply**, **last longer**, but are **less effective**. They are mainly used where heat is less of an issue like **power supplies** and **GPUs**.

## Fans

Both, **air cooling** and **liquid cooling** rely on fans to provide proper **airflow** to transfer heat away. Fans vary in
 - **Cubic feet per Minute**
   - describes the amount of air they move
 - **noice rating**
    - describes how loud they are during operation (~25db is considered quiet)

## Troubleshooting

Even with proper cooling, computers can overheat if something goes wrong. Here are the most common causes and how to fix them:

### High Load
#### Problem
High load can lead to high temperatures. Especially **browser tabs** or **malware** can lead to unexpectedly high load.
#### Fix
Check the system for high load (Task Manager) and run anti-malware scans.

### Dust Buildup
#### Problem
Dust acts like a blanket inside your PC, clogging fans, heatsinks, and filters. This reduces airflow and traps heat.
#### Fix
Power down your system, open the case, and use compressed air or a soft brush to clean fans, heatsinks, and vents. Consider adding dust filters if you don’t already have them.

Additionally, make sure to always have a slightly positive air pressure (more air being pushed into the case then being pulled out). This generally leads to noticeably less dust in the case.

> [!WARNING]
> Be careful while using compressed air on fans. The air can make the fans spin "manually", making them act as generators and leading to the production of electricity. This can potentiall damage components. It is best to hold fans while cleaning, to stop them from spinning. 

### Dry Thermal Paste
#### Problem
After a few years, thermal paste dries out and loses effectiveness, leading to higher temperatures. Depending on the usage of the computer, thermal paste typically lasts **2-5 years** before you have to reapply. However, whenever you seperate the components connected via thermal paste, you should replace it anyway.
#### Fix
Clean off the old paste with isopropyl alcohol and reapply new paste.

> [!TIP]
> Thermal paste can act as a strong adhesive between CPU and cooler. Before separating them, use the PC for a few minutes to increase temperature, making them easier to separate. Additionally, you can use a thin string (like dental floss) to "cut" through the thermal paste layer between the two.

> [!NOTE]
> Thermal Pads usually last **7-10 years** and rarely cause any issues. Replacing them only when absolutely necessary.

### Bad Airways
#### Problem
Fans spinning in the **wrong direction**, bad **cable management**, or other components blocking the airflow can lead to overheating.
#### Fix
Check airways and fan direction
 - **Front & Bottom → intake** (bring cool air in)
 - **Rear & Top fans → exhaust** (push hot air out)

### High Ambient Temperatures
#### Problem
Hot rooms can put additional stress on cooling.
#### Fix
If applicable, move the computer to a cooler room or install **Air Conditioning**. You can also try **liquid cooling** or, if you already do, **larger radiators**.

### Faulty Fans or Pump
#### Problem
Mechanical failure can stop a fan or pump from moving air/coolant.
#### Fix
Visually check all fans, listen for pump operation and check coolant levels.

### Case size
#### Problem
very compact cases sometimes can’t dissipate enough heat.
#### Fix
You'll need a larger case.