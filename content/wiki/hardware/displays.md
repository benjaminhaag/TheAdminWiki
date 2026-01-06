---
date: '2026-01-03T11:36:16Z'
draft: true
title: 'Displays'
image: '/images/displays.webp'
tags: ["hardware","displays", "a+"]
---

A **display** turns electronic information into visible images for us humans to consume. It takes signals from a computer, phone, TV tuner, or another source and visualizes them as **text**, **pictures**, or **video** that your eyes can see.

Displays are made up of a grid of **pixels (picture elements)**. Each pixel can change its brightness and color. When millions of these pixels are controlled together, they form the full image on the screen.

Every pixel is made up of three subpixels: **red**, **green**, and **blue**. By adjusting the brightness of each subpixel, mixing the colors additively, virtually any other color can be created. This principle is the same across nearly all modern display technologies, whether **LCD**, **OLED**, or others.

TODO: image

## Attributes

### Response Time

The **response time** measures how long an individual pixel takes to change from one state to another, often specified as **gray-to-gray** or  **black-to-white-to-black**. A slow pixel response may lead to visual artifacts such as **motion blur** or **ghosting** during fast-moving scenes.

> [!NOTE]
> The response time doesn’t dictate how fast one shown image can be replaced by another.

### Refresh Rate

The **refresh rate** indicates how many images per second the display can show, measured in **Hertz (Hz)** [1Hz = 1/s]. This is usually limited by the display controller, generated heat, and other technical constraints. On cheaper LCDs, slow response time can also reduce effective refresh quality.

### Pixel Desity

**Pixel density** describes how tightly pixels are packed over a given distance, measured in **pixels per inch (ppi)**. Higher pixel density means smaller pixels and sharper images.

However, pixel density alone doesn’t fully determine perceived sharpness, as viewing distance plays a major role. A TV viewed from across the room doesn’t need the same ppi as a monitor viewed from 20 inches away.

### Resolution

**Resolution** defines the total number of pixels horizontally and vertically. It standardizes image sharpness independently of screen size. Common resolutions fall into a few aspect ratio categories:

#### 4:3

 - **VGA** 640:480
 - **SVGA** 800:600
 - **SXGA** 1280:1024
 - **UXGA** 1600:1200

The **4:3** category reflects older display formats based on early TV ratios. Windows may still default to **SVGA** if driver issues occur.

#### 16:10

 - **WSXGA** 1440:900
 - **WUXGA** 1920:1200

Originally inspired by the **golden ratio**, 16:10 eventually lost popularity to 16:9 due to better alignment with HDTV and multimedia content.

#### HDTV (16:9)

 - **720p** 1366:768
 - **1080p** 1920:1080
 - **1440p / QHD / WQHD** 2560:1440
 - **4K / UHD** 3840:2160
 - **5K** 5120:2880

The **“p”** denotes **progressive scan**, where each frame is drawn line by line in order. Older **interlaced** formats (e.g., 1080i) drew 
alternating lines per frame, reducing perceived quality for better refresh rates.

#### 21:9

 - **UWFHD** 2560:1080
 - **UWQHD** 3440:1440
 - **UW4K** 4320:1800
 - **5K Ultrawide** 5120:2160

The ultrawide format most often denoted as "21:9" originally was introduced to better show cinema-movies, frequently filmed in said format. It additionally gained popularity for its additional screen real-e
state for productivity and increased FOV for gaming. While somewhat established, not all games support the 21:9 format.

#### 32:9

 - **DFHD** 3840:1080
 - **DQHD** 5120:1440

An even further extended format is the "Double-" or "Dual-" standards, being twice as wide as their 16:9 counter-part. As for the 21:9 format, it originates from cinema. As 21:9 it provides additional real 
estate and can give a more immersive gaming experience. Since 32:9 is not yet as established, incompatibilities need to be expected.

### Color gamut

The **color gamut** represents the range of colors a display can produce.

Sometimes, especially with newer RGB E-Inc displays, the actual number of colors is given. However, more common with regular displays is a percentage on a defined referenced gamut such as **CIE 1931**.

The ***CIE 1931*** is based on the human visual perception and, therefore, one of the most common spectrums to compare color gamuts of different devices. Other spectrums are used for other purposes and include

 - **CIE 1932** - general comparison
 - **sRGB** - Web and consumer devices
 - **Adobe RGB** - photography, media and printing
 - **DCI-P3** - cinema and high-end displays
 - **Rec.2020 (BT.2020)** - UHD and HDR TVs

### Color accuracy

**Color accuracy** measures how close the displayed colors are to their intended reference, usually quantified with **ΔE**.
Lower ΔE means better color fidelity. High gamut does not guarantee high accuracy.

### Brightness

**Brightness** indicates how much light the display emits, measured in **nits (nt)**.

 - A good general-purpose display averages 200–500 nits.
 - Home theaters can work with lower brightness (~200–300 nits)
 - Bright rooms may require higher brightness (~400–500 nits or more)

## LCD

An LCD screen is built from several layers that all work together to form an image. At the back sits the power supply, which delivers the different voltages needed by the display. The logic board processes the incoming signal from HDMI, DisplayPort, and other sources, and translates it into instructions for each pixel.

