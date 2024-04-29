# [Team Schematic](file:///C:/Users/aweso/Downloads/Hardware_Implementation_V2.pdf)  
[![FINAL_Schematic](https://github.com/Team-310/Team-310.github.io/assets/157059404/03df1ba4-872b-4ea6-91bf-7790a73babd7)](file:///C:/Users/aweso/Downloads/Hardware_Implementation_V2.pdf)

Team 310 chose this circuit design because it was the cleanest version that could meet all our user needs as well as the project requirements. The temperature and pressure sensor satisfy the product requirements while also giving the user crucial weather information. The motor subsystem provides a visual indication that the device is active and gathering data. By spinning the flower, it adds an aesthetically pleasing aspect to our product to fulfill user needs. The ESP32 allows the user to receive the temperature and pressure data via WIFI, meeting the project requirements and adding an extra feature well liked by the user. The microcontroller controls all the subsystems for smooth operation and WIFI control that anyone can use. Overall, the product is designed to exceed user expectations by providing data about the weather and acting as aesthetically pleasing home decor.

## Version 2.0
If the team were able to to make a version 2 of this design, there would be a few things we would want to improve. First, we would include traces from the motor driver to the MSSP1 pins on the microcontroller while still having header pins for easy access/debugging pruposes. We would also include power traces for the 3.3V and the 9V directly to the motor driver. Due to the fact that the temperature and humidity sensors are "floating" from the rest of the board, we would include a row of header pins directly connected to 3.3V as well as a row of header pins connected to ground. An addition of 3 extra LEDs would be implemented on the unused microcontroller GPIO pins for software and hardware debugging. While there was 1 on board LED for debugging, the team had to jumper wire another LED to use for debugging the second analog sensor when implementing all subsystems into one project. 

[Refer to Bill of Materials in Appendix](Appendix.md)  

# Team PCB  
### Front  
![Front_PCB](https://github.com/Team-310/Team-310.github.io/assets/157059404/1a353fbe-5c22-4cc2-ad1c-f270f0cff043)  
### Back  
![BACK_Pcb](https://github.com/Team-310/Team-310.github.io/assets/157059404/0d64bbe5-73be-490c-8d57-07318451bece)  
### Front
![PCB_FRONT](https://github.com/Team-310/Team-310.github.io/assets/157059404/9374cf41-cafe-455a-8965-1a99d46e6b49)  
### Back  
![PCB_BACK](https://github.com/Team-310/Team-310.github.io/assets/157059404/f2522715-a8d4-4d52-9edf-f5b7bf4d4498)  

