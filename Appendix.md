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
