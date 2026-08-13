# Transmissive Pulse Oximeter

A ground-up, battery-powered clip-on pulse oximeter designed to measure blood oxygen saturation ($SpO_2$), heart rate (BPM), and body temperature in real-time. Built around an ESP32 microcontroller, the device features a custom-designed analog front end (AFE), a discrete SAR ADC, and an OLED display for live vitals and waveform monitoring.

## Repository Structure

* **/hardware** - Contains all PCB design files, schematics, and the Bill of Materials (BOM).
* **/software** - Complete ESP32 firmware source code. Includes the main application (`main.ino`), custom LED driving logic (`LEDDriver.h`), discrete ADC libraries (`cap_adc.h`, `ots_adc.h`), oxygen calculation algorithms, and OLED GUI drivers.
* **/simulations** - LTspice files used to model and verify the AFE, Power Manangement, and SAR ADC binary search behavior prior to physical layout.
* **/docs** - Project documentation, including the final project report (`Final_Report.pdf`) and the final presentation slides (`Final_Presentation.pdf`).

## System Highlights

* **Dual-Wavelength PPG**: Uses alternating Red and IR LEDs with ambient light subtraction to calculate precise oxygen saturation.
* **Custom Analog Front End**: In-house transimpedance amplification, filtering, and signal conditioning.
* **Thermal Compensation**: Integrated PTAT circuit and bandgap reference to prevent thermal drift and ensure measurement accuracy across different operating conditions. Additionally allows for real-time temperature measurement and compensation for the LEDs.
* **Discrete SAR ADC**: Custom analog-to-digital conversion using a 14-bit capacitive DAC/off-the-shelf DAC approach alongside an external comparator. 
* **Real-time OLED GUI**: On-device rendering of the PPG waveform, battery life, $SpO_2$ percentage, BPM, and temperature.

## Team
* **Andy Gonzalez** – Analog Front End, PTAT & Bandgap, Temperature Compensation, GUI
* **Adam Amir** – Power Management, Heart Rate Detection, $SpO_2$ Algorithm
* **Yash Bhagat** – SAR ADC, ADC Timing Conversion, Data Acquisition
* **Ben Ha** – Mechanical Design, LED Driver
