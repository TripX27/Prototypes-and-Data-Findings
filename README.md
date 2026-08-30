# Project Shuddham: Portable Intuitive Purification System
A frugal, IoT-enabled, solar-powered suitcase water purification system designed to treat acidic mine drainage and heavy metal contamination in off-grid regions.

## Our Unique Solution
* Dual-chamber architecture physically isolates dry electronics from wet hydraulic filtration stages.
* Automated gating blocks dispensing if pH, TDS, or turbidity exceed safe thresholds.
* Multi-barrier purification integrates sediment, carbon, iron reduction, reverse osmosis, and UV-C disinfection.
* Real-time IoT monitoring tracks pH, TDS, turbidity, and temperature via low-power ESP32.
* Off-grid solar architecture utilizes a 12V LiFePO4 battery and MPPT solar charging.
* Dual outlets separate safe drinking permeate from reject brine for domestic reuse.

## Strategic Rationale: Suitcase Architecture
* Rapid tactical mobility enables sub-5-minute deployment in remote zones without civil infrastructure.
* Dual-chamber isolation separates wet hydraulics from sensitive IoT microcontrollers, preventing moisture risks.
* Anchoring heavy pumps to the base maintains a low center of gravity.
* A single self-contained footprint unifies filtration, automated sensors, batteries, and solar harvesting.

## Firmware Architecture & Control Logic
To ensure physical hardware safety loops are never delayed by network latency, the system utilizes a FreeRTOS dual-core architecture on the ESP32. 
* **Core 0:** Manages deterministic sensor data acquisition, digital filtering, temperature compensation, and physical actuator gating.
* **Core 1:** Dedicated entirely to asynchronous tasks, including I2C display rendering and cloud telemetry.
