# ESP8266 (ESP-12) Modbus TCP <-> RTU bridge
 The simpliest (all in one file) Arduino / VSCode example.
 ESP8266 works as:
 1. Modbus RTU master via UART (Software Serial)
 2. Modbas TCP server via WiFi
    
## How it works
1. External TCP client (for instance Windows PC application) sends Modbus request on ESP8266 local IP address.
2. ESP8266 sens Modbus RTU request vai UART (Serial port) to any Modbus slave device.
3. ESP8266 receives Modbus RTU responce from the slave.
4. ESP8266 translate the responce to TCP client via WiFi.
