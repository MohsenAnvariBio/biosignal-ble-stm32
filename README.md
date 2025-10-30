# REAL-TIME EMBEDDED BIOSIGNAL MONITORING SYSTEM WITH BLE TRANSMISSION AND ANDROID VISUALIZATION

> Unified ECG + PPG (MAX30102) real-time acquisition & processing with BLE streaming to Android.

## Overview
This project implements a real-time biosignal acquisition system using an **STM32F446RE** Nucleo board.  
It acquires ECG (AD8232 analog front end) and PPG (MAX30102 via I²C and FIFO), applies digital filtering (HPF, LPF, moving average), performs peak detection and SpO₂/HR estimation, and streams processed signals in real time over **Bluetooth Low Energy (HM-10)** to an Android app for visualization.

Originally the system streamed over UART to a LabVIEW GUI. This version replaces USB-UART with **BLE (HM-10)** to stream data to a smartphone.

## Key features
- Synchronized ECG (ADC) and PPG (MAX30102 FIFO) acquisition.
- On-board digital signal processing: HPF, moving average smoothing, peak detection, SpO₂ and HR calculation.
- BLE streaming of processed ECG + PPG values to Android (HM-10 BLE module).
- Configurable sampling rate and BLE link parameters.
- Safe, paced transmissions to avoid BLE buffer overruns.

## Hardware
- STM32F446RE (Nucleo / custom board)
- AD8232 ECG front-end
- MAX30102 Pulse Oximeter (I²C)
- DSD TECH HM-10 BLE (Bluetooth 4.0 BLE) module — UART interface (VCC 3.3 V)
- Optional: FTDI/USB-TTL (3.3 V) for initial HM-10 configuration

## Software / Libraries
- STM32 HAL (CubeMX generated)
- HM-10 AT command helper
- Android application (https://github.com/MohsenAnvariBio/BioWave)


![Block Diagram](https://raw.githubusercontent.com/MohsenAnvariBio/biosignal-ble-stm32/1397e34d5e90fcb89109babe3ed14d124688d955/HealthMonitor/images/BlockDiagram.png)

![Curcuit](https://github.com/MohsenAnvariBio/biosignal-ble-stm32/blob/401778bdbd8b3f39392f361924014681f11b2fce/HealthMonitor/images/curcuit.png)

![App](https://github.com/MohsenAnvariBio/biosignal-ble-stm32/blob/401778bdbd8b3f39392f361924014681f11b2fce/HealthMonitor/images/App.png)

> Author: Mohsen Anvari<br>
> Email: s.mohsen.anvari.bio@gmail.com<br>
> Website: https://sites.google.com/view/mohsenanvari/home

