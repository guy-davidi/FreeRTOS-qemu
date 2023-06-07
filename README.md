# FreeRTOS QEMU Demo

This guide explains how to run the FreeRTOS demo on top of the QEMU emulator.

## Prerequisites

- Linux machine (tested on Ubuntu 20.04)
- Git installed
- ARM toolchain (gcc-arm-none-eabi) installed
- QEMU emulator installed

## Installation

1. Clone the FreeRTOS Kernel repository:
```
git clone https://github.com/FreeRTOS/FreeRTOS-Kernel.git
```

2. Navigate to the FreeRTOS demo directory:
```
cd FreeRTOS-Kernel/FreeRTOS/Demo/CORTEX_M3_MPS2_QEMU_GCC
```

3. Build the demo application:
```
make
```
4. Install the ARM toolchain:
```
sudo apt update
sudo apt install gcc-arm-none-eabi
```
5. Verify the installation of the ARM toolchain:
```
arm-none-eabi-gcc --version
```

6. Initialize and update Git submodules (if needed):
```
git submodule update --init --recursive
git submodule sync --recursive
```

## Run FreeRTOS Demo in QEMU

7. Start the FreeRTOS demo in QEMU:
```
qemu-system-arm -M mps2-an385 -kernel build/RTOSDemo.axf -serial stdio
```

The demo application should start running in QEMU, and you should see the output on the console.

Note: The `-serial stdio` option redirects the serial output of the QEMU emulator to the console.

8. Observe the FreeRTOS Demo:

The demo application typically demonstrates some functionality like blinking LEDs, task scheduling, or other features specific to the chosen demo. You can observe the behavior of the demo as it runs in QEMU.

9. Exit QEMU:

To exit QEMU, press `Ctrl + A` followed by `x`.

Alternatively, you can close the terminal window running QEMU.

## Additional Notes

- If you encounter any issues or errors during the setup or execution of the demo,
please refer to the official FreeRTOS documentation or the specific demo documentation for troubleshooting and further information.

- Make sure you have the necessary permissions to run QEMU with the appropriate privileges (e.g., using `sudo` if required).

- This guide assumes a Linux environment, specifically Ubuntu 20.04. The steps and commands may differ for other operating systems.

- QEMU offers a wide range of options and configurations. You can explore the QEMU documentation for more advanced usage and customization options.
