# Getting Started with Renode

Introduction to Renode, a software development framework for embedded systems.

## About Renode

Renode is a tool for development of embedded systems. A strength of the tool is that is supports multi-node systems.

What Renode does is that it lets us build a model of an embedded system. The model is so close to a real-world system that it can run the same binary software that run on real hardware.

A use case for Renode is to start initial development of an embedded system on a general purpose computer without having access to the actual embedded hardware.

## Download

Renode can be downloaded for various platforms from the download section at [renode.io](https://renode.io/#downloads).

### Windows Installation

On a Windows machine you will download an installer file and the installation is started by just double clicking this file.

The installation process is more or less self-explanatory. I personally choose the option "Add to PATH" and left other options untouched.

Using the default options Renode ended up being placed at `C:\Program Files\Renode`.

### Getting Started

There is a Tutorials section at [renode.io](https://renode.io/tutorials/).

These tutorials are in current state a bit of a disappointment being only three brief videos without sound and very limited explanation whats going on. Anyway lets analyse the videos and try to figure out what is going on.

#### Video 1 - Basic functions

Video description:

> A video walkthrough on loading a sample platform - Silicon Lab's EFM32MG running a Zephyr shell application, displaying the list of peripherals, and logging capabilities.

EFR32MG is a SoC from the company Silicon Lab's and Zephyr is a RTOS for embedded systems.

Three console windows are shown on a computer screen at the start of the video:

1. Terminal - root@runner...
2. Terminal - Renode
3. Renode

A developer will first type, what seems to be a comment in the Renode Window:

```txt
(monitor) # run a very simple demo
```

Then follows entering of commands:

```txt
(monitor) set bin $CWD/efr32mg1p-zephyr-shell.elf
(monitor) i @scripts/single-node/efr32mg.resc
```

Assuming that the first commands sets the binary file to be run by Renode. The second command seems to run a script.

The commands causes output in the Terminal - Renode. There is multiple output but the summary is that the binary is loaded and the script is run as per the commands.

In the Renode window a yellow text appears:

```txt
(EFR32-MG)
```

After the yellow text the word `peripherals` then appears, unclear if this is typed in or shows up because it is part of the script.

Now also another fourth console window pops up, labelled EFR32-MG:sysbus.usart0. Name implies that this relates to serial communication of the EFR32-MG.

A tree view is displayed in the Renode window showing the available peripherals on the EFR32-MG. A selection of what is displayed is:

- bitband_peripherals
- bitband_sram
- cpu
- flash
- flashCtrl
- i2c0
- nvic
- usart0
