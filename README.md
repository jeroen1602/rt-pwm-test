# PWM square wave

This is a project for testing if the Raspberry pi with a real time kernel will be influenced by high CPU usage. 

This project uses git submodules, so make sure to initialize it `git submodule update --init --recursive`.

## Building

This project uses `cmake` as a build system.

Libraries used:
 - `libgpiod` / `libgpiod2`
 
 To build first create a build directory
 ```bash
mkdir build 
```
And cd into it
```bash
cd build
```

now initialize the project using cmake

```bash
cmake ../
```

And finally build the project. You can make both the executables by calling `make` or just one by changing the build target.
Use `make pwm` or `make cpuburn-a7` to build only one of the executables.

## PWM

The `pwm` executable is for creating a simple square wave on `pin 18` of the Raspberry pi gpio port. The `pwm` 
executable uses a commandline argument for the frequency (in hz). To change any other settings you will need to change 
 the defines in the `pwm.cpp` file.

 - Change the `OUTPUT_PIN` define to change the output pin.
 
Don't forget to rebuild the executable after changing the defines.


## cpuburn-a7

`cpuburn-a7` is a program downloaded form [github](https://github.com/ssvb/cpuburn-arm). It is used to stress test the 
cpu of the Raspberry pi to simulate a high load. It simulates a 100% CPU load on all available cores, so make sure the 
PI has enough cooling.

If you are running the program on a more modern CPU or with a more modern kernel you may need to edit the `CMakeList.txt` 
file to compile the correct version of the `cpuburn`test. 

If this is done then make sure to update the cmake instance. CD into the build folder `cd build` and `cmake ../`.

 
