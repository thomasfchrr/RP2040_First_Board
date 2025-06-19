# RP2040_First_Board

## Objective

I’m starting the design and assembly of a PCB centered around the **RP2040** microcontroller. The goal is to get hands-on experience with basic electronic circuit design (microcontroller + peripherals + power), PCB layout, and programming in a new environment. I’m using this GitHub repo to document the technical specs and lay out a clear working plan. This is a personal project, nothing formal, so I’m focusing more on the content than on polish. I’m coming in with very little electronics background and only some small prior experience. I plan to learn online through forums, YouTube tutorials, chatbots, and inspiration from other projects.

## Project Scope

I’m going to use only components I already have in stock (recycled), which saves me time on researching parts or ordering. This might not be the best choice of components, but it’s what I have, so I’m sticking with it.

### Microcontroller

I chose the **RP2040**, a dual-core ARM Cortex-M0+ running at 133 MHz, with 264 KB of RAM and an integrated USB 1.1 controller. It offers 30 versatile GPIO pins supporting ADC, PWM, I²C, SPI, and UART. It can be programmed in MicroPython or with the Pico C SDK. For this project, I’m going with the Pico SDK: programming in C lets me freely manage the dual-core, which isn’t possible with MicroPython (and I want to experiment with that).

### Flash

I’ll use a **25Q64JVSIQ**, a 64 Mbit (8 MB) SPI NOR flash memory with read speeds up to 104 MHz. Since the RP2040 has no internal flash, I need this external component to store firmware and non-volatile data.

### Display

I have a small OLED screen driven by the **SSD1306**, compatible with I²C/SPI, with a 128x32 monochrome resolution. It’s compact, low-power, and provides a simple visual interface for the project.

### Charge Controller

I’m using the **TP4056E**, a linear charger for a single-cell Li-Ion battery. It includes basic protections (overcharge, overdischarge, short circuit) and charges via USB. It’s perfect for powering a RP2040-based setup easily.

### Measurement IC

I also have an **INA3221**, a three-channel high-side voltage/current monitor (up to 26 V) with I²C interface. It will help me monitor power consumption on different rails, detect overloads, and so on.

### Connectors

I’m integrating a **16-pin female USB-C port**, compatible with USB 2.0. It’s compact and reversible, allowing both 5 V power input and USB communication — useful for charging via the **TP4056E** or programming the **RP2040**.

### Other

I plan to add two or three **LEDs** for quick debugging of the **RP2040** states (even though I already have the **SSD1306**, LEDs are handy and let me use some GPIO pins). I’ll also add some **buttons** to interact with the project, for example to navigate between features.
