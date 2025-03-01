# ESP32-CAM Webcam Example with PlatformIO

## Description

This is the example code from [CameraWebServer.ino](https://github.com/espressif/arduino-esp32/blob/master/libraries/ESP32/examples/Camera/CameraWebServer/CameraWebServer.ino) converted to a PlatformIO compilable project.

![cam](cam.png)

## Configuration

### Camera model

Known camera models can be selected at the top of the `main.cpp` in the selection

```cpp
// Select camera model
//#define CAMERA_MODEL_WROVER_KIT // Has PSRAM
//#define CAMERA_MODEL_ESP_EYE // Has PSRAM
//#define CAMERA_MODEL_M5STACK_PSRAM // Has PSRAM
//#define CAMERA_MODEL_M5STACK_V2_PSRAM // M5Camera version B Has PSRAM
//#define CAMERA_MODEL_M5STACK_WIDE // Has PSRAM
//#define CAMERA_MODEL_M5STACK_ESP32CAM // No PSRAM
#define CAMERA_MODEL_AI_THINKER // Has PSRAM
//#define CAMERA_MODEL_TTGO_T_JOURNAL // No PSRAM
```

These pins then map to the [include/camera_pins.h](include/camera_pins.h) definitions.

If you have custom camera pins that does not follow the known cameras, you must modify and add these pins to the `camera_pins.h` file.

### WiFi credentials

Add the following content and fill your WiFi SSID and password in `include/wifi_creds.h`:

```cpp
#ifndef WIFI_CREDS_H
#define WIFI_CREDS_H

#define WIFI_SSID "*********"
#define WIFI_PASSWORD "*********"

#endif  // WIFI_CREDS_H
```

### Board configuration

The `platformio.ini` currently configures the project for an ESP-WROVER chipset (has PSRAM), with the flash in QIO mode at 80MHz.

If these settings are not correct for you, change the file with your correct `board = ..` value and other settings accordingly to the [PlatformIO board documentation](https://platformio.org/boards).
