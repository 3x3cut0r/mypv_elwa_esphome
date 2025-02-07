# MY PV ELWA ESPHome Adapter

ESPHome configuration file to setup IR sensor to read data from MY PV ELWA IR interface

0. [Link to discussion](https://community.home-assistant.io/t/elwa-dc-read-uart-protocol-by-ir-hichi-with-esphome-how-to-get-into-seperate-variables/652873)

1. Installation

```bash
# install esphome
# visit https://esphome.io/guides/installing_esphome.html

# clone and enter this repo
git clone https://github.com/3x3cut0r/mypv_elwa_esphome_ir_sensor.git
cd mypv_elwa_esphome_ir_sensor

# create your secrets.yaml
cp secrets.example.yaml secrets.yaml

# generate api encryption key
openssl rand -base64 32

# replace the lines in your secrets.yaml:
api_encryption_key: 'your-base64-api-encryption-key'
wifi_ssid: 'your-wifi-ssid'
wifi_password: 'your-wifi-password'

# validate your configuration
esphome config esphome.yaml
```

2. Cabling
   | **IR Hichi** | **ESP32** |
   |------------|---------|
   | TX | GPIO 16 (RX) |
   | RX | GPIO 17 (TX) |
   | GND | GND |
   | VCC | 5V |
