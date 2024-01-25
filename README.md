# ESP8266 (ESP-12) Modbus TCP <-> RTU bridge
 The simpliest (all in one file) Arduino / VSCode example.
 ESP8266 works as:
 1. Modbus RTU master via UART (Software Serial port)
 2. Modbas TCP server over WiFi
    
## How it works
1. An external TCP client (such as a Windows PC application) sends a Modbus request to the ESP8266's local IP address.
2. The ESP8266 sens Modbus RTU requests vai UART (Serial port) to any Modbus slave device.
3. The ESP8266 receives a Modbus RTU response from the slave.
4. The ESP8266 transmits the response to the TCP client via WiFi.

## Restrictions
The code supports the most commonly used functions:
+ 0x03 READ HOLDING REGISTERS
+ 0x06 WRITE HOLDING REGISTER
+ 0x10 WRITE MULTIPLE HOLDING REGISTERS

Legacy features not supported:
READ/WRITE COILS/DISCRETE INPUTS

## How to use
+ Visual Studio Code project in the **VSCode project** folder.
+ Arduino IDE project in the **Adruino project** folder.

Enter your Wi-Fi credentials.
```
WiFi.begin("ssidname","password");
```
Replace the UART pins if necessary.
```
//  user defines
#define MB_UART_RX_PIN 13
#define MB_UART_TX_PIN 15
```
Enter the baud rate for the slave device.
```
swSerial.begin(9600, SWSERIAL_8N1, MB_UART_RX_PIN, MB_UART_TX_PIN);
```

## How to find out the local Wi-Fi IP address of ESP8266.
Open the router's web page in a browser. View the list of clients.

## How to debug
Use the built-in USB-COM serial port at the selected baud rate:
```
Serial.begin(115200);
```
