# Building ADVi3++ from the Sources

**Note**: Work in progress.

## Introduction

The sources of **ADVi3++** are hosted on GitHub in two projects:

* [ADVi3pp-Marlin](https://github.com/andrivet/ADVi3pp-Marlin) for the Mainboard part
* [ADVi3pp-LCD](https://github.com/andrivet/ADVi3pp-LCD) for the LCD Touch Panel part

Here, we will only consider the Mainboard part, based on [Marlin Firmware](http://marlinfw.org).

There are several ways to build **ADVi3++** from the sources:

* Using [Visual Studio Code](https://code.visualstudio.com) ([PlatformIO IDE](https://platformio.org/platformio-ide)). **This is the recommended way**.
* Using [Jetbrains CLion](https://www.jetbrains.com/clion/) and [PlatformIO](http://docs.platformio.org/en/latest/ide/clion.html). This is what I am using the most
* Using [Atmel Studio 7](https://www.microchip.com/mplab/avr-support/atmel-studio-7) (based on Microsoft Visual Studio 2015)
* Using [Arduino IDE](https://www.arduino.cc/en/Main/Software). This what people are using the most often but **I recommend to avoid this solution**. **ADVi3++** may drop support for Arduino IDE in the future (more on this later)
* Using any other editor or IDE (Atom, Sublime, ...) and [PlatformIO Core](https://platformio.org)

The following chapters describe each solution.

## Download ADVi3++ Sources

![](https://cdn4.iconfinder.com/data/icons/iconsimple-logotypes/512/github-64.png)

The first step is to obtain the sources. They are hosted on GitHub. You have several way to do that:

* On the [GitHub page](https://github.com/andrivet/ADVi3pp-Marlin), choose **Clone or Download** and then the best option for you
* Use your local installation of **Git** to clone the project:

```
git clone https://github.com/andrivet/ADVi3pp-Marlin.git
```

* Fork the project in GitHub and then clone your fork locally. If you plan to made modifications and submit Push Requests, this is the way to go.

## Visual Studio Code / PlatformIO IDE

![](https://code.visualstudio.com/assets/home/home-screenshot-mac-lg-2x.png)

**Note**: **This is the recommended way to build ADVi3++**.

Visual Studio Code (not the same than Visual Studio) is a free, open-source and multi-platform IDE created by Microsoft. This is today one of the best free IDE with many extensions to support different languages, framework, etc. One of these extensions is PlatformIO IDE.

[The installation is simple](https://platformio.org/get-started/ide?install=vscode). You first install Visual Studio Code and then the `platformio-ide` extension.

Then follow these steps:

* Start Visual Studio Code
* Click on **PlatformIO Home** button on the bottom [PlatformIO Toolbar](http://docs.platformio.org/en/latest/ide/vscode.html#ide-vscode-toolbar)

![](http://docs.platformio.org/en/latest/_images/platformio-ide-vscode-welcome.png)

* Under **Quick Access**, click on **Open Project** (not **Import**)
* Navigate to the root of the **ADVi3pp-Marlin** project. This directory contains a file named **platformio.ini**. Click **Open [directory name]**.
* The project is loaded, parsed and the PlatformIO Toolbar turns blue.
* To build the project with default settings, click on the checkmark in the bottom PlatformIO toolbar

![](assets/platformio-build.png)

* The project is build and you see something similar to this:

```
[...]
AVR Memory Usage
----------------
Device: atmega2560

Program:  153632 bytes (58.6% Full)
(.text + .data + .bootloader)

Data:       5417 bytes (66.1% Full)
(.data + .bss + .noinit)


================= [SUCCESS] Took 7.30 seconds =================

========================== [SUMMARY] ==========================
Environment i3plus                      [SUCCESS]
Environment i3plus-bltouch              [SUCCESS]
Environment i3plus-debug                [SKIP]
Environment i3plus-bltouch-debug        [SKIP]
================= [SUCCESS] Took 14.11 seconds =================
```

* As you can see, by default, it builds the `i3plus` and `i3plus-bltouch` targets, i.e. the release version for the stock i3 Plus printer and the release version for the printer with a BLTouch sensor.
* To build other targets, click on the **Run Task...** icon

![](assets/platformio-task.png)

* Choose the appropriate task:

![](assets/platformio-tasks.png)

* Firmwares are built into the hidden `.pioenvs` folder in sub-folders with the names of the targets. The name of the firmware is always `firmware.elf` (binary executable) and `firmware.hex` (hexadecimal text form).

## Jetbrains CLion

![](assets/CLion.png)

[CLion](https://www.jetbrains.com/clion/) is a **commercial** IDE created by [Jetbrains](https://www.jetbrains.com). If you are already the owner of CLion or of Jetbrains suite of IDE, it is an interesting option, in particular if you are familiar with the other IDEs such as WebStorm (Javascript), IDEA (Java), PyCharm (Python), etc.

**TO WRITE**

## Atmel Studio 7

![](assets/AtmelStudio7.png)

[Atmel Studio 7](http://www.microchip.com/mplab/avr-support/atmel-studio-7) is a free, integrated development platform for developing and debugging all AVR&reg; and SAM microcontroller applications.

As far as I know, using Atmel Studio is the only way to use **hardware debuggers** such as [AVR Dragon](https://www.microchip.com/DevelopmentTools/ProductDetails/ATAVRDRAGON) or [Atmel-ICE](http://www.microchip.com/developmenttools/ProductDetails/atatmel-ice).

As Atmel Studio is not specific to Arduino development, it does not include **Arduino Core library** by default. You have to add it manually into **ADVi3++** project:

* From the [GitHub release page](https://github.com/andrivet/ADVi3pp-Marlin/releases), download **ArduinoCore-xxx.zip** (**xxx** is the version number, for example **ArduinoCore-3.0.2.zip**)
* Unzip the file somewhere (your Desktop, a temporary folder, etc.)
* Copy **ArduinoCore** into the root of the **ADVi3pp-Marlin** project (i.e. `ADVi3pp-Marlin` folder)

![](assets/ArduinoCore.png)

You can now open the project in **Atmel Studio**

* Start **Atmel Studio 7**
* Choose **Open Project...**
* Navigate to the root of the ADVi3pp-Marlin project. This directory contains a file named **ADVi3pp-Marlin.atsln**. Choose it and click **Open**
* Wait until the project is loaded

### Build a BLTouch release with Atmel Studio 7

* To build a **BLTouch** release, click on the **Solution Configurations** drop-down and choose **BLTouch-Release**

## Arduino IDE

![](assets/ArduinoIDE2.png)

Even if it is often the solution chosen by people, **I recommend to avoid it** for the following reasons:

* Is Arduino IDE still actively developed? It is not sure at all if you look at the history of releases and news on the blog. Maybe the plan is to replace it entirely by Arduino Create, the cloud version of Arduino IDE.
* The Arduino IDE is far behind alternatives such as Visual Studio Code regarding the IDE and the editor. 
* Even with the Beta 1.9, it is still not possible to put source code in subfolders. The toolchain does support subfolders but not the IDE. In other terms, it is possible to compile but not to edit.
* Arduino IDE is good to do some sketches, not to cope with relatively big project as Marlin and ADVi3++ are.
* With Arduino IDE, it is difficult to build for either the stock firmware or for BLTouch support. There is nothing to support multiple targets.
* Because of all these reasons, **I may drop in the near future the support of Arduino IDE**.

However, if you still want to use Arduino IDE, here are the steps:

* Open Arduino IDE (1.8.5 or higher)
* Select **File** / **Open** and browse to `Marlin.ino` inside the `Marlin` subfolder
* Select the right board under **Tools**:
  - **Board**: Arduino/Genuino Mega or Mega2560
  - **Processor**: ATmega2560 (Mega 2560)
* Click on the rounded checkmark to build the project or select **Verify/Compile** in the **Sketch** menu
* You can them **Upload** the firmware onto the printer (be sure to select the right port before under **Tools**)
* Or **Export compile binary**. It generates the following files (in the `Marlin` subdirectory):
    - `Marlin.ino.mega.hex`
    - `Marlin.ino.with_bootloader.mega.hex`

* Usually, you use the first file (`Marlin.ino.mega.hex`)

### Build a BLTouch release with Arduino IDE

By default, **ADVI3++** build a non-BLTouch release (i.e. a release for the stock printer). If you want to build a BLTouch release, I highly encourage you to use **PlatformIO** or **PlatformIO IDE**. However, I have recently modified the sources to ease the build with Arduino IDE:

* Open the file `advi3pp_defines.h`
* Uncomment the line with `#define ADVi3PP_BLTOUCH` (i.e. remove the two `//` and the space).
* Compile as explain above

## PlatformIO Core

PlatformIO is an open source ecosystem for IoT development, in particular Arduino development. PlatformIO Core is a heart of whole PlatformIO ecosystem. This a Command Line Tool that consists of multi-platform build system, platform and library managers and other integration components.

### Installation

The installation depends of your operating system. Please follow the [official instructions to install PlatformIO Core](http://docs.platformio.org/en/latest/installation.html).

### Building

Enter the following command to build the firmware (both with and without BLTouch support):

```
platformio run
```

The project is build and you see something similar to this:

```
[...]
AVR Memory Usage
----------------
Device: atmega2560

Program:  153632 bytes (58.6% Full)
(.text + .data + .bootloader)

Data:       5417 bytes (66.1% Full)
(.data + .bss + .noinit)


================= [SUCCESS] Took 7.30 seconds =================

========================== [SUMMARY] ==========================
Environment i3plus                      [SUCCESS]
Environment i3plus-bltouch              [SUCCESS]
Environment i3plus-debug                [SKIP]
Environment i3plus-bltouch-debug        [SKIP]
================= [SUCCESS] Took 14.11 seconds =================
```

As you can see, by default, it builds the `i3plus` and `i3plus-bltouch` targets, i.e. the release version for the stock i3 Plus printer and the release version for the printer with a BLTouch sensor.

Firmwares are built into the hidden `.pioenvs` folder in sub-folders with the names of the targets. The name of the firmware is always `firmware.elf` (binary executable) and `firmware.hex` (hexadecimal text form).



