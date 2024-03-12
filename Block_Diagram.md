# Block Diagram

![image](https://github.com/Team-310/Team-310.github.io/assets/156128630/bb6c6d62-de24-46da-ba08-8840d45402f9)

## **Sensors (Pressure and Temperature)**
* **Subsystem Responsibility:** These sensors are responsible for gathering environmental data and sending the data to the Microcontroller. The BME280 is the sensor for the atmospheric pressure, and the temperature sensor is the SHT40-AD1B-R2
* **Contribution to the project:** These sensors provide the raw data necessary to monitor environmental conditions. The data collected will be used to inform users of weather conditions near them when they our Mobile Weather Station App.

## **Microcontroller**
* **Subsystem Responsibility:** The microcontroller serves as the central processing unit for the sensor data. It reads data from both sensors, processes it (if necessary), and sends it to the ESP-32. It will also gather responses from the ESP-32 to alert the motor sensor to turn the motor on.
* **Contribution to the Project:** It acts as the brain of the operation, interpreting sensor data and controlling other components based on thresholds and predefined logic.

## **Motor**
* **Subsystem Responsibility:** The motor is used as a form of mechanical action, it will spin the flower when the system is reading data.
* **Contribution to the Project:** Provides the physical response as well as gives the user a visual aspect to know when data is being read based on the microcontroller's commands.

## **ESP-32 Module**
* **System Responsibility:** The ESP-32 connects to a web server and uploads the data it receives from the microcontroller. This involves real-time data streaming when the user requests data.
* **Contribution to the Project:** Enables remote monitoring and control capabilities. Providing the user data and sending data to the Microcontroller from the user inputs.

## **Integration** 
The microcontroller receives a command from the ESP-32 to start the program then it reads and processes data from the sensors, controls the motor, and then communicates with the ESP32 to upload the information to a web server. This setup integrates sensing, processing, actuating, and communication functions into a cohesive system.

## **Achievement of Project Requirements** 
This integrated system meets requirements for environmental monitoring and control, with the added capability of remote data access and potentially remote control. This stuctures uses the strengths of each component to achieve an efficient system for our Flora Forecast.
