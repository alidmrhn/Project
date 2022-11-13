Q1) Let's assume that a few of the peripherals you use have the same hardcoded I2C address. 
What solution would you use to solve this problem?


A1) I can use another communication protocol. If I don't have such a chance, 
I would examine the device's datasheet to see if the I2C address can be changed. 
Assuming it can't be changed, I would work on integrating the I2C channel multiplexer into the system.


Q2) Let's say you want about 30 hardware modules to communicate with each other. There is one STM32
microcontroller on each module, and the modules can be removed and installed instantly.
Which communication standard would you use for these modules to communicate effectively with each other? Why?


A2) If we consider the I2C communication protocol, we will have to use devices with different I2C addresses.
This creates 30 different stm32 variants. If we use the solutions as we answered in the 1st question,
we will have to deal with 30 modules separately. We will need to make 2 extra connections in the SPI 
communication protocol.In addition, we can create only 1 master in the SPI protocol. It is not possible
to communicate between slaves.In this case, I would prefer the CAN protocol. The CAN protocol is a fast
and reliable method. They do not have problems such as many connections like spi and addresses like i2c.
As another method, I could also consider wirelessly communicating the system by integrating a wifi
module into each module.


Q3) What are the main features of Real-Time Operating Systems and how do they differ from regular OS’s?


A3) In Rtos, time limits are clearly stated and the system is strictly followed.
It focuses on a single application and tasks are queued according to their importance. 
In this way, important tasks are completed on time. The differences between them; 
Regular OS tries to do all the processes or tasks at the same time. It doesn't prioritize like Rtos.
Rtos makes the most of memory resource, but general os does not. Rtos general usage area is embedded systems.
The usage area of regular OS is computer, server etc.
