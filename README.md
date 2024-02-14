# DCC Handler 
This is the ESP-NOW peer handler for the DCC project. It is responsible for receiving ESP-NOW submersion packets and forwarding them to the DCCListener. A 9-byte packet is in the form
```c
typedef struct {
    uint8_t MOB_STATE;
    float longitude;
    uint8_t latitude;
} 
```
The MOB_STATE is a 1-byte value that represents the state of the MOB. The longitude is a 4-byte float value that represents the longitude of the MOB. The latitude is a 4-byte float value that represents the latitude of the MOB.

This will listen for ESP-NOW packets and forward them to the DCCListener over Serial UART. These MOB strings are in the form:
"MOB: OK, 12345.12345, 12345.12345, 12345.12345"

## Installation
To install the DCC Handler, you need to have the ESP-IDF installed. You can find the installation instructions [here](https://docs.espressif.com/projects/esp-idf/en/latest/esp32/get-started/index.html).

After you have the ESP-IDF installed, you can clone this repository and build the project using the following commands:
```bash
git clone
cd dcc-handler
idf.py build
```

## To Run
To run the DCC Handler, you need to have the ESP32 connected to your computer. You can then run the following command to flash the ESP32:
```bash
idf.py -p <PORT> flash
```

## Configuration
Using idf.py menuconfig, you can configure the DCC Handler to use the correct WiFi and ESP-NOW settings. You can also configure the DCC Handler to use the correct DCCListener address and port.
