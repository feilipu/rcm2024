# RCM2024

This is a RabbitCore® Module using the R2000 microprocessor, designed for RC2014 Standard Bus specification.

The R2000 is substantially compatible with 8080 and Z80 processors, but implements enhanced instructions supporting high level languages such as C.

## Concept

The Rabbit® family of microprocessors is widely under-represented amongst hobby constructor, and very few (if any) "home made" RabbitCore® Modules have been developed. This RCM2024 is supposed to provide at least one option for hobby constructors and RC2014 enthusiasts.

The Rabbit microprocessor comes in many varieties, but the R2000 is the only version supporting 5V operation enabling it to work with the RC2014 Standard Bus. Therefore this RCM2024 is based on the R2000 Version C microprocessor.

The RCM2024 can be operated as a) a RC2014 CPU Module using standard RC2014 Backplane and accessory Modules, b) a RC2014 combined Backplane and microprocessor system, and c) as a standalone single board computer with its own serial, memory, and mass storage support.

The R2000 microprocessor has 5x 8-bit parallel ports, in addition to the usual Z80 bus interface, enabling a variety of interfaces to be integrated on to the RCM2024. These include a 8-bit Compact Flash IDE Port, a SPI interface supporting SD Cards and general SPI Master operation, an I2C interface, and up to 4x asynchronous and clocked serial interfaces.

## Hardware Specification

The RCM2024 is a double height RC2014 Module being 99.1mm wide x 99mm high, with one or two RC2014 Standard Bus connectors along one edge.

Standard features include.

- 245 kByte of NAND FLASH, using `WE0`, `OE0`, and `CS0`. This is the cold boot memory device.
- 1 MByte of Static RAM, using `WE0`, `OE0`, and `CS1`.

- Cold boot, and serial programming Port A using a USB interface (FTDI).
- 2 x asynchronous serial interfaces Port C and D with FTDI standard interfaces.

- SPI synchronous serial interface Port B with Grove / Sparkfun interface supporting external SPI Slave devices, and onboard SD Card.
- SD Card cage for optional FAT32 formatted mass storage.

- I2C interface (open drain) with Grove / Sparkfun interface supporting external I2C 5V or 3.3V Slave devices.

- Compact Flash Module 8-bit IDE Interface for optional FAT32 formatted mass storage.

- Also, the R2000 microprocessor has two Timers, and a Real Time clock capability, enabling time of day and interval timing.

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
<td style="border: 1px solid #cccccc; padding: 6px;"></td>
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
