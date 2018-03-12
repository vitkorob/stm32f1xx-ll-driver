# STM32F1xx Low Layer Driver

This project contains only the Low-Layer APIs source code for STM32F1 microcontrollers.
For code base the author uses official the Low-Layer APIs code from package [STM32CubeF1][1].

## Why does this project exist?

The ST company actively promotes its product - hardware abstraction layer (HAL).
Author of this repository considers that the HAL is a bullshit. Only Low-Layer APIs
is true product for experts.

In official [package][1] the Low-Layer APIs was mixed with bullshit code of HAL.
In this repository the author singled out the quintessence of Low-Layer APIs source code.

## Additional enhancement

After singling out the Low-Layer APIs source code the author made some improvements that
don't change official code any way:

-   IAR project for building static library of Low-Layer APIs
-   new module for dynamically setting the interrupt handler (the vector table has been copied to the RAM sector)

## Low-Layer APIs for other series

Author made repositories for other series:

-   [STM32L0 series][2]

[1]:  //www.st.com/content/st_com/en/products/embedded-software/mcus-embedded-software/stm32-embedded-software/stm32cube-mcu-packages/stm32cubef1.html   "STM32CubeF1"
[2]:  //github.com/vitkorob/stm32l0xx-ll-driver/
