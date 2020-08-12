# ulab Samples - links, examples, benchmarks, etc, about ulab module, a NumPy-like array manipulation library for Micropython and CircuitPython

##### Authors : [Eduardo Destefani Stefanato](https://github.com/EduardoDestefani), [Pedro Henrique Robadel da Silva Camâra](https://github.com/ph-robadel), [Roberto Colistete Jr](https://github.com/rcolistete), [Thiago Ferreira Santos](https://github.com/thiagofe)

##### Last update : August 12th 2020


## Links about ulab

- [official repository 'v923z/micropython-ulab'](https://github.com/v923z/micropython-ulab);
- [official documentation 'micropython-ulab’s documentation'](https://micropython-ulab.readthedocs.io/);
- [Jupyter Notebook 'ulab Manual, with technical details of the implementation'](https://github.com/v923z/micropython-ulab/blob/master/docs/ulab-manual.ipynb);
- Adafruit tutorial, ['ulab: Crunch Numbers fast in CircuitPython. Use numpy-like commands to process data quickly'](https://learn.adafruit.com/ulab-crunch-numbers-fast-with-circuitpython);
- MicroPython Forum topic, ['ulab, or what you will - numpy on bare metal'](https://forum.micropython.org/viewtopic.php?f=3&t=7005);
- news e articles about ulab :
    * vídeo [It's FFT Tuesday! Testing out mic FFT on CircuitPython](https://www.youtube.com/watch?v=c0SMT1UY37M) - Adafruit Industries
YouTube channel, 02/2020;
    * [NUMPY COMES TO MICRO PYTHON](https://hackaday.com/2019/10/29/numpy-comes-to-micro-python/) - Hackaday, 29/10/2019;
    * [HackSpace Magazine Issue 30 – CircuitPython ulab](https://blog.adafruit.com/2020/04/24/hackspace-magazine-issue-30-circuitpython-ulab-clue-adafruit-circuitpython-hackspacemag-adafruit/) - Adafruit Blog, 24/04/2020;
    * [Zoltán Vörös' ulab Brings NumPy-Style Fast Math to MicroPython in Just 25kB of Compiled Code"](https://www.hackster.io/news/zoltan-voros-ulab-brings-numpy-style-fast-math-to-micropython-in-just-25kb-of-compiled-code-aa52a81cd269) - Hackster, 11/2019.


## Firmwares and MicroPython boards adopting ulab

- [CircuitPython firmware >= v5.1.0 (02/04/2020)](https://github.com/adafruit/circuitpython/releases/tag/5.1.0), ulab in CircuitPython isn't included on boards with small flash memory.  
[CircuitPython 5.1.0 Released! - Adafruit Blog, 02/04/2020](https://blog.adafruit.com/2020/04/02/circuitpython-5-1-0-released-circuitpython-python-ulab-adafruit-circuitpython/).  
[Official CircuitPython documentação about ulab](https://circuitpython.readthedocs.io/en/latest/autoapi/ulab/index.html);
- [OpenMV Cam firmware >= v3.5.0 (20191104)](https://docs.openmv.io/library/index.html?highlight=ulab#third-party-libraries-on-the-openmv-cam);
- [MicroPython for K210 Lobo firmware >= v202002](https://loboris.eu/forum/showthread.php?tid=1004);
- [MaixPy >= v0.5.0 (28/12/2019)](https://twitter.com/SipeedIO/status/1210875423627702272).


## Firmwares with ulab included, built by the community

- ["Firmwares for MicroPython on Pyboard v1.1/Lite v1.0/D SF2/D SF3/D SF6 - rcolistete GitLab"](https://gitlab.com/rcolistete/micropython-firmwares/-/tree/master/Pyboard), with single precision (SP/FP32) and double precision (DP/FP64), without and with threads;
- ["Firmwares for MicroPython on ESP8266 - rcolistete GitLab"](https://gitlab.com/rcolistete/micropython-firmwares/-/tree/master/ESP8266), with single precision (SP/FP32), without threads;
- ["Firmwares for MicroPython on ESP32 - rcolistete GitLab"](https://gitlab.com/rcolistete/micropython-firmwares/-/tree/master/ESP32), with single precision (SP/FP32) and double precision (DP/FP64), with threads;
- ["Firmwares for MicroPython on Pycom boards"](https://gitlab.com/rcolistete/micropython-firmwares/-/tree/master/Pycom), without and with PyBytes, with single precision (SP/FP32) and double precision (DP/FP64), with threads.


## Benchmark of FFT with 1024 points

`ulab.fft.fft()` calculation time for 1024 points with single precision (FP32) and double precision (FP64) for float point numbers, using ulab v0.54.0 & MicroPython v1.12 (if not cited) :

| Board                       |  Clock (MHz)  |  Time (ms) in FP32  |  Time (ms) in FP64  |
| :-------------------------- | :-----------: | :-----------------: | :-----------------: |
| Pyboard Lite v1.0           | 96 (default)  |        3.572        |        53.39        |
| Pyboard v1.1                | 168 (default) |        2.0382       |        32.076       |
| Pyboard v1.1 CPy 6.0.0a2    | 168 (default) |        2.253        |          -          |
| Pyboard D SF2               | 216 (maximum) |        1.039        |        17.660       |
| Pyboard D SF6               | 216 (maximum) |        1.001        |        2.041        |
| ESP8266 EX (WeMos D1 Mini)  | 160 (maximum) |       28.874        |          -          |
| ESP32-PICO-D4 rev1 (M5StickC) | 240 (maximum) |      1.635        |        20.97        |
| ESP32 D0WDQ6 rev0 (LoLin32) | 240 (maximum) |        1.53         |        20.95        |
| ESP32 PSRAM D0WDQ6 rev1 (LoLin32 Pro) | 240 (maximum) | 2.30      |        23.18        |
| ESP32 D0WDQ6 rev0 (LoPy v1) | 160 (default) |         2.38        |        32.877       |
| ESP32 PSRAM D0WDQ6 rev1 (LoPy4) | 160 (default) |     3.00        |        34.5         |
| MAixBiT - Lobo fw v202002   | 400 (default) |          -          |       **1.030**     |
| MAixBiT - MaixPy v0.5.0     | 600 (maximum) |        1.45         |          -          |
| OpenMV M7 - fw v3.6.7       | 216 (default) |        0.780        |          -          |
| OpenMV H7 - fw v3.6.7       | 480 (default) |      **0.397**      |          -          |
| OpenMV H7 CPy 6.0.0a2       | 480 (default) |        1.99         |          -          |
| ItsyBitsy M4 CPy 6.0.0a2    | 120 (default) |         3.1         |          -          |
| Adafruit CLUE CPy 6.0.0a2   | 64 (default)  |        7.19         |          -          |
| Teensy 4.0 CPy 6.0.0a2      | 600 (default) |        1.84         |          -          |

### Observations

- firmwares with ulab included on Pyboard's, ESP8266, ESP32 and Pycom boards, from ["MicroPython Firmwares - rcolistete GitLab"](https://gitlab.com/rcolistete/micropython-firmwares);
- CircuitPython (CPy) 6.0.0a2 using ulab v0.51.1, only with single precision (FP32);
- MAixBiT - Lobo fw v202002 using ulab v0.37.0, only with  double precision (FP64);
- MAixBiT - MaixPy v0.5.0 using ulab v0.26.2, only with single precision (FP32);
- OpenMV fw v3.6.7 using ulab v0.50.2, only with single precision (FP32).

### Analyses

- [**OpenMV H7**](https://openmv.io/products/openmv-cam-h7) with ARM Cortex-M7 [STM32H743VI](https://www.st.com/en/microcontrollers-microprocessors/stm32h743vi.html) has double precision (FP64) hardware support, but the OpenMV firmware only supports single precision (FP32), **is the winner in single precision (FP32) FFT**. Notice that [CircuitPython on OpenMV H7](https://circuitpython.org/board/openmv_h7/) is not well optimised;
- [**Sipeed MAix BiT**](https://www.seeedstudio.com/Sipeed-MAix-BiT-for-RISC-V-AI-IoT-p-2872.html) with RISC-V 64bit [Kendryte K210](https://canaan.io/product/kendryteai) has double precision (FP64) hardware support **is the winner in double precision (FP64) FFT when using the MicroPython for K210 Lobo firmware** (supporting only FP64). While MaixPy firmware is for single precision (FP32), even with overclocking it is slower, so not well optimised;
- [**OpenMV M7**](https://openmv.io/products/openmv-cam-m7) is old as it was released in January 2017, but with ARM Cortex-M7 [STM32F765VI](https://www.st.com/en/microcontrollers-microprocessors/stm32f765vi.html) it has FP64 hardware support, while OpenMV firmware only supporting single precision (FP32), it is **the 2nd place in FP32 FFT**;
- [**Pyboard D SF6**](https://store.micropython.org/product/PYBD-SF6-W4F2) with ARM Cortex-M7 [STM32F767VIT](https://www.st.com/en/microcontrollers-microprocessors/stm32f767vi.html) has double precision (FP64) hardware support, it is **2nd place in FP64 FFT and 3rd place in FP32 FFT**;
- [**Pyboard D SF2**](https://store.micropython.org/product/PYBD-SF2-W4F2) with ARM Cortex-M7 [STM32F722IEK](https://www.st.com/content/st_com/en/products/microcontrollers-microprocessors/stm32-32-bit-arm-cortex-mcus/stm32-high-performance-mcus/stm32f7-series/stm32f7x2/stm32f722ie.html), is a lot cheaper than Pyboard D SF6 but has only FP32 hardware support, obtaining the **4th place** and almost the same performance of Pyboard D SF6 **in in FP32 FFT**, but is is a lot slower in FP64 FFT;
- ESP32 boards with higher (240 MHz) clock and without PSRAM have good performance in FP32 FFT, 
- [Teensy 4.0](https://www.pjrc.com/store/teensy40.html) with ARM Cortex-M7 [NXP iMX RT1062](https://www.nxp.com/products/processors-and-microcontrollers/arm-microcontrollers/i-mx-rt-crossover-mcus/i-mx-rt1060-crossover-mcu-with-arm-cortex-m7-core:i.MX-RT1060) has double precision (FP64) hardware support, bbut CircuitPython only supports FP32 and it is not well optimised.
