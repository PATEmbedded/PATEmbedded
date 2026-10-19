<p align="center">
  <img src="assets/banner.svg" width="100%" alt="Pourya Afshintabar · Embedded Systems Engineer · Firmware, hardware and Edge AI · 10+ years building embedded products">
</p>

<p align="center">
  <a href="mailto:pat.embedded@gmail.com"><img alt="Email" src="https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white"></a>
  <a href="https://www.linkedin.com/in/pourya-afshintabar/"><img alt="LinkedIn" src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white"></a>
</p>

I build complete embedded products, from system architecture, schematics and multilayer PCBs to C/C++ firmware on bare metal, FreeRTOS and embedded Linux, and I carry them through bring-up and testing to series production. In more than ten years my work has spanned industrial automation, oil & gas, power, medical devices and IoT, and I have led hardware teams along the way. Today my focus is Edge AI: small neural networks that run directly on microcontrollers, with no cloud.

<p>
  <img alt="C" src="https://img.shields.io/badge/C-A8B9CC?style=flat-square&logo=c&logoColor=black">
  <img alt="C++17" src="https://img.shields.io/badge/C%2B%2B17-00599C?style=flat-square&logo=cplusplus&logoColor=white">
  <img alt="Python" src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white">
  <img alt="FreeRTOS" src="https://img.shields.io/badge/FreeRTOS-2E7D32?style=flat-square">
  <img alt="Embedded Linux" src="https://img.shields.io/badge/Embedded_Linux-FCC624?style=flat-square&logo=linux&logoColor=black">
  <img alt="ESP-IDF" src="https://img.shields.io/badge/ESP--IDF-E7352C?style=flat-square&logo=espressif&logoColor=white">
  <img alt="STM32" src="https://img.shields.io/badge/STM32-03234B?style=flat-square&logo=stmicroelectronics&logoColor=white">
  <img alt="Altium Designer" src="https://img.shields.io/badge/Altium_Designer-A5915F?style=flat-square&logo=altiumdesigner&logoColor=white">
  <img alt="TensorFlow Lite Micro" src="https://img.shields.io/badge/TensorFlow_Lite_Micro-FF6F00?style=flat-square&logo=tensorflow&logoColor=white">
</p>

<table>
  <tr><td><b>Firmware</b></td><td>C, C++ (11/14/17), Python · bare metal, FreeRTOS, embedded Linux · GCC, CMake, Yocto/Buildroot</td></tr>
  <tr><td><b>Processors</b></td><td>ARM Cortex-M (ST, NXP, TI) · Cortex-A (TI Sitara, Allwinner) · ESP32 · Xilinx FPGA · TI C2000 DSP</td></tr>
  <tr><td><b>Hardware</b></td><td>Altium Designer · multilayer, high-speed and low-noise PCBs · signal and power integrity · EMI/EMC · DFM</td></tr>
  <tr><td><b>Connectivity</b></td><td>Gigabit Ethernet, PoE, CAN, RS-485, USB · Wi-Fi, BLE, LoRa · MQTT, HTTP/REST, TLS, OTA</td></tr>
  <tr><td><b>Edge AI</b></td><td>TensorFlow Lite Micro, Edge Impulse, STM32Cube.AI · quantization, pruning · CMSIS-NN</td></tr>
</table>

## Featured project

### [esp32-secure-ota](https://github.com/PATEmbedded/esp32-secure-ota): signed firmware updates for ESP32

