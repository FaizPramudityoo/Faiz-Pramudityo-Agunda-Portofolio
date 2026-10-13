# Hi, I'm Faiz Pramudityo Agunda

### Electronics & Embedded Systems | PCB Design | FPGA RTL | IoT & Data Platforms

Welcome to my engineering portfolio. I build systems that connect sensors, microcontrollers, digital logic, communication networks, and data platforms. My projects span PCB design, wireless sensing, FPGA-based data processing, and cloud data architecture.

This profile highlights four projects. The ESP32 gateway and FPGA parser are team projects; the gas and indoor air quality monitor is an academic thesis prototype. The linked repositories contain the implementation details.

## Technical Skills

| Area | Technologies and methods used in these projects |
| --- | --- |
| PCB & hardware | Schematic capture, component integration, PCB layout, power distribution, Altium Designer |
| Embedded systems | STM32F103C8T6, ESP32/ESP32-S3, sensor interfaces, PlatformIO, C/C++ |
| Communication & IoT | UART, LoRa SX1278, Wi-Fi, Ethernet, RS-485, CAN, Ubidots |
| FPGA & verification | Verilog HDL, finite state machines, NMEA parsing, checksum logic, simulation, AMD Vivado |
| Data platforms | Apache Airflow, MinIO, Dremio, Nessie, Metabase, Docker Compose |
| Supporting tools | Python serial communication, Git, test-data organization |

## Featured Projects

### 1. ESP32-S3 IoT Gateway PCB

**Focus:** PCB and hardware platform design

An ESP32-S3-based gateway board designed in Altium Designer as a flexible interface between sensors, industrial devices, and network services. The hardware design combines several communication options and expansion circuits on a four-layer PCB.

**System design**

- ESP32-S3 as the main controller.
- W5500 Ethernet interface and an LTE module interface for network connectivity.
- RS-485 and CAN interfaces for industrial communication.
- ADS7128 analog input expansion and TCA9534 digital I/O expansion.
- microSD interface for local storage.
- A dedicated 5 V to 3.3 V power regulation stage.

**Repository contents:** Altium project file, schematic sheets, PCB layout, and supporting design files.

**Tools:** Altium Designer, ESP32-S3

**Repository:** https://github.com/FaizPramudityoo/ESP32-Based-IoT-Gateaway

### 2. Combustion Gas and Indoor Air Quality Monitoring System

**Focus:** Wireless sensing and cloud monitoring · Undergraduate thesis prototype

A two-node system for observing combustion gas and indoor air quality trends in a residential setting. An STM32 transmitter collects sensor readings and sends them over 433 MHz LoRa. An ESP32 receiver displays the readings on an OLED and forwards them to Ubidots over Wi-Fi.

**Transmitter — STM32F103C8T6**

- Reads MQ-7 for CO response, MQ-135 for CO₂-equivalent air quality response, and DHT22 for temperature and humidity.
- Packages sensor readings and sends them through an SX1278 LoRa module.

**Receiver — ESP32**

- Receives and decodes LoRa packets.
- Presents readings locally on an OLED display.
- Sends readings to Ubidots for remote viewing.

**Repository contents:** PlatformIO firmware for both nodes, hardware design files, and a representative excerpt of LoRa communication test data.

**Tools:** STM32, ESP32, LoRa SX1278, PlatformIO, Ubidots

**Measurement scope:** The MQ-7 and MQ-135 were evaluated for response behavior and trends. Without calibrated reference instruments, the prototype does not establish absolute CO or CO₂ accuracy and is not a certified gas safety device. The raw test data in the repository is a partial excerpt; the thesis documents the broader results and limitations.

**Repository:** https://github.com/FaizPramudityoo/Combustion-Gas-IAQ-Monitoring-STM32-LoRa

### 3. FPGA NMEA Parser via UART

**Focus:** RTL design and serial data processing

A Verilog design for the Zybo Z7 that receives NMEA GGA sentences over UART at 115200 baud. A finite state machine recognizes the sentence structure, stores selected fields, checks the XOR checksum, and transmits fields from valid sentences back to a serial monitor.

**Implementation highlights**

- UART receiver and transmitter modules for the serial interface.
- FSM-based extraction of message ID, time, coordinates, hemisphere directions, GPS quality, satellite count, HDOP, and altitude.
- Checksum comparison against the two hexadecimal characters following the NMEA `*` delimiter.
- LED indicators for receive activity, checksum status, and a no-data timeout.
- A self-checking testbench covering valid, invalid, and lowercase hexadecimal checksums.

**Repository contents:** Verilog RTL, simulation testbench, and Zybo Z7 pin constraints.

**Tools:** Verilog HDL, AMD Vivado, UART, Python serial communication

**Verification scope:** The supplied testbench injects bytes into the parser internally. It verifies parsing and response logic, while the physical UART connection and full board behavior require separate hardware testing.

**Repository:** https://github.com/FaizPramudityoo/FPGA-Based-NMEA-Parser-UART

### 4. Data Lake Cloud Architecture

**Focus:** Data platform architecture and service integration

A Docker Compose-based environment for exploring how data storage, workflow orchestration, query processing, versioning, and visualization fit together in a data lake ecosystem. The project organizes multiple services into a reproducible local deployment rather than treating each tool as an isolated application.

**Architecture components**

- **Apache Airflow** defines and schedules data workflows through DAGs.
- **MinIO** provides S3-compatible object storage for data lake files.
- **Nessie** supplies versioned catalog functionality.
- **Dremio** provides a query and processing layer for data exploration.
- **Metabase** presents queries and results through analytics dashboards.

**Repository contents:** Docker Compose configuration, service Dockerfiles, an Airflow DAG directory, and setup instructions for the Metabase–Dremio driver. The documented setup also creates the required Docker networks before starting the services.

**Tools:** Docker Compose, Apache Airflow, MinIO, Nessie, Dremio, Metabase

**Project scope:** The repository documents the architecture and startup process. Specific pipeline outcomes, performance measurements, and production deployment are not claimed here.

**Repository:** https://github.com/FaizPramudityoo/datalake-cloud-architecture

## How I Approach a Project

I start by mapping the data path: where a measurement or message enters, how it is processed, and where the result is displayed, transmitted, or stored. I keep design files, implementation, and testing notes together so the scope and limitations of each project are visible.

## Contact

LinkedIn: [https://www.linkedin.com/in/faizpramudityoagunda/](https://www.linkedin.com/in/faizpramudityoagunda/)

Email: [Pramudityo32@gmail.com](mailto:Pramudityo32@gmail.com)
---

The ESP32 gateway and FPGA parser are team projects. The descriptions above summarize shared technical work; individual contributions can be added once specified.
