### Espressif Audio Development Framework (ESP-ADF) Example Walk-Through

Honestly, this is here as a sort of backup copy of how I got the LyraT Mini audio dev board configured and able to run the examples (https://github.com/espressif/esp-adf). Other than that, it's a quick walk-through for *beginners* on how I got the `pipeline_recording_to_sdcard` example to work using the ESP32 ADF framework and hopefully it might help someone else just starting out. For me at least, it was extremely difficult to get the examples to work mostly just due to how the docs were organized. That being said, the docs are *very* good. The example is a good starting point for anyone who wants to record audio on one of the ESP32 audio development boards. The example uses the following components:

-   [ESP32 ADF GitHub Repository](https://github.com/espressif/esp-adf)
-   [ESP32 LyraT Mini audio development board](https://www.espressif.com/en/products/hardware/esp32-lyrat-mini)
-   [ESP-ADF](https://docs.espressif.com/projects/esp-adf/en/latest/get-started/index.html#installation-step-by-step)

The example is located in the examples `esp-adf/examples/pipeline/pipeline_recording_to_sdcard` directory at the GitHub repository here: [pipeline_recording_to_sdcard](https://github.com/espressif/esp-adf/tree/3f8a6aab2636a1c569931f9b4af911013abf021e/examples/recorder/pipeline_recording_to_sdcard)

---

Installing ESP-ADF framework

0. Do not worry with installing the ESP-IDF framework, I still have not figured out why they make you install the IDF framework first...could very well be my inexperience showing but you do not need to do this if you just want to start working with the ADF framework right away. Also, ADF keeps it's own copy of IDF and uses that which turns out to be a good thing.

1. So, the actual first step is to install the ESP-ADF framework. Use the `master` repository branch. The `master` branch is the most stable branch and using specific versions of the ESP-ADF framework caused me a lot issues. I spent a lot of time trying to get the example to work using a specific version of the ESP-ADF framework. I was not successful. I recommend using the `master` branch.

```bash
git clone --recursive https://github.com/espressif/esp-adf.git
```

2. Second, configure the `$ESP-IDF` and `$ESP-ADF` compilation environment by running the following commands. I didn't use the install or export.sh scripts located in the root directory initially and this caused me a lot of problems. I recommend using these scripts.

```bash
cd esp-adf
./install.sh
. ./export.sh
```

3. After completing the above environment variable configuration, you should be able to run the following command without any errors.

```bash
cd $ADF_PATH/examples/get-started/${your_example_program_of_choice}
idf.py build flash monitor
```

Note: Remember that you always need to run the `export.sh` script again after your exit your terminal session. This is because the environment variables are not saved after you exit your terminal session. And it is NOT recommended to add the environment variables to your `.bashrc` file. This is because the ESP-IDF and ESP-ADF frameworks are constantly being updated. If you add the environment variables to your `.bashrc` file, you will have to update the environment variables every time the ESP-IDF or ESP-ADF frameworks are updated. This is a pain. I recommend using the `export.sh` script each time you start a new terminal session. After this, you can run the `idf.py` commands _inside_ of your chosen example directory.

Again, this is for *beginners*, those that know very little and are struggling with getting the toolchain set up. Once you reach the `idf.py build flash monitor` stage it's pretty smooth sailing after that. The examples *just work*. This is a fun and powerful audio dev board, hopefully I'll build some interesting things with it once I learn more. 