[![CI](https://github.com/PATEmbedded/esp32-secure-ota/actions/workflows/ci.yml/badge.svg)](https://github.com/PATEmbedded/esp32-secure-ota/actions/workflows/ci.yml)
[![Release](https://img.shields.io/github/v/release/PATEmbedded/esp32-secure-ota?style=flat-square)](https://github.com/PATEmbedded/esp32-secure-ota/releases)

Firmware updates over HTTPS for ESP32 and ESP32-S3 with ESP-IDF. A device in the field never installs a forged or an older image, and never stays on a broken one.

| Check | How |
|---|---|
| Server identity | TLS against the ESP-IDF certificate bundle or one pinned CA; plain HTTP is refused |
| Image origin | Only images signed with the release key: ECDSA P-256 on ESP32, RSA-3072 on ESP32-S3 |
| Integrity | SHA-256 checked before the new slot is selected, so an interrupted download never boots |
| No downgrade | The image header is read first; another project or an older version is rejected before the download goes on |
| Health after the update | The new image must pass a self-test, or the bootloader returns to the previous one |

With a written threat model, unit tests, and CI that builds and signs the firmware with ESP-IDF 5.5 and 6.0.

## Open-source libraries

<table>
  <tr>
    <td width="50%" valign="top">
      <h3><a href="https://github.com/PATEmbedded/embedded-cpp-toolkit">embedded-cpp-toolkit</a></h3>
      <p>Header-only firmware building blocks: a table-driven state machine, observable values, weekly schedules, JSON request validation, a debouncer and a periodic timer. No hardware dependency.</p>
      <p><a href="https://github.com/PATEmbedded/embedded-cpp-toolkit/actions/workflows/ci.yml"><img alt="CI" src="https://github.com/PATEmbedded/embedded-cpp-toolkit/actions/workflows/ci.yml/badge.svg"></a> <img alt="C++17, any MCU" src="https://img.shields.io/badge/C%2B%2B17-any_MCU-00599C?style=flat-square"></p>
    </td>
    <td width="50%" valign="top">
      <h3><a href="https://github.com/PATEmbedded/esp32-psram-allocator">esp32-psram-allocator</a></h3>
      <p>Standard C++ containers in the external PSRAM of ESP32 chips, with an optional fallback to internal RAM, so large data leaves the internal RAM to Wi-Fi and FreeRTOS.</p>
      <p><a href="https://github.com/PATEmbedded/esp32-psram-allocator/actions/workflows/ci.yml"><img alt="CI" src="https://github.com/PATEmbedded/esp32-psram-allocator/actions/workflows/ci.yml/badge.svg"></a> <img alt="C++17, ESP-IDF" src="https://img.shields.io/badge/C%2B%2B17-ESP--IDF-E7352C?style=flat-square"></p>
    </td>
  </tr>
  <tr>
    <td width="50%" valign="top">
      <h3><a href="https://github.com/PATEmbedded/esp32-gpio-devices">esp32-gpio-devices</a></h3>
      <p>Debounced buttons with click, multi-click and long-press events, and outputs that blink and pulse. One task handles them all and sleeps while nothing happens.</p>
      <p><a href="https://github.com/PATEmbedded/esp32-gpio-devices/actions/workflows/ci.yml"><img alt="CI" src="https://github.com/PATEmbedded/esp32-gpio-devices/actions/workflows/ci.yml/badge.svg"></a> <img alt="C++17, ESP-IDF" src="https://img.shields.io/badge/C%2B%2B17-ESP--IDF-E7352C?style=flat-square"></p>
    </td>
    <td width="50%" valign="top">
      <h3><a href="https://github.com/PATEmbedded/esp32-time-sync">esp32-time-sync</a></h3>
      <p>SNTP with time zones, a status that says how far the clock can be trusted, and a sensible clock after a power cut instead of 1970.</p>
      <p><a href="https://github.com/PATEmbedded/esp32-time-sync/actions/workflows/ci.yml"><img alt="CI" src="https://github.com/PATEmbedded/esp32-time-sync/actions/workflows/ci.yml/badge.svg"></a> <img alt="C, ESP-IDF" src="https://img.shields.io/badge/C-ESP--IDF-E7352C?style=flat-square"></p>
    </td>
  </tr>
</table>

Every repository here is built the same way:

- unit tests on a PC with GCC and Clang, under AddressSanitizer and UndefinedBehaviorSanitizer
- firmware and example builds in CI, for ESP-IDF 5.5 and 6.0 where ESP-IDF is used
- documentation with diagrams and examples, a changelog, tagged releases and the MIT license

---

**Contact:** [pat.embedded@gmail.com](mailto:pat.embedded@gmail.com) · [LinkedIn](https://www.linkedin.com/in/pourya-afshintabar/)
