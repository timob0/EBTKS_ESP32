# EBTKS ESP32 firmware

Build the ESP32 firmware with PlatformIO:

```sh
platformio run -e esp32dev
```

The project uses the ESP32 Arduino core's built-in SPIFFS filesystem. Do not
install the legacy `LittleFS_esp32` library: it is unused here and incompatible
with the current core's filesystem API.

The asynchronous server and TCP dependencies are pinned to a compatible pair
from ESP32Async. The former `me-no-dev/ESP Async WebServer` package is no longer
available under that name.
ESPAsyncWiFiManager is also fetched from its original GitHub repository at a
fixed revision because its former registry package is unavailable.

The browser terminal (`/` and `/ws`) and the custom firmware updater (`/updater`)
remain available. The optional filesystem editor (`/edit`) has been removed
because it is no longer bundled with ESPAsyncWebServer. AsyncElegantOTA is not
needed by the custom updater.
