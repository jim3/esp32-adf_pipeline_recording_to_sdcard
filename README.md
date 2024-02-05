### Espressif Audio Development Framework (ESP-ADF) Example Walk-Through

This is a walk-through on how I got the `pipeline_recording_to_sdcard` example to work using the ESP32 ADF framework. For me at least, it was extremely difficult to get the example to work. The example is a good starting point for anyone who wants to record audio one of the ESP32 audio development boards. The example uses the following components:

-   [ESP32 ADF GitHub Repository](https://github.com/espressif/esp-adf)
-   [ESP32 LyraT Mini audio development board](https://www.espressif.com/en/products/hardware/esp32-lyrat-mini)
-   [ESP-ADF](https://docs.espressif.com/projects/esp-adf/en/latest/get-started/index.html#installation-step-by-step)

The example is located in the examples `esp-adf/examples/pipeline/pipeline_recording_to_sdcard` directory at the GitHub repository here: [pipeline_recording_to_sdcard](https://github.com/espressif/esp-adf/tree/3f8a6aab2636a1c569931f9b4af911013abf021e/examples/recorder/pipeline_recording_to_sdcard)

---

## Table of Contents

