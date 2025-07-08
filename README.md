# STM32 Blinky - HAL Approach

This project demonstrates a simple LED blinky application for the STM32F446RE Nucleo board using STM32 HAL (Hardware Abstraction Layer) functions.

## Overview

This is part of a series where I implement the same functionality using two different approaches:
1. **HAL Functions** (this repository) - Using STM32's high-level abstraction layer
2. **Memory Mapping** (separate repository) - Direct register manipulation for deeper hardware understanding

## Hardware

- **Board**: STM32F446RE Nucleo
- **LED**: Built-in user LED (typically connected to PA5)

## Approach

This implementation uses STM32 HAL functions which provide:
- High-level abstraction over hardware registers
- Easier and faster development
- Built-in error handling and safety checks
- Portability across different STM32 families

### Key HAL Functions Used
- `HAL_GPIO_TogglePin()` - To toggle LED state
- `HAL_Delay()` - For timing delays
- `HAL_GPIO_Init()` - GPIO initialization

## Project Structure

```
├── Core/
│   ├── Inc/           # Header files
│   │   ├── main.h
│   │   ├── stm32f4xx_hal_conf.h
│   │   └── stm32f4xx_it.h
│   ├── Src/           # Source files
│   │   ├── main.c     # Main application logic
│   │   ├── stm32f4xx_hal_msp.c
│   │   └── stm32f4xx_it.c
│   └── Startup/       # Startup files
├── Drivers/           # STM32 HAL drivers
└── *.ioc             # STM32CubeMX configuration
```

## HAL-Level Implementation

This project uses HAL functions that abstract:
- **HAL_GPIO_TogglePin()**: High-level GPIO control
- **HAL_Delay()**: System tick-based delay
- **HAL_GPIO_Init()**: Automated GPIO configuration
- **HAL_Init()**: System initialization

## Learning Objectives

- Understanding STM32 HAL layer
- GPIO control using high-level functions
- Project structure in STM32CubeIDE
- Comparison with low-level register manipulation

## Demo

Demo Video Link: https://youtu.be/-b5W9rJqOqQ

## Comparison

For a deeper understanding of how the same functionality is implemented using direct register manipulation, check out the companion repository: [STM32-Blinky-MemoryMap](https://github.com/Ama-Andam/STM32-Blinky-MemoryMap)

This HAL approach provides ease of use while the memory mapping approach helps understand what happens "under the hood" when using HAL functions.
