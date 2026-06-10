# NASA cFS + Yamcs Satellite Simulator

A portfolio project demonstrating a simulated spacecraft command and telemetry system using **NASA Core Flight System (cFS)** and **Yamcs**.

This project focuses on extending a simulated spacecraft application with ground commands, housekeeping telemetry, and live verification through a Yamcs mission control interface.

## Project Overview

The goal of this project was to build and verify an end-to-end spacecraft command and telemetry flow:

```text
Ground Command
    ↓
Yamcs / Command Interface
    ↓
cFS Command Ingest
    ↓
SIM_SAT Application
    ↓
Housekeeping Telemetry
    ↓
Yamcs Telemetry Display
```

## Implemented Features

### Commands

The simulated spacecraft supports the following commands:

| Command          | Description                                      |
| ---------------- | ------------------------------------------------ |
| `NOOP`           | Verifies that the command path is alive          |
| `RESET_COUNTERS` | Resets command counters                          |
| `SET_MODE`       | Changes spacecraft mode between SAFE and NOMINAL |
| `SET_HEATER`     | Turns a simulated heater device ON or OFF        |
| `INJECT_FAULT`   | Simulates a spacecraft fault condition           |

### Housekeeping Telemetry

The project extends housekeeping telemetry with:

| Parameter             | Description                        |
| --------------------- | ---------------------------------- |
| `CommandCounter`      | Counts valid commands              |
| `CommandErrorCounter` | Counts invalid commands            |
| `AppRunCount`         | Tracks application execution count |
| `CurrentMode`         | Shows SAFE or NOMINAL mode         |
| `HeaterState`         | Shows heater OFF or ON             |
| `SimTemperatureC`     | Simulated temperature value        |
| `FaultActive`         | Indicates active simulated fault   |
| `FaultCount`          | Counts injected faults             |

## Verification Results

The system was verified through live Yamcs telemetry:

* `SET_MODE` successfully updated `CurrentMode`
* `SET_HEATER` successfully updated `HeaterState` and `SimTemperatureC`
* `INJECT_FAULT` successfully updated `FaultActive` and `FaultCount`
* Telemetry packet rate and data rate were confirmed in Yamcs
* XML/MDB byte-order issues were debugged and fixed for 16-bit telemetry values

## Technologies Used

* NASA Core Flight System (cFS)
* Yamcs Mission Control
* C programming
* XML / XTCE Mission Database
* Linux / Ubuntu WSL
* Bash terminal commands
* Git and GitHub
* Telemetry and command packet debugging

## Skills Demonstrated

* Embedded software development
* Flight software command handling
* Telemetry packet structure design
* Mission database configuration
* Debugging byte-order and packet decoding issues
* Linux-based development workflow
* System integration testing

## Video Demo Link

https://youtu.be/515nqVJrwqM

## Notes

This repository is presented as a portfolio-safe project summary. It documents the system design, implemented features, and verification results without exposing private or proprietary internship source code.

## Project Status

Completed core command and telemetry features:

* [x] Live housekeeping telemetry in Yamcs
* [x] NOOP command verification
* [x] RESET_COUNTERS command verification
* [x] SET_MODE command implementation
* [x] SET_HEATER command implementation
* [x] INJECT_FAULT command implementation
* [x] Yamcs telemetry decoding
* [x] Byte-order debugging and fixes

