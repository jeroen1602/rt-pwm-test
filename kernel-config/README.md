# Kernel config

In this folder are the 2 kernel build configs used for building the kernel, with and without the kernel patch.
Using the offical build guide [https://www.raspberrypi.org/documentation/linux/kernel/building.md](https://www.raspberrypi.org/documentation/linux/kernel/building.md). And the RT patch [https://cdn.kernel.org/pub/linux/kernel/projects/rt/](https://cdn.kernel.org/pub/linux/kernel/projects/rt/). 

This project uses the 5.9.x kernel, which was the latest at the time.

After the `make ARCH=arm CROSS_COMPILE=arm-linux-gnueabihf- bcm2709_defconfig` step just copy in the correct config 
file and rename it to .config. Then follow the rest of the cross-compile steps.