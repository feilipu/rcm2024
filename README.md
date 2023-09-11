# RCM2024

This is a RabbitCore® Module using the R2000 microprocessor, designed for RC2014 Standard Bus specification.

The R2000 is substantially compatible with 8080 and Z80 processors, but implements enhanced instructions supporting high level languages such as C.

## Concept

The Rabbit® family of microprocessors is under-represented amongst hobby constructors, and very few (if any) "home made" RabbitCore® Modules have been developed. This RCM2024 is supposed to provide at least one option for hobby constructors and RC2014 enthusiasts.

The Rabbit microprocessor comes in many varieties, but the R2000 is the only version supporting 5V operation enabling it to work with the RC2014 Standard Bus. Therefore this RCM2024 is based on the R2000 Version C microprocessor.

The RCM2024 can be operated as;

 1. a RC2014 CPU Module in a standard RC2014 Backplane and using standard RC2014 Modules,
 2. a RC2014 combined Backplane and microprocessor system supporting RC2014 Modules, and as
 3. a standalone single board computer (SBC) with its own serial, memory, and mass storage support.

The R2000 microprocessor has 5 8-bit parallel ports, in addition to the usual Z80 bus interface, enabling a variety of interfaces to be integrated on to the RCM2024. These include a 8-bit Compact Flash IDE Port, a SPI interface supporting SD Cards and general SPI Master operation, an I2C interface, and up to 4x asynchronous and clocked serial interfaces.

## Hardware Specification

The RCM2024 is a double height RC2014 Module being 99.1mm wide x 99mm high, with one or two RC2014 Standard Bus connectors along one edge.

Standard features include.

- 256 kByte of NOR FLASH, using `WE0`, `OE0`, and `CS0`. This is the cold boot memory device.
- 1 MByte of Static RAM, using `WE0`, `OE0`, and `CS1`.

- Cold boot, and serial programming Port A using a USB interface (FTDI).
- 2 x asynchronous serial interfaces Port C and D with FTDI standard connectors.

- SPI synchronous serial interface Port B with Grove / Sparkfun connectors supporting external SPI Slave devices, and onboard SD Card.
- SD Card cage for optional FAT32 formatted mass storage.

- I2C interface (open drain) with Grove / Sparkfun connector supporting external I2C 5V or 3.3V Slave devices.

- Compact Flash Module 8-bit IDE Interface for optional FAT32 formatted mass storage.

- Also, the R2000 microprocessor has two Timers, and a Real Time clock capability, enabling time of day and interval timing.

### Hardware Modularity