Because liquid crystals themselves do not emit light, a separate backlight is required. In older screens this was provided by **Cold Cathode Fluorescent Lamps (CCLF)**, while modern displays almost always use **LEDs**. The raw light is not distributed evenly, so it passes through **diffuser sheets** and **light guides** that spread it uniformly across the panel.

Next, the light meets the first **polarizer**. Polarizers only allow light waves that are aligned in a certain direction (_polarization_) to pass through. A second polarizer is placed in front of the panel, rotated by 90 degrees. With only these two polarizers, almost no light would pass, since the polarized light that passes through the first polarizer, does not adhere to the polarization of the second. Consequently, all light would be blocked and the screen would remain dark.

Between the polarizers sits the **liquid crystal layer**. These crystals can be controlled by applying voltage across transparent electrodes. In the simplest and most common form, the **twisted nematic (TN)** cell, the molecules are arranged straight when no voltage is applied. Light passes through as it is. When voltage is applied, the molecules twist. This twist rotates the polarization of the light (by up to 90 degrees), allowing it to pass through the second polarizer, making the light visible to the eye. In this way, each pixel can be switched between bright and dark.

Other liquid crystal technologies work in a similar way but differ in how the molecules move. **In-plane switching (IPS)** panels rotate the molecules within the plane of the screen, which improves color accuracy and viewing angles. **Vertical alignment (VA)** panels keep the molecules upright in their resting state and tilt them when voltage is applied, resulting in deeper blacks and higher contrast. **Twisted nematic (TN)**, in contrast, is cheaper and faster but has weaker colors and limited viewing angles.

All of these approaches share the same basic principle: a backlight shines through polarizers, liquid crystals, and color filters, and by controlling the orientation of the crystals with voltage, the screen determines how much light each pixel lets through.

// TODO: image

#### Inverter

**Cold Cathode Fluorescent Lamps (CCFL)** operate on **high-frequency AC** at around **600–700 V**, not on the low-voltage DC that the PSU delivers. To supply this, an **inverter** converts the DC from the PSU into high-voltage, high-frequency AC.

> [!Warning]
> Inverters can store high voltages even when the display is unplugged. Handle with caution, as they can cause serious injury.

### Mini-LED

Polarizers are never perfect. Even when two polarizers are exactly perpendicular, some light still passes through. This is why dark areas appear as dark gray instead of true black.

To reduce this effect, **Mini-LED backlights** were developed. Instead of one large backlight, they use many individually controlled mini-LEDs, each illuminating only a small cluster of pixels. This allows dark areas of the image to be lit much less. So, for example, if one half of the screen is black and the other half is white, the black side looks significantly darker than with traditional LED or CCFL backlights.

However, when a black pixel is right next to a bright white pixel, some light still bleeds into the dark area. Mini-LED improves contrast, but it does not achieve perfect black.

## OLED

**Organic Light Emitting Diode (OLED)** displays work differently from LCDs. Each pixel is a set of three ogranic LEDs (red, green and blue) that generate their own colored light, so there is no need for a separate backlight or liquid-crystal layer. When a pixel is off, it produces no light at all, resulting in true black.

This gives OLED panels:
 - **Perfect blacks** and very high contrast.
 - **Thinner screens**, since no backlight layer is required.
 - **Faster response times**, because each pixel switches on and off directly.

The main drawbacks are:
 - **Higher cost** compared to LCD.
 - Risk of **burn-in**, where static images can leave a permanent mark on the screen, since LEDs wear off.

## Comparison

|                 | Twisted Nematic | Vertical Alignment | In-Plane Switching | OLED       |
| --------------- | --------------- | ------------------ | ------------------ | ---------- |
| Response Time   | 1-3 ms          | 4-8 ms             | 4-8 ms             | <1ms       |
| Refresh Rate    | 240-500 Hz      | 165-240 Hz         | 240-360 Hz         | 120-240 Hz |
| Color Gamut     | 65-70%          | 75-85%             | 80-99%             | >99%       |
| Color Accuracy  | Bad             | Medium             | High               | Best       |
| angle stability | Bad             | Medium             | High               | Best       |


> [!NOTE]
> These numbers are just averages for comparison. High-End displays can be much better and cheap ones much worse. Always compare the data sheets.

## Touch Digitizer

A touch digitizer is the layer in a touchscreen that detects where your finger (or stylus) touches the display. It converts physical contact into an electronic signal that the device can understand.

There are two main types:

 1. **Resistive touch digitizers**
   - Made of two thin, conductive layers separated by a small gap.
   - When you press the screen, the layers touch, completing a circuit.
   - The device measures the voltage change to determine the touch position.
   - **Pros**: Works with fingers, styluses, or gloves; cheaper to produce.
   - **Cons**: Less precise, lower clarity, and supports only single-touch in most cases.

 2. **Capacitive touch digitizers**
   - Made of a transparent conductive layer that holds an electrical charge.
   - When your finger touches the screen, it disturbs the local electric field.
   - Sensors measure the change in capacitance to determine the touch location.
   - **Pros**: High precision, supports multi-touch gestures, better transparency.
   - **Cons**: Usually requires a bare finger or specialized stylus.

Modern touchscreens often combine LCD or OLED displays with a **capacitive digitizer** to allow both high-quality visuals and accurate touch input.