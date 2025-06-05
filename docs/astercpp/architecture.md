# Project Architecture

Below is a brief overview of the directory layout used inside the
[AsterCPP](https://github.com/redpropulsion/AsterCPP/) repository.
It should help new contributors find the relevant components quickly.

```
AsterCPP/
├─ boards/        # configuration files and startup code for specific boards
├─ cmake/         # helper CMake scripts
├─ include/       # public header files
├─ src/           # C++ source code
├─ tests/         # unit tests and integration tests
└─ tools/         # additional scripts used during development
```

The `src` folder groups the source files by feature:

- `core/` – low level services and RTOS integration
- `drivers/` – peripherals such as sensors and communication interfaces
- `app/` – high level application logic

This structure allows the code to scale as new boards and features are added.
