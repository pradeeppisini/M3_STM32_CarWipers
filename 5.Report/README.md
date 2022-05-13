# OBJECTIVE OF THIS PROJECT:
By using STM32F407,buttons,4 LED's the project should be done using the timers and the sequence of glowing of LED's RED,GREEN,BLUE and the 4th acc mode either ON or OFF mode.If we press for a long time car should start or stop and by clicking the buttons the wipers speed mode should change.
# INTRODUCTION:

* we use the STM32F4xx-discovery board to illustrate an automobile wiper control system. Most automobile wipers are controlled by a DC motor, however because the STM32F4xx-discovery lacks a motor, we are exploring using LEDs in this application. As an example, the wiper control system. The STM32F4xx-discovery board has four LEDs and a Push Button. The colours of these LEDs are orange, green, red, and blue. A current limiting resistor connects four user LEDs to the PD12, PD13, PD14, and PD15 pins of PORTD on the Discovery board. To make a push button work with the STM32F407VG microcontroller, the GPIO pins will be set as digital input pins. If you push and hold the user button for two seconds, the Red When the ignition key is positioned at the ACC, the LED illuminates. Furthermore, the LEDs are flickering, indicating that the wipers are turned on.

#   COMPONENTS AND SUPPLIES:

1. STM32F407 Discovery Board
2. Push Button
3. LED's
4. Resistors
5. Power Supply

# ADVANTAGES:

* It is quite easy to use.
* Rain sensor-based systems are extremely simple to install.
* Individual rain sensors are fairly inexpensive.
* As a consequence, less energy is consumed.
* As a consequence, rain sensor-based equipment like vehicle wipers and irrigation systems last longer since they only work when needed.
* To save money during wet seasons, turn off the irrigation system. Electricity bills are lowered as a consequence.
* Rain sensors store water during rain events, allowing it to be available throughout the summer and winter.
# DISADVANTAGES:

* The entire system cost rises when more components, including a rain sensor, are required.
* Rain sensors must make a decision within a few minutes to avoid erroneous detection of rain.
* When water falls squarely on the rain sensor, the mechanism activates.

# Exploring STM32F407 Discovery Board:
![image](https://user-images.githubusercontent.com/101619680/168203100-e55036da-1f5a-4c49-87a2-d76c028bbb45.png)

This project gives almost all the basic information needed to get started with STM32F407 Discovery Board and also development of driver code.

* Software Tool : STM32cubeIDE, for more information visit: STM32CubeIDE
* Hardware Used : STM32F4 DISCOVERY kit, for more information visit: STM32F4 DISCOVERY
* For installation of STM32CubeIDE refer Youtube
* Note : As this microcontroller has many advanced features and the main aim of this project is to get all basic insights, during the driver development only the required functionalities are added and other advanced functionality is not added. I may update the driver and other functionality in the future.

Please find the STM32F4 Discovery User Manual,STM32F4xxx Reference Manual (RM0090) and other related documents inside a folder called Documents. I will be referring to these documents for information such as block diagrams, register details ect.

# Overview of STM32F407VGT6 Microcontroller:
![image](https://user-images.githubusercontent.com/101619680/168203141-05752152-e61b-4bd8-b57f-ebbef66327ad.png)

The STM32F407 Discovery board uses STM32F407VGT6 Microcontroller which has ARM Cortex-M4F Processor, which is capable of running upto 168Mhz. This MCU has many peripherals such as GPIO ports, TIMERS, ADCs, DACs, Flash Memory, SRAM, SPI, UART ect. The processor and peripherals talk via BUS-Interface. There are three busses available

I-BUS (Instruction Bus) D-BUS (Data Bus) S-BUS (System Bus) I-BUS This bus connects the Instruction bus of the Cortex®-M4 with FPU(Floating point unit) core to the BusMatrix. This bus is used by the core to fetch instructions. The target of this bus is a memory containing code (internal Flash memory/SRAM or external memories through the FSMC/FMC).

D-BUS This bus connects the databus of the Cortex®-M4 with FPU to the 64-Kbyte CCM data RAM to the BusMatrix. This bus is used by the core for literal load and debug access. The target of this bus is a memory containing code or data (internal Flash memory or external memories through the FSMC/FMC).

S-BUS This bus connects the system bus of the Cortex®-M4 with FPU core to a BusMatrix. This bus is used to access data located in a peripheral or in SRAM. Instructions may also be fetched on this bus (less efficient than ICode). The targets of this bus are the internal SRAM1, SRAM2 and SRAM3, the AHB1 peripherals including the APB peripherals, the AHB2 peripherals and the external memories through the FSMC/FMC.

So instructions and data use I-bus and D-bus respectively, All the other peripheral uses System bus. The Cortex-M4 processor contains three external Advanced High-performance Bus (AHB)-Lite bus interface and one Advanced Peripheral Bus (APB) interface. The GPIOs are connected to AHB1 bus which has a maximum speed of 150Mhz and is divided into two buses as APB1 and APB2. APB1 runs at 42Mhz(max) and APB2 runs at 82Mhz(max). The different peripherals such as SPI, UART, TIMERs, ADCs, DACs, etc are connected to either APB1/APB2 buses. And the AHB2(168Mhz max) is connected to Camera and USB OTG interfaces, AHB3 is connected to External memory controller.

