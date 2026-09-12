# My-first-linux-PCB

**CURRENTLY IN DEVELOPMENT!**

As my title clearly shows, this is my first PCB designed to work with Linux. I wanted to finish this project relatively quickly and easily, so you will notice while reading this that I took quite a few shortcuts when designing it, such as with my SoC, or should I say SiP?

The main goal of this project is not to make the smallest, fastest, or cheapest Linux computer possible. This is just a bring-up board. It is mainly a learning project. I wanted to see how far I could get designing a Linux-capable board myself, while learning about things like SiPs, power supplies and tolerances, boot media, high-speed interfaces like USB 2.0, power-related PCB layout, and Linux bring-up along the way.

## The SiP

For the processor, I decided to use an Allwinner V3s.

The V3s is an interesting SoC for a project like this because it contains quite a lot of the hardware needed for a Linux system in one package, so it made sense to design my first Linux board around it. Most importantly, it contains an ARM Cortex-A7 CPU, DDR2 memory inside the package, SD/MMC, and various other peripherals that I decided not to use for time and cost's sake, such as RGB parallel, MIPI CSI, the audio codec, and Ethernet.

This is also where the "SiP" part comes in.

Instead of having to route an external DDR memory bus myself, the V3s already has the memory integrated into the package.

This was a big shortcut, and it has some drawbacks. The biggest one is that I am stuck with the amount of memory provided by the V3s rather than being able to choose my own external RAM.

I wanted to learn how to design a Linux board without making the first version unnecessarily difficult. I will move to a more complicated SoC with external memory in a different project.

## What I am trying to build

The eventual goal is a small custom Linux handheld computer. As I said, this is just a bring-up board.

That future board is intended to include things such as:

* HDMI
* USB-C power
* One or multiple USB-C OTG connections
* Display support
* Maybe camera support
* Wi-Fi through an internal USB port
* Better power management and optimisation
* A comfortable size to hold

## Why I made this

I have already designed smaller microcontroller PCBs, but a Linux-capable board is a significant step up in complexity.

With a microcontroller, I can generally design the hardware, flash the firmware, and immediately start working with the board, as I found out.

A Linux system has many more things that have to work together. The processor has to boot properly, the storage has to work properly (I'm afraid that it won't), the device tree has to describe the board correctly (I might struggle a bit with this), and the Linux kernel has to support the peripherals I actually connected.

That makes this project much more interesting to me.

Another reason is that I want to understand DTBs and DTSes, so I can reverse-engineer the R36S console more easily... at least when I get better at PCB design.

## The shortcuts

This project is intentionally not my "ideal" design.

For example, using the V3s avoids having to design and route an external DDR memory interface, but it comes at the cost of being limited to the memory integrated into the V3s. I omitted Ethernet entirely because I knew that it would be annoying to route.

I also intend to use existing Linux support and device-tree work wherever possible rather than trying to write everything from scratch.

I would rather get one complicated-enough board working and understand why it works than spend months making an unnecessarily difficult first revision.

All I wanted was a working Linux board.

## What I have learned so far

This project has already taught me considerably more than I expected.

Some of the things I have had to learn include:

* General ARM SoC hardware design
* Power-rail design
* The basics of decoupling
* DDR and memory considerations
* SD/MMC
* USB's true complexity
* HDMI's true complexity
* Different MIPI interfaces
* Linux device trees
* Bootloaders and the early boot process
* PCB stackups and impedance matching
* Good ground planes and stitching vias
* High-speed PCB routing
* Component selection, with some help
* Proper datasheet reading
* Checking whether components are actually suitable for assembly
* Working around the limitations of PCB manufacturers

There are also plenty of things I still do not understand properly. That is one of the many reasons I am making this project.

## Current status

**In development.**

The schematic is complete, as is the PCB.

The next major milestone is getting the PCB manufactured and then finding out which parts of my design actually work.

I fully expect something to go wrong. (Either the USB-C ports or TF2.)

If the first revision does not boot, that will still be useful. I will have a real board to debug rather than another theoretical design sitting in EasyEDA.

## What comes next

The eventual goal is not simply to have a Linux handheld. It is to understand how the entire system works, from the hardware and PCB all the way up to Linux.

And this is only my first Linux PCB and 4th PCB I ever designed.

Thank you.

# Renders
<img width="1328" height="1274" alt="image" src="https://github.com/user-attachments/assets/b23e0450-9271-4961-8533-9d5b32211e3b" />
<img width="1558" height="914" alt="image" src="https://github.com/user-attachments/assets/63a42a12-cdd7-4a52-b3a2-760e51bba334" />
<img width="1450" height="960" alt="image" src="https://github.com/user-attachments/assets/6fa49fde-1f24-4688-8b9f-3b7073b6cb6a" />
<img width="1424" height="1226" alt="image" src="https://github.com/user-attachments/assets/dc1aca4b-0845-4427-9466-6afcb461438b" />


