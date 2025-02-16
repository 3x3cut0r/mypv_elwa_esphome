# MY PV ELWA ESPHome Adapter

ESPHome configuration file to setup a IR Hichi uart adapter to read data from MY PV ELWA IR interface  
[Link to discussion](https://community.home-assistant.io/t/elwa-dc-read-uart-protocol-by-ir-hichi-with-esphome-how-to-get-into-seperate-variables/652873)

## Installation

1. install esphome (https://esphome.io/guides/installing_esphome.html)

2. clone and enter this repo

```bash
cd mypv_elwa_esphome
git clone https://github.com/3x3cut0r/mypv_elwa_esphome.git
```

3. create and edit your secrets.yaml

```bash
mv secrets.example.yaml secrets.yaml
```

to connect to home assistant or iobroker you need to generate either an api encryption key or enable mqtt settings in esphome.yaml

```bash
# generate api encryption key
openssl rand -base64 32
```

4. validate your configuration

```bash
esphome config esphome.yaml
```

5. connect your ESP32 to your computer via USB

6. start esphome dashboard

```bash
esphome dashboard .
```

7. open the dashboard in a webbrowser: http://localhost:6052/

8. click on the 3 dots of the ONLINE showing esphome.yaml box -> Install -> Plug into this computer

9. wait for `preparing download`

10. click on `1. Download project` (maybe the file is marked as unsafe -> click on keep file anyway)

11. click on `2. Open ESPHome Web`

12. click on `CONNECT` -> choose your ESP32 on the list

13. clicn on `INSTALL` -> choose your previously downloaded `firmware.factory.bin`

14. while holding the `BOOT`-Button on your device, click on `INSTALL` again

15. wait for the installer to finish

16. your ESP32 should now connect to your wifi

17. check your internet router to get the ip-address of the device (device name is `esphome-web-e45ce4`)

18. open in a webbrowser the ip, e.g.: http://192.168.178.254

## Cabling

![ESP32-DEV-KIT-v4-pinout](ESP32-DEV-KIT-v4-pinout.jpg)

**Note: TX and RX are normally crossed. This was not the case for me. You may have to rotate the two pins to find out what is right.**

| **IR Hichi** | **ESP32**    |
| ------------ | ------------ |
| TX           | GPIO 17 (TX) |
| RX           | GPIO 16 (RX) |
| GND          | GND          |
| VCC          | 5V           |
