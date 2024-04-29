# Appendix
### Team Organization
*Table 1. Communication Preferences*


| Name            | 1st Choice Communication | 2nd Choice Communication | 3rd Choice Communication |
|-----------------|--------------------------|--------------------------|--------------------------|
| Julia P.        | Text                     | Discord                  | Email                    |
| Angie V.        | Text                     | Discord                  | Email                    |
| Margaret L.     | Text                     | Discord                  | Email                    |
| Elliott G.      | Text                     | Discord                  | Email                    |

*Figure 1. Meeting Schedule*
![image](https://github.com/Team-310/Team-310.github.io/assets/156128630/49d06e23-cd85-4ca5-8800-20339e80db1b)

*Table 2. Project Roles and Duties*


| Name            | Role            | Duties  |
|-----------------|-----------------|---------|
| Julia Providell | Meeting Leader  | Schedules team meetings, creates and distributes an agenda for each meeting, and runs each meeting |
| Angie Valencia  | Assignment Leader | Coordinates the team's work on a given assignment to Canvas before the due date|
| Margaret Linde  | Meeting Recorder | Takes minutes of each team meeting, including attendance, and records action items and to whom they are assigned |
| Elliott Gillespie | Project Monitor | Tracks the team's progress relative to the project schedule (Gantt chart) and keeps team members apprised of deadlines and project status |


### User Needs
*Figure 2. User Needs on Jamboard (Unorganized, Unranked, Uncombined)*  
![user needs yellow](https://github.com/Team-310/Team-310.github.io/assets/157058267/156edaf9-3b0e-4e22-851b-7c7b9b0d2921)  

*Figure 3. Categorized User Needs*
![user needs 2](https://github.com/Team-310/Team-310.github.io/assets/157058267/7391d182-8a62-4562-b35b-8d20787b10ee)  

*Figure 4. Ranked User Needs in Categories*
![un 3](https://github.com/Team-310/Team-310.github.io/assets/157058267/5367b766-9f8a-4106-9bfb-5b95a280518d)  

*Figure 5. Ranked User Needs in Catgories from 3 to 1 stars*
![un 3](https://github.com/Team-310/Team-310.github.io/assets/157058267/eb51f35f-d932-493a-a5b3-9a8a66454e85)


*Figure 6. User Needs in an Ordered List*
![image](https://github.com/Team-310/Team-310.github.io/assets/157058267/863c03bc-a4cf-4b98-9eb3-f19aaac9729b)  


### Design Ideation
*Figure 7. Brainstorming Ideas on Jamboard*
![image](https://github.com/Team-310/Team-310.github.io/assets/157058267/3acb941f-1801-4a76-9f12-065ac1d75c18)  
*Figure 8. Design Concepts Categorized into 3 Categories*
![image](https://github.com/Team-310/Team-310.github.io/assets/157058267/f362140b-ba65-4762-80d7-e9a5df01ef8f)  

## [Bill of Materials](https://docs.google.com/spreadsheets/d/1FA7_zZz8KkpmYs1YQsXKBv4hid6KEE90/edit?usp=sharing&ouid=106828450620415480012&rtpof=true&sd=true)  
![BOM](https://github.com/Team-310/Team-310.github.io/assets/157059404/319b0432-979a-4232-be70-d8406ffab253)

## Motor - [LS-00028](https://www.digikey.com/en/products/detail/osepp-electronics-ltd/LS-00028/11198652)  
![Motor](https://github.com/Team-310/Team-310.github.io/assets/157059404/938f106a-640f-4d7f-b0f9-9414d8ad850c)  
Our team chose this motor because of its small size and voltage requirement. Since the motor will not need to move heavy parts, only light plastic pieces, it is ideal for our project. It also has a simple design, so it will be easy to implement it.

## Power Supply - 9V Battery  
![Battery](https://github.com/Team-310/Team-310.github.io/assets/157059404/c82bdb55-c936-455e-97de-ff75d56ad892)  
Our team chose this 9V battery to power the Flora Forecast because they are readily available. The user can easily replace the battery too. The 9V battery supplies enough power for up to 2 hours of constant use of our device.  

## Webserver Screen Shot from Innovation Show Case ##
*Figure 9. ESP32 Website Data*
[FinalESP32WebsiteData.pdf](https://github.com/Team-310/Team-310.github.io/files/15151820/FinalESP32WebsiteData.pdf)

## ESP32 Code ##
#include <WiFi.h>
#include <AsyncTCP.h>
#include <ESPAsyncWebServer.h>

const char* ssid = "Maggies iPhone 15 Pro Max";  // Your WiFi SSID
const char* password = "Mhlinde830";  // Your WiFi password

AsyncWebServer server(80);

// Global variables to store sensor data
String temperature = "N/A";
String humidity = "N/A";
String pressure = "N/A";

// Function to parse data received from UART
void parseData(String data) {
    int tempIndex = data.indexOf("T:") + 2;
    int humIndex = data.indexOf("H:") + 2;
    int presIndex = data.indexOf("P:") + 2;

    temperature = data.substring(tempIndex, data.indexOf(" ", tempIndex));
    humidity = data.substring(humIndex, data.indexOf(" ", humIndex));
    pressure = data.substring(presIndex, data.length());

    Serial.print("Parsed Temperature: "); Serial.println(temperature);
    Serial.print("Parsed Humidity: "); Serial.println(humidity);
    Serial.print("Parsed Pressure: "); Serial.println(pressure);
}
const char* index_html = 
"<!DOCTYPE HTML><html>\n"
"<head>\n"
"  <meta name='viewport' content='width=device-width, initial-scale=1'>\n"
"  <meta charset='UTF-8'>\n"
"  <script src='https://cdn.jsdelivr.net/npm/chart.js'></script>\n"
"  <style>\n"
"    body { background-color: #FFD1DC; display: flex; align-items: flex-start; }\n"
"    #leftPanel { width: 50%; padding: 10px; box-sizing: border-box; }\n"
"    #rightPanel { width: 50%; }\n"
"    canvas { max-width: 100%; height: auto !important; }\n"
"    .sensorValue { font-size: 1.5em; }\n"
"    .sensorLabel { font-weight: bold; }\n"
"  </style>\n"
"</head>\n"
"<body>\n"
"<div id='leftPanel'>\n"
"  <img src='data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAArUAAAK2CAIAAADfVvO4AAAgAElEQVR4Aey9Z3RbR5Y/ON/3036Y3f/+J/X0dprunp7ZObtnt6dn...' alt='Flora Forecast' style='width: 100px; height: auto;'>\n"
"  <h1>ESP32 Sensor Server</h1>\n"
"  <p class='sensorValue'>Current Temperature: <span id='displayTemp'></span>°C</p>\n"
"  <p class='sensorValue'>Current Humidity: <span id='displayHum'></span>%</p>\n"
"  <p class='sensorValue'>Current Pressure: <span id='displayPress'></span> hPa</p>\n"
"</div>\n"
"<div id='rightPanel'>\n"
"  <canvas id='tempChart'></canvas>\n"
"  <canvas id='humChart'></canvas>\n"
"  <canvas id='pressChart'></canvas>\n"
"</div>\n"
"  <script>\n"
"    const ctxTemp = document.getElementById('tempChart').getContext('2d');\n"
"    const ctxHum = document.getElementById('humChart').getContext('2d');\n"
"    const ctxPress = document.getElementById('pressChart').getContext('2d');\n"
"    const tempChart = new Chart(ctxTemp, {\n"
"      type: 'line',\n"
"      data: { labels: [], datasets: [{ label: 'Temperature (°C)', data: [], borderColor: 'red', fill: false }] },\n"
"      options: { scales: { y: { beginAtZero: true } } }\n"
"    });\n"
"    const humChart = new Chart(ctxHum, {\n"
"      type: 'line',\n"
"      data: { labels: [], datasets: [{ label: 'Humidity (%)', data: [], borderColor: 'blue', fill: false }] },\n"
"      options: { scales: { y: { beginAtZero: true } } }\n"
"    });\n"
"    const pressChart = new Chart(ctxPress, {\n"
"      type: 'line',\n"
"      data: { labels: [], datasets: [{ label: 'Pressure (hPa)', data: [], borderColor: 'green', fill: false }] },\n"
"      options: { scales: { y: { beginAtZero: true } } }\n"
"    });\n"
"    function fetchData() {\n"
"      fetch('/data')\n"
"        .then(response => response.json())\n"
"        .then(data => {\n"
"          const now = new Date();\n"
"          const hours = now.getHours() % 12 || 12;\n"
"          const minutes = now.getMinutes().toString().padStart(2, '0');\n"
"          const label = hours + ':' + minutes + ' ' + (now.getHours() >= 12 ? 'PM' : 'AM');\n"
"          document.getElementById('displayTemp').textContent = data.temperature;\n"
"          document.getElementById('displayHum').textContent = data.humidity;\n"
"          document.getElementById('displayPress').textContent = data.pressure;\n"
"          tempChart.data.labels.push(label);\n"
"          tempChart.data.datasets[0].data.push(data.temperature);\n"
"          tempChart.update();\n"
"          humChart.data.labels.push(label);\n"
"          humChart.data.datasets[0].data.push(data.humidity);\n"
"          humChart.update();\n"
"          pressChart.data.labels.push(label);\n"
"          pressChart.data.datasets[0].data.push(data.pressure);\n"
"          pressChart.update();\n"
"        })\n"
"        .catch(error => console.error('Error fetching data:', error));\n"
"    }\n"
"    setInterval(fetchData, 1000); // Update every second\n"
"  </script>\n"
"</body>\n"
"</html>\n";

void setup() {
  Serial.begin(115200);
  Serial2.begin(9600, SERIAL_8N1, 16, 17); // Configure UART2

  WiFi.begin(ssid, password);
  while (WiFi.status() != WL_CONNECTED) {
    delay(1000);
    Serial.println("Connecting to WiFi...");
  }

  Serial.println("Connected to WiFi");
  Serial.print("IP Address: ");
  Serial.println(WiFi.localIP());

  server.on("/", HTTP_GET, [](AsyncWebServerRequest *request) {
    request->send_P(200, "text/html", index_html, NULL);
  });

  server.on("/data", HTTP_GET, [](AsyncWebServerRequest *request) {
    String data = "{\"temperature\":\"" + temperature + "\",\"humidity\":\"" + humidity + "\",\"pressure\":\"" + pressure + "\"}";
    request->send(200, "application/json", data);
  });

  server.begin();
}

void loop() {
  if (Serial2.available()) {
    String data = Serial2.readStringUntil('\n');
    Serial.print("Received data: "); Serial.println(data); // Debug received data
    parseData(data);
  }
}

## MCC Configuration Screen Shots ##
*Figure 10. MCC Configuration Pin-Out*
<img width="946" alt="image" src="https://github.com/Team-310/Team-310.github.io/assets/156128630/3b848997-cb70-4b8c-9b33-3c823dd8d3c9">

*Figure 11. MCC Configuration ESUART2*
<img width="428" alt="image" src="https://github.com/Team-310/Team-310.github.io/assets/156128630/12c0e922-4bf9-47a0-937f-61a7483d6fc9">

*Figure 12. MCC Configuration MSSP1*
<img width="442" alt="image" src="https://github.com/Team-310/Team-310.github.io/assets/156128630/53f86935-41dc-457d-9737-ef89d4f4a04f">

*Figure 13. MCC Configuration MSSP2*
<img width="446" alt="image" src="https://github.com/Team-310/Team-310.github.io/assets/156128630/489744d5-5f60-48a8-8dd3-54777dab13f9">

*Figure 14. MCC Configuration TMR2*
<img width="405" alt="image" src="https://github.com/Team-310/Team-310.github.io/assets/156128630/ebcaae43-fcd0-4646-afd2-e707fc111393">

*Figure 15. MCC Configuration Interrupt Module*
<img width="343" alt="image" src="https://github.com/Team-310/Team-310.github.io/assets/156128630/6ca37d53-3179-4cc2-97ab-32fbbb392805">

## MPLAB X Main Code ##
#include "mcc_generated_files/mcc.h"
#include "mcc_generated_files/i2c2_master.h"
#include "mcc_generated_files/examples/i2c2_master_example.h"
#include "mcc_generated_files/eusart2.h"
#include "application.h"
#include "bme280.h"
#include <string.h>
#include <stdio.h>

#define TC74 0x4C
#define TC74_Address 0x00

uint8_t byteArray[] = {0b11101111, 0b11101000, 0b11101101};
uint8_t byteValue;
uint8_t byteValue2;
uint8_t byteValue3;

void main(void)
{
    // Initialize the device
    SYSTEM_Initialize();
    I2C2_Initialize();
    EUSART2_Initialize();
    SPI1_Initialize();
    SPI1_Open(SPI1_DEFAULT);

    uint8_t temp = 0;
    char dataStr[50]; // Buffer to hold the formatted sensor data string

    INTERRUPT_GlobalInterruptEnable();
    INTERRUPT_PeripheralInterruptEnable();

    while (1)
    {
        WeatherStation_initialize();
        WeatherStation_Print();

        float humidity = BME280_getHumidity();
        float pressure = BME280_getPressure();

        if (humidity <= 27) {
            Press_LED_SetHigh();
        } else {
            Press_LED_SetLow();
        }
        __delay_ms(100);

        temp = I2C2_Read1ByteRegister(TC74, TC74_Address); // Read temperature from TC74

        if (temp <= 27) { //25.5
            Temp_LED_SetHigh();

            __delay_ms(50);
            CSNpin_SetLow();
            SPI1_ExchangeByte(0b11101111); // Command to control motor in one direction         
            CSNpin_SetHigh();
            __delay_ms(50);
        } else {
            Temp_LED_SetLow();

            __delay_ms(50);
            CSNpin_SetLow();
            SPI1_ExchangeByte(byteArray[2]); // Command to control motor in another direction        
            CSNpin_SetHigh();
            __delay_ms(50);
        }

        // Format the sensor data into a string
        sprintf(dataStr, "T:%u H:%.2f P:%.2f", temp, humidity, pressure);
        
        // Transmit formatted data to ESP32 over EUSART2
        for (char *ptr = dataStr; *ptr != '\0'; ptr++) {
            EUSART2_Write(*ptr);
        }
        EUSART2_Write('\n'); // Send newline for better readability at the receiver end
    }
}

## MPLAB X BME280 Source File ##
#include "bme280.h"
#include "mcc_generated_files/examples/i2c2_master_example.h"
#include <math.h>

/**
  Section: Driver APIs
 */

uint8_t BME280_getID(void) {
    return I2C2_Read1ByteRegister(BME280_ADDR, BME280_ID_REG);
}

void BME280_reset(void) {
    I2C2_Write1ByteRegister(BME280_ADDR, BME280_RESET_REG, BME280_SOFT_RESET);
}

void BME280_sleep(void) {
    bme280_ctrl_meas.mode = BME280_SLEEP_MODE;
    I2C2_Write1ByteRegister(BME280_ADDR, BME280_CTRL_MEAS_REG, bme280_ctrl_meas.ctrlMeasReg);
}

void BME280_readFactoryCalibrationParams(void) {
    uint8_t paramBuff[24];
    I2C2_ReadDataBlock(BME280_ADDR, BME280_CALIB_DT1_LSB_REG, paramBuff, 24);
    calibParam.dig_T1 = (((uint16_t) paramBuff[1]) << 8) + paramBuff[0];
    calibParam.dig_T2 = (((int) paramBuff[3]) << 8) + paramBuff[2];
    calibParam.dig_T3 = (((int) paramBuff[5]) << 8) + paramBuff[4];
    calibParam.dig_P1 = (((uint16_t) paramBuff[7]) << 8) + paramBuff[6];
    calibParam.dig_P2 = (((int) paramBuff[9]) << 8) + paramBuff[8];
    calibParam.dig_P3 = (((int) paramBuff[11]) << 8) + paramBuff[10];
    calibParam.dig_P4 = (((int) paramBuff[13]) << 8) + paramBuff[12];
    calibParam.dig_P5 = (((int) paramBuff[15]) << 8) + paramBuff[14];
    calibParam.dig_P6 = (((int) paramBuff[17]) << 8) + paramBuff[16];
    calibParam.dig_P7 = (((int) paramBuff[19]) << 8) + paramBuff[18];
    calibParam.dig_P8 = (((int) paramBuff[21]) << 8) + paramBuff[20];
    calibParam.dig_P9 = (((int) paramBuff[23]) << 8) + paramBuff[22];

    calibParam.dig_H1 = (uint8_t) I2C2_Read1ByteRegister(BME280_ADDR, BME280_CALIB_DH1_REG);

    I2C2_ReadDataBlock(BME280_ADDR, BME280_CALIB_DH2_LSB_REG, paramBuff, 7);
    calibParam.dig_H2 = (((int) paramBuff[1]) << 8) + paramBuff[0];
    calibParam.dig_H3 = (uint8_t) paramBuff[2];
    calibParam.dig_H4 = (((int) paramBuff[3]) << 4) | (paramBuff[4] & 0xF);
    calibParam.dig_H5 = (((int) paramBuff[5]) << 4) | (paramBuff[4] >> 4);
    calibParam.dig_H6 = (short) paramBuff[6];
}

void BME280_config(uint8_t sbtime, uint8_t coeff) {
    bme280_config.t_sb = sbtime; // Set standby time;
    bme280_config.filter = coeff; // Set filter coefficient;
}

void BME280_ctrl_meas(uint8_t osrs_T, uint8_t osrs_P, uint8_t mode) {
    bme280_ctrl_meas.osrs_T = osrs_T; // Set oversampling temperature;
    bme280_ctrl_meas.osrs_P = osrs_P; // Set oversampling pressure;
    bme280_ctrl_meas.mode = mode; // Set sensor mode;
}

void BME280_ctrl_hum(uint8_t osrs_H) {
    bme280_ctrl_hum = osrs_H; // Set oversampling humidity;
}

void BME280_initializeSensor(void) {
    I2C2_Write1ByteRegister(BME280_ADDR, BME280_CONFIG_REG, bme280_config.configReg);
    I2C2_Write1ByteRegister(BME280_ADDR, BME280_CTRL_HUM_REG, bme280_ctrl_hum);
    I2C2_Write1ByteRegister(BME280_ADDR, BME280_CTRL_MEAS_REG, bme280_ctrl_meas.ctrlMeasReg);
}

void BME280_startForcedSensing(void) {
    bme280_ctrl_meas.mode = BME280_FORCED_MODE;
    I2C2_Write1ByteRegister(BME280_ADDR, BME280_CTRL_MEAS_REG, bme280_ctrl_meas.ctrlMeasReg);
}

void BME280_readMeasurements(void) {
    uint8_t sensorData[BME280_DATA_FRAME_SIZE];

    I2C2_ReadDataBlock(BME280_ADDR, BME280_PRESS_MSB_REG, sensorData, BME280_DATA_FRAME_SIZE);

    adc_H = ((uint32_t) sensorData[BME280_HUM_MSB] << 8) |
            sensorData[BME280_HUM_LSB];

    adc_T = ((uint32_t) sensorData[BME280_TEMP_MSB] << 12) |
            (((uint32_t) sensorData[BME280_TEMP_LSB] << 4) |
            ((uint32_t) sensorData[BME280_TEMP_XLSB] >> 4));

    adc_P = ((uint32_t) sensorData[BME280_PRESS_MSB] << 12) |
            (((uint32_t) sensorData[BME280_PRESS_LSB] << 4) |
            ((uint32_t) sensorData[BME280_PRESS_XLSB] >> 4));
}

float BME280_getTemperature(void) {
    float temperature = (float) BME280_compensateTemperature() / 100;
    return temperature;
}

float BME280_getPressure(void) {
    float pressure = (float) BME280_compensatePressure() / 100; // measured in hPa (equivalent to millibar)
 
    // Note: Atmospheric pressure changes with elevation. 
    // The following code finds the equivalent pressure at sea level to give accurate readings
    // in accordance with the international Standard Atmosphere.
    // The equation is: P0 = P1 (1 - (0.0065h/ (T + 0.0065h + 273.15))^(-5.257)
    // where:   P0 = calculated mean sea level pressure (hPa)   
    //          P1 = actual measured pressure (hPa))
    //          h = elevation (m) 
    //          T = temp is degrees C
    float temp = BME280_getTemperature();
    double mantissa = 1 - (0.0065 * ELEVATION / (temp + (0.0065 * ELEVATION) + 273.15));
    double adjustment = pow(mantissa, -5.257);
    float press_adj = adjustment * pressure;

    return press_adj;
}

float BME280_getHumidity(void) {
    float humidity = (float) BME280_compensateHumidity() / 1024;
    return humidity;
}

/* 
 * Returns temperature in DegC, resolution is 0.01 DegC. 
 * Output value of "5123" equals 51.23 DegC.  
 */
static uint32_t BME280_compensateTemperature(void) {
    long long tempV1, tempV2, t;

    tempV1 = ((((adc_T >> 3) - ((long long) calibParam.dig_T1 << 1))) * ((long long) calibParam.dig_T2)) >> 11;
    tempV2 = (((((adc_T >> 4) - ((long long) calibParam.dig_T1)) * ((adc_T >> 4) - ((long long) calibParam.dig_T1))) >> 12)*((long long) calibParam.dig_T3)) >> 14;
    t_fine = tempV1 + tempV2;
    t = (t_fine * 5 + 128) >> 8;

    return t;
}

/* 
 * Returns pressure in Pa as unsigned 32 bit integer. 
 * Output value of "96386" equals 96386 Pa = 96.386 kPa 
 */
 static uint32_t BME280_compensatePressure(void) {
    long pressV1, pressV2;
    uint32_t p;

    pressV1 = (((long) t_fine) >> 1) - (long) 64000;
    pressV2 = (((pressV1 >> 2) * (pressV1 >> 2)) >> 11) * ((long) calibParam.dig_P6);
    pressV2 = pressV2 + ((pressV1 * ((long) calibParam.dig_P5)) << 1);
    pressV2 = (pressV2 >> 2)+(((long) calibParam.dig_P4) << 16);
    pressV1 = (((calibParam.dig_P3 * (((pressV1 >> 2) * (pressV1 >> 2)) >> 13)) >> 3) +
            ((((long) calibParam.dig_P2) * pressV1) >> 1)) >> 18;
    pressV1 = ((((32768 + pressV1))*((long) calibParam.dig_P1)) >> 15);

    if (pressV1 == 0) {
        // avoid exception caused by division by zero
        return 0;
    }

    p = (((uint32_t) (((long) 1048576) - adc_P)-(pressV2 >> 12)))*3125;
    if (p < 0x80000000) {
        p = (p << 1) / ((uint32_t) pressV1);
    } else {
        p = (p / (uint32_t) pressV1) * 2;
    }

    pressV1 = (((long) calibParam.dig_P9) * ((long) (((p >> 3) * (p >> 3)) >> 13))) >> 12;
    pressV2 = (((long) (p >> 2)) * ((long) calibParam.dig_P8)) >> 13;
    p = (uint32_t) ((long) p + ((pressV1 + pressV2 + calibParam.dig_P7) >> 4));

    return p;
}

static uint32_t BME280_compensateHumidity(void) {//static
    long humV;
    uint32_t h;

    humV = (t_fine - ((long) 76800));
    humV = (((((adc_H << 14) - (((long) calibParam.dig_H4) << 20) - (((long) calibParam.dig_H5) * humV)) +
            ((long) 16384)) >> 15) * (((((((humV * ((long) calibParam.dig_H6)) >> 10) *
            (((humV * ((long) calibParam.dig_H3)) >> 11) + ((long) 32768))) >> 10) +
            ((long) 2097152)) * ((long) calibParam.dig_H2) + 8192) >> 14));
    humV = (humV - (((((humV >> 15) * (humV >> 15)) >> 7) * ((long) calibParam.dig_H1)) >> 4));
    humV = (humV < 0 ? 0 : humV);
    humV = (humV > 419430400 ? 419430400 : humV);

    h = (uint32_t) (humV >> 12);
    return h;
}

## MPLAB X Application Source Code ##

#include "application.h"

/**
  Section: Variable Definitions
 */

#define DEFAULT_STANDBY_TIME    BME280_STANDBY_HALFMS
#define DEFAULT_FILTER_COEFF    BME280_FILTER_COEFF_OFF
#define DEFAULT_TEMP_OSRS       BME280_OVERSAMP_X1
#define DEFAULT_PRESS_OSRS      BME280_OVERSAMP_X1
#define DEFAULT_HUM_OSRS        BME280_OVERSAMP_X1
#define DEFAULT_SENSOR_MODE     BME280_FORCED_MODE

bool weather_initialized = 0;

bool label_initial = false;
/**
  Section: Driver APIs
 */

void WeatherClick_readSensors(void) {
    if (DEFAULT_SENSOR_MODE == BME280_FORCED_MODE) {
        BME280_startForcedSensing();
    }
    BME280_readMeasurements();
}


void WeatherStation_initialize(void) {
    BME280_reset();
    __delay_ms(50);
    BME280_readFactoryCalibrationParams();
    BME280_config(BME280_STANDBY_HALFMS, BME280_FILTER_COEFF_OFF);
    BME280_ctrl_meas(BME280_OVERSAMP_X1, BME280_OVERSAMP_X1, BME280_FORCED_MODE);
    BME280_ctrl_hum(BME280_OVERSAMP_X1);
    BME280_initializeSensor();
    weather_initialized = 1;
}

void WeatherStation_Print(void) {
    
    WeatherClick_readSensors();

    temp_string = BME280_getTemperature();
    press_string = BME280_getPressure();    // using float
    humid_string = (uint8_t) BME280_getHumidity();
    
    sprintf(str_temp, "      %.1fC", temp_string); // Temperature to String Conversion;
    sprintf(str_press, "       %u hPa", press_string); // Pressure to String Conversion;
    sprintf(str_hum, "          %u%%", humid_string); // Humidity to String Conversion;
    

    printf("\n Temperature: %.1fC \r\n", temp_string);
    printf("\n Pressure: %u hPa\r\n", press_string);
    printf("\n Relative Humidity: %u%% \r\n", humid_string);
   
 }


