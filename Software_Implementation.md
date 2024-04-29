# Software Implementation

*Figure 1. Software Block Diagram*
![image](https://github.com/Team-310/Team-310.github.io/assets/81040359/25ca7560-2dbe-4f5d-8c50-d3fe7ad4c897)

## Summary ##
The software block diagram comprehensively encompasses all the essential functions necessary for the design to work effectively. It also meets all the requirements outlined in the assignment. The software enables interrupts, manages, and gathers data from sensors, and controls the motor during data collection. This provides both visual and auditory stimuli to users, signaling that the weather station is operational. After data collection, the controller processes the data and transmits it to the ESP32, which then interfaces with the internet, allowing users to access the weather data on their phones.

## Decision-Making Process Based on Software Implementation ##
Our team knew what we wanted the product to do, but using the block diagram helped connect the pieces on how all the components would work together. It made writing the code easier and also highlighted areas where we needed to add features, like a button, and how to display data since we didn't have an LCD.

## Top 5 Biggest Changes and Issues to Our Software Design ##
**Physical Button/Switch Instead of Web-Browser Control:**
**Issue:** Initially, the design allowed for controlling the device exclusively via a web browser. However, during usability tests, we found that some users preferred a more tactile and immediate method to interact with the device, especially when their devices were not immediately accessible.
**Resolution:** We integrated a switch on the device. This change allows users to manually control the weather station, such as toggling it on or off, without needing to access the web interface. This was supported by adjustments in our UML diagrams to include hardware control interfaces in the system's operations.

**Refresh Times:**
**Issue:** The original software had longer intervals for data refresh, which led to delays in the weather data being updated, making the data less useful for users needing real-time information.
**Resolution:** We optimized the software to refresh weather data more frequently. This involved enhancing the performance of the data acquisition loop and ensuring that the system could handle more frequent updates without sacrificing battery life or processing power.

**Flower Displays Temperature in Spinning Direction:**
**Issue**: Previously, the device simply turned on to indicate operation, which did not provide users with immediate, useful information about the environment.
**Resolution:** We redesigned the feature so that the flower now displays the temperature using directional spinning. Warmer temperatures result in clockwise spinning, while cooler temperatures are indicated with counterclockwise spinning. This visual representation allows users to quickly assess temperature changes at a glance.

**Plotting Data on the ESP32:**
**Issue:** In the original design, the ESP32 was only used to transmit data to the internet without local processing or display capabilities.
**Resolution:** We updated the software to enable the ESP32 to plot temperature, humidity, and pressure data directly on a connected display. This allows for immediate visualization of the data at the site of the weather station, enhancing user interaction and making the data more accessible and understandable. The UML diagrams were updated to include the data plotting functionality within the ESP32's responsibilities.

**Increased Variety of Transmitted Variables:**
**Issue:** Initially, our system could only transmit one variable, which greatly limited the scope and utility of the weather data provided.
**Resolution:** We expanded the capability of the system to transmit multiple variables—specifically temperature, humidity, and pressure. This broader data collection provides a more comprehensive overview of weather conditions, enhancing the value and accuracy of the information provided to users.

## Version 2.0 Software Design Plan ##
For "Version 2.0" of our software design, we plan to introduce several functions and structures to enhance system performance and user experience. First, we'd create key functions such as **MotorControl** for managing PWM signals to control motor speed accurately, **BatteryStatus** to monitor and report on battery life, **DataBuffering** to manage data staging before its display or transmission, and **UserSettings** to handle interactions for system settings like refresh rates and power states.

To effectively manage our codebase, we'd organize our code into distinct layers: The hardware Layer would handle direct interactions with hardware components such as sensors, motors, and the battery. The Control Layer would implement the logic required for system controls, interfacing with the hardware layer to ensure smooth operation. This division would simplify maintenance and scalability.

To improve the debuggability of our software, we would implement comprehensive logging across all layers and integrate a simulation environment that mimics real-world operations for thorough pre-deployment testing.

Regarding peripherals and system features, incorporating advanced battery management systems and enhancing sensor interfaces would make our system more reliable and functional. We'd also look to robust communication protocols to ensure data integrity and security during transmission.

Finally, to simplify and improve our protocol design, we would update our communication standards to support more efficient data handling and error-checking mechanisms. This would reduce overhead and improve the responsiveness of our system, providing a seamless user experience and more reliable data collection and management. Furthermore, introducing simulation points in the UML diagrams to test different system responses or failures can greatly benefit the development process. This allows for the simulation of various scenarios from the diagrams themselves, enabling developers to predict and rectify potential system failures before actual deployment. These comprehensive enhancements to the UML diagrams are designed to ensure that every team member has a clear and detailed understanding of the system's modifications and their impacts, facilitating a more robust and user-centric software development cycle. These enhancements, when visually mapped in updated UML diagrams, would clearly outline the improved flow of data and control throughout the system, ensuring every team member has a clear understanding of the modifications and their impacts.


