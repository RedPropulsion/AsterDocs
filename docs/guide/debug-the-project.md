# Debug RedAster in CLion

Follow the next steps to debug the project with CLion.

### Requirements:

* __Open OCD__:
  First of all you have to have installed Open OCD (Open On-Chip Debugger), an open-source utility to debug microcontrollers.
  It can be installed through a package manager:

  macOS:
   ```
   brew install open-ocd
   ```
  Linux:
   ```
   sudo apt-get install openocd
   ```
  Windows:
   ```
   choco install openocd
   ```
* __GDB__:
  Make sure to have installed GDB (GNU Debugger). It can be installed through a package manager:

  macOS:
   ```
   brew install gdb
   ```
  Linux:
   ```
   sudo apt-get install gdb
   ```
  Windows:
  Follow the instructions on this page: [MinGW System](https://sourceforge.net/projects/mingw/files/MinGW/).

### Create the CLion Configuration:
Follow the next steps to debug your code inside CLion:

1. Go in the settings and set the Embedded Development specifications.
2. Create a new configuration for your build. Make sure is an "OpenOCD Download & Run" type of configuration.

   <p align="center">
       <img width = "700" src="/assets/EmbeddedDevConfig.png" alt="EmbeddedDevConfig" style="margin-top:20px; margin-bottom:20px;">
   </p>

3. Now fill the settings with as "Target and Executable binary" the RedAster.elf . Then as "Board config file" specify
   the path of the "custom_st_nucleo_h723ZG.cfg" present in the repo.

   <p align="center">
       <img width = "700" src="/assets/CLionConfig.png" alt="CLionConfig" style="margin-top:20px; margin-bottom:20px;">
   </p>