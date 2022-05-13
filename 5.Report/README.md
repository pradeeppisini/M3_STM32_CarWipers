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


# STM32F407VG
* The STM32F407 Kit exploits the elite exhibition STM32F407 microcontrollers capacities to mak eit straightforward for clients to make sound based application. It accompanies a ST-LINK inserted troubleshoot instrument, a ST-MEMS computerized accelerometer, an advanced mouthpiece, a sound DAC with coordinated class D speaker driver, LEDs, pushbuttons and USB OTG miniature AB connector. Ethernet network, a LCD Display and different elements have been added ti the STM32F4 DISCOVERY unit. the STM32F405xx and STM32F407xx families are worked around the elite execution Arm cortex - M4 bit RISC center, which runs at up to 168 MHz.

# FEATURES OF STM32F407VG MICROCONTROLLER

* Up to 1 Mbyte of flash memory
* Up to 192+4 Kbytes of SRAM including 64-Kbytes of CCM (Core Coupled Memory) data RAM.
* 512 bytes of OTP memory.
* Flexible static memory controller supporting Compact flash SRAM, PSRAM, NOR and NAND memories

# WORKING PRINCIPLE:
* Accept that the autos is the microcontroller. Assuming that the button is hit, the primary drove (red) will turn on, clicking again the wiper will begin and the subsequent drove (blue) will turn in for an ideal rate. In the event that the button os squeezed once more, the third driven (green) will turn on, and the wiper's speed will be expanded in contrast with the past one. The fourth press will turn on the fourth driven (orange), and the wiper speed will be expanded as per the past one. the microcontroller (vehicle) is switched off after the fifth snap.
# 4W & H (WHO,WHAT,WHEN,WHERE,HOW):
* Accept that the car is the microcontroller. Assuming the button is hit, the main drove (red) will turn on, Clicking again the wiper will begin, and the subsequent drove (blue) will turn on for an ideal rate. On the off chance that the button is squeezed once more, the third driven (green) will turn on, and the wiper's speed will be expanded in contrast with the past one. The fourth press will turn on the fourth driven (orange), and the wiper speed will be expanded as per the past one. The microcontroller (vehicle) is switched off after the fifth snap.

# Utilizes:
# WHAT:
* The operational speed of a vehicle wiper is controlled by a wiper speed control mechanism based on rain conditions. To generate, the control system incorporates a rain sensor (30) that detects rain conditions. The amplitude of an analogue signal depends on the detected rain conditions.
# WHY:
* To keep the windscreen clean enough to give adequate view at all times. #WHEN The windshield wipers remove rain and snow from the windshield, while the headlights improve visibility at night.
# WHO:
* Mark Anderson invented on 1902
# STRENGTH:
* Low Budget
* Decrease the accidental situation
* High Bargaining Power Supliers
* Increase safety

# WEAKNESS:
* High maintenance.
* High Transaction Cost
* Limited speed
* Week Focus on Process Innovations
* Can be frustrating at low penetration rates.

# OPPORTUNITIES:
* Emerging New Markets
* Technological Development
* Demand for Saver Equipments
* Technological Lock in of Product
* Enables novel MTM application.

# THREATS:
* Low Bargaining Power Buyers
* Highly REgulated Industry
* Ethical Pressure
* Econimical Crisis
* MTM delayed adapation.

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

# OUTPUT IAMGES:

1.User button and hold it for two seconds
![image](https://user-images.githubusercontent.com/101619680/168224813-7ec4c324-0edb-4739-8b97-56e58d5c32f4.png)

2.wiper speed low
![image](https://user-images.githubusercontent.com/101619680/168224879-3335c168-8832-44e5-b8ab-d0f303b04717.png)

3.Wiper speed medium
![image](https://user-images.githubusercontent.com/101619680/168224922-79a29e14-de2d-4833-914d-83cde08417cc.png)

4.Wiper speed is high
![image](https://user-images.githubusercontent.com/101619680/168224983-84015987-0816-49be-8363-b5eace5a631e.png)

5.User button is pressed and held for 2 seconds, the red LEDis off
![image](https://user-images.githubusercontent.com/101619680/168225087-663c9e67-3e33-4e46-87d6-13acc9919781.png)