To minimise the cost of the RCM2024 Module the majority of the accessory devices will be implemented as Sub-Modules.

 - Power Supply Module - [Pololu D24V10F5](https://www.pololu.com/product/2831) - optional if used with RC2014 Backplane.
 - SD Card Module - [Adafruit MicroSD Card Breakout](https://www.adafruit.com/product/254) - provides 3.3V to 5V bus conversion.
 - Serial Interface Module(s) - [SparkFun FTDI Basic](https://www.sparkfun.com/products/9716) - FTDI Interface standard serial to USB conversion.
 - Programming Serial Interface Module - [SparkFun FT231X Breakout](https://www.sparkfun.com/products/13263) - FTDI Interface with full breakout.

Integrated accessories are RAM, NOR Flash, CF Card cage, RC2014 Z80 Bus using `WE1` and `OE1`, and Rabbit USB Programming Interface.

### Key Device Selection

The following devices are on the RCM2024 Module

<b>R2000 Microprocessor</b><br>
Manufacturer - Digi International<br>
Manufacturer Product Number - 20-668-0003<br>
Sourcing from [Mouser](https://au.mouser.com/ProductDetail/DIGI/20-668-0003?qs=h7SQhMV2qI2v0rAEPCUB8A%3D%3D)

<b>SRAM 1MB x 8</b><br>
Manufacturer - Infineon Technologies<br>
Manufacturer Product Number - CY62158ELL-45ZSXI<br>
Sourcing from [Mouser](https://au.mouser.com/ProductDetail/Infineon-Technologies/CY62158ELL-45ZSXI?qs=k2piNBSag3%2FbPFa6bGnpTA%3D%3D)

<b>NOR Flash 512kB x 8</b><br>
Manufacturer - Microchip Technology<br>
Manufacturer Product Number - SST39SF040-55-4I-WHE<br>
Sourcing from [Mouser](https://au.mouser.com/ProductDetail/Microchip-Technology/SST39SF040-55-4I-WHE?qs=Ot24P6tC%2FQ4H1AkrSlmtNw%3D%3D)

<b>Power Supervision</b><br>
Manufacturer - Analog Devices / Maxim Integrated<br>
Manufacturer Product Number - DS1233DZ-5+<br>
Sourcing from [Mouser](https://au.mouser.com/ProductDetail/Analog-Devices-Maxim-Integrated/DS1233DZ-5%2b?qs=0Y9aZN%252BMVCXL0FvBiwYcRQ%3D%3D)

<b>Main Oscillator Crystal - 29.4912 MHz SMT</b><br>

<b>RTC Oscillator Crystal - 32.768 kHz SMT</b><br>

<b>Compact Flash Card Connector</b><br>
Manufacturer - ATTEND Technology<br>
Manufacturer Product Number - 101D-TAAA-R01<br>
Sourcing from [Digikey](https://www.digikey.co.uk/en/products/detail/attend-technology/101D-TAAA-R01/21284924)

<b>Grove I2C Connector</b><br>
Manufacturer - Seeed Studio<br>
Manufacturer Product Number - 114020164<br>
Sourcing from [Mouser](https://au.mouser.com/ProductDetail/Seeed-Studio/114020164?qs=7MVldsJ5Uayw%2FOfizq4F8w%3D%3D&mgh=1&vip=1&gclid=Cj0KCQjw0vWnBhC6ARIsAJpJM6ccTrkdiWTo3hYb-w90yz-BwvWj4Sbol2SJHF1jbXY-PI2Z1vYyWiAaAhruEALw_wcB)


### Port Pin Assignment

<div>
<table style="border: 2px solid #cccccc;">
<tbody>
<tr>
<th style="border: 1px solid #cccccc; padding: 6px;">Port A</th>
<th style="border: 1px solid #cccccc; padding: 6px;">Pin</th>
<th style="border: 1px solid #cccccc; padding: 6px;">Assignment</th>
<th style="border: 1px solid #cccccc; padding: 6px;">Comment</th>
</tr>
<tr>
<td style="border: 1px solid #cccccc; padding: 6px;"></td>
<td style="border: 1px solid #cccccc; padding: 6px;">0 - 7</td>
<td style="border: 1px solid #cccccc; padding: 6px;">IDE Data</td>
<td style="border: 1px solid #cccccc; padding: 6px;">8-Bit Compact Flash Interface</td>
</tr>
<tr>
<th style="border: 1px solid #cccccc; padding: 6px;">Port B</th>
<th style="border: 1px solid #cccccc; padding: 6px;">Pin</th>
<th style="border: 1px solid #cccccc; padding: 6px;">Assignment</th>
<th style="border: 1px solid #cccccc; padding: 6px;">Comment</th>
</tr>
<tr>
<td style="border: 1px solid #cccccc; padding: 6px;"></td>
<td style="border: 1px solid #cccccc; padding: 6px;">7</td>
<td style="border: 1px solid #cccccc; padding: 6px;">SPI CS1</td>
<td style="border: 1px solid #cccccc; padding: 6px;">Device Select for SPI Port</td>
</tr>
<tr>
<td style="border: 1px solid #cccccc; padding: 6px;"></td>
<td style="border: 1px solid #cccccc; padding: 6px;">6</td>
<td style="border: 1px solid #cccccc; padding: 6px;">SPI CS0</td>
<td style="border: 1px solid #cccccc; padding: 6px;">Device Select for SPI SD Card</td>
</tr>
<tr>
<td style="border: 1px solid #cccccc; padding: 6px;"></td>
<td style="border: 1px solid #cccccc; padding: 6px;">2 - 5</td>
<td style="border: 1px solid #cccccc; padding: 6px;">Input</td>
<td style="border: 1px solid #cccccc; padding: 6px;">Breakout Port</td>
</tr>
<tr>
<td style="border: 1px solid #cccccc; padding: 6px;"></td>
<td style="border: 1px solid #cccccc; padding: 6px;">1</td>
<td style="border: 1px solid #cccccc; padding: 6px;">SPI CD</td>
<td style="border: 1px solid #cccccc; padding: 6px;">Card Detect for SPI SD Card</td>
</tr>
<tr>
<td style="border: 1px solid #cccccc; padding: 6px;"></td>
<td style="border: 1px solid #cccccc; padding: 6px;">0</td>
<td style="border: 1px solid #cccccc; padding: 6px;">SPI CLK</td>
<td style="border: 1px solid #cccccc; padding: 6px;">Clock for SPI (CLK B)</td>
</tr>
<tr>
<th style="border: 1px solid #cccccc; padding: 6px;">Port C</th>
<th style="border: 1px solid #cccccc; padding: 6px;">Pin</th>
<th style="border: 1px solid #cccccc; padding: 6px;">Assignment</th>
<th style="border: 1px solid #cccccc; padding: 6px;">Comment</th>
</tr>
<tr>
<td style="border: 1px solid #cccccc; padding: 6px;"></td>
<td style="border: 1px solid #cccccc; padding: 6px;">7</td>
<td style="border: 1px solid #cccccc; padding: 6px;">RX A</td>
<td style="border: 1px solid #cccccc; padding: 6px;">Programming & Cold Boot Serial Port (LPT)</td>
</tr>
<tr>
<td style="border: 1px solid #cccccc; padding: 6px;"></td>
<td style="border: 1px solid #cccccc; padding: 6px;">6</td>
<td style="border: 1px solid #cccccc; padding: 6px;">TX A</td>
<td style="border: 1px solid #cccccc; padding: 6px;">Programming & Cold Boot Serial Port (LPT)</td>
</tr>
<tr>
<td style="border: 1px solid #cccccc; padding: 6px;"></td>
<td style="border: 1px solid #cccccc; padding: 6px;">5</td>
<td style="border: 1px solid #cccccc; padding: 6px;">RX B</td>
<td style="border: 1px solid #cccccc; padding: 6px;">SPI MISO </td>
</tr>
<tr>
<td style="border: 1px solid #cccccc; padding: 6px;"></td>
<td style="border: 1px solid #cccccc; padding: 6px;">4</td>
<td style="border: 1px solid #cccccc; padding: 6px;">TX B</td>
<td style="border: 1px solid #cccccc; padding: 6px;">SPI MOSI</td>
</tr>
<tr>
<td style="border: 1px solid #cccccc; padding: 6px;"></td>
<td style="border: 1px solid #cccccc; padding: 6px;">3</td>
<td style="border: 1px solid #cccccc; padding: 6px;">RX C</td>
<td style="border: 1px solid #cccccc; padding: 6px;">Asynchronous Serial C (Console)</td>
</tr>
<tr>
<td style="border: 1px solid #cccccc; padding: 6px;"></td>
<td style="border: 1px solid #cccccc; padding: 6px;">2</td>
<td style="border: 1px solid #cccccc; padding: 6px;">TX C</td>
<td style="border: 1px solid #cccccc; padding: 6px;">Asynchronous Serial C (Console)</td>
</tr>
<tr>
<td style="border: 1px solid #cccccc; padding: 6px;"></td>
<td style="border: 1px solid #cccccc; padding: 6px;">1</td>
<td style="border: 1px solid #cccccc; padding: 6px;">RX D</td>
<td style="border: 1px solid #cccccc; padding: 6px;">Asynchronous Serial D (TTY)</td>
</tr>
<tr>
<td style="border: 1px solid #cccccc; padding: 6px;"></td>
<td style="border: 1px solid #cccccc; padding: 6px;">0</td>
<td style="border: 1px solid #cccccc; padding: 6px;">TX D</td>
<td style="border: 1px solid #cccccc; padding: 6px;">Asynchronous Serial D (TTY)</td>
</tr>
<tr>
<th style="border: 1px solid #cccccc; padding: 6px;">Port D</th>
<th style="border: 1px solid #cccccc; padding: 6px;">Pin</th>
<th style="border: 1px solid #cccccc; padding: 6px;">Assignment</th>
<th style="border: 1px solid #cccccc; padding: 6px;">Comment</th>
</tr>
<tr>
<td style="border: 1px solid #cccccc; padding: 6px;"></td>
<td style="border: 1px solid #cccccc; padding: 6px;">7</td>
<td style="border: 1px solid #cccccc; padding: 6px;">DTR C</td>
<td style="border: 1px solid #cccccc; padding: 6px;">Asynchronous Serial C (Console)</td>
</tr>
<tr>
<td style="border: 1px solid #cccccc; padding: 6px;"></td>
<td style="border: 1px solid #cccccc; padding: 6px;">6</td>
<td style="border: 1px solid #cccccc; padding: 6px;">DTR D</td>
<td style="border: 1px solid #cccccc; padding: 6px;">Asynchronous Serial D (TTY)</td>
</tr>
<tr>
<td style="border: 1px solid #cccccc; padding: 6px;"></td>
<td style="border: 1px solid #cccccc; padding: 6px;">2 - 5</td>
<td style="border: 1px solid #cccccc; padding: 6px;">Input / Output</td>
<td style="border: 1px solid #cccccc; padding: 6px;">Breakout Port - Open Drain Capable</td>
</tr>
<tr>
<td style="border: 1px solid #cccccc; padding: 6px;"></td>
<td style="border: 1px solid #cccccc; padding: 6px;">1</td>
<td style="border: 1px solid #cccccc; padding: 6px;">I2C SDA</td>
<td style="border: 1px solid #cccccc; padding: 6px;">I2C Master Interface</td>
</tr>
<tr>
<td style="border: 1px solid #cccccc; padding: 6px;"></td>
<td style="border: 1px solid #cccccc; padding: 6px;">0</td>
<td style="border: 1px solid #cccccc; padding: 6px;">I2C SCL</td>
<td style="border: 1px solid #cccccc; padding: 6px;">I2C Master Interface</td>
</tr>
<tr>
<th style="border: 1px solid #cccccc; padding: 6px;">Port E</th>
<th style="border: 1px solid #cccccc; padding: 6px;">Pin</th>
<th style="border: 1px solid #cccccc; padding: 6px;">Assignment</th>
<th style="border: 1px solid #cccccc; padding: 6px;">Comment</th>
</tr>
<tr>
<td style="border: 1px solid #cccccc; padding: 6px;"></td>
<td style="border: 1px solid #cccccc; padding: 6px;">7</td>
<td style="border: 1px solid #cccccc; padding: 6px;">IDE WR</td>
<td style="border: 1px solid #cccccc; padding: 6px;">8-Bit Compact Flash Interface</td>
</tr>
<tr>
<td style="border: 1px solid #cccccc; padding: 6px;"></td>
<td style="border: 1px solid #cccccc; padding: 6px;">6</td>
<td style="border: 1px solid #cccccc; padding: 6px;">IDE RD</td>
<td style="border: 1px solid #cccccc; padding: 6px;">8-Bit Compact Flash Interface</td>
</tr>
<tr>
<td style="border: 1px solid #cccccc; padding: 6px;"></td>
<td style="border: 1px solid #cccccc; padding: 6px;">5</td>
<td style="border: 1px solid #cccccc; padding: 6px;">IDE CS1</td>
<td style="border: 1px solid #cccccc; padding: 6px;">8-Bit Compact Flash Interface</td>
</tr>
<tr>
<td style="border: 1px solid #cccccc; padding: 6px;"></td>
<td style="border: 1px solid #cccccc; padding: 6px;">4</td>
<td style="border: 1px solid #cccccc; padding: 6px;">IDE CS0</td>
<td style="border: 1px solid #cccccc; padding: 6px;">8-Bit Compact Flash Interface</td>
</tr>
<tr>
<td style="border: 1px solid #cccccc; padding: 6px;"></td>
<td style="border: 1px solid #cccccc; padding: 6px;">3</td>
<td style="border: 1px solid #cccccc; padding: 6px;">IDE A2</td>
<td style="border: 1px solid #cccccc; padding: 6px;">8-Bit Compact Flash Interface</td>
</tr>
<tr>
<td style="border: 1px solid #cccccc; padding: 6px;"></td>
<td style="border: 1px solid #cccccc; padding: 6px;">2</td>
<td style="border: 1px solid #cccccc; padding: 6px;">IDE A0</td>
<td style="border: 1px solid #cccccc; padding: 6px;">8-Bit Compact Flash Interface</td>
</tr>
<tr>
<td style="border: 1px solid #cccccc; padding: 6px;"></td>
<td style="border: 1px solid #cccccc; padding: 6px;">1</td>
<td style="border: 1px solid #cccccc; padding: 6px;">IDE A0</td>
<td style="border: 1px solid #cccccc; padding: 6px;">8-Bit Compact Flash Interface</td>
</tr>
<tr>
<td style="border: 1px solid #cccccc; padding: 6px;"></td>
<td style="border: 1px solid #cccccc; padding: 6px;">0</td>
<td style="border: 1px solid #cccccc; padding: 6px;">RC2014 INT</td>
<td style="border: 1px solid #cccccc; padding: 6px;">RC2014 Standard Bus INT</td>
</tr>
</tbody>
</table>
</div>


## Trade Marks

Rabbit® and RabbitCore® are registered trade marks of Digi International Inc.
