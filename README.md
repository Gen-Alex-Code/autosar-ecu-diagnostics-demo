# AUTOSAR ECU Diagnostics Demo

AUTOSAR-inspired ECU diagnostics simulator demonstrating modern C++17 software architecture, CMake-based builds, and automated testing.

## Build Instructions

### Configure

```bash
cmake -S . -B build
```

### Build

```bash
cmake --build build
```

## Run

### Linux

```bash
./build/autosar_ecu_diagnostics_demo
```

### Windows

```powershell
.\build\Debug\autosar_ecu_diagnostics_demo.exe
```

## Testing

GoogleTest is integrated through CMake FetchContent.

Tests are enabled by default.

### Configure and Build with Tests Enabled

```bash
cmake -S . -B build -DAUTOSAR_DEMO_ENABLE_TESTS=ON
cmake --build build
```

### Execute Tests

```bash
ctest --test-dir build
```

### Configure and Build without Tests

```bash
cmake -S . -B build -DAUTOSAR_DEMO_ENABLE_TESTS=OFF
cmake --build build
```

## Current Status

### Completed Milestones

* M0 — Repository & Documentation Foundation
* M1 — CMake Operational
* M2 — GoogleTest Operational

### Upcoming Milestones

* M3 — Diagnostic Models
* M4 — Diagnostic Event Manager (DEM)
* M5 — Runtime Environment (RTE)
* M6 — Diagnostic Communication Manager (DCM)
* M7 — Integration Testing
* M8 — Documentation Finalization
* M9 — v0.1 Release

## Project Constraints

Phase 1 intentionally excludes:

* STM32
* FreeRTOS
* Hardware dependencies
* Real AUTOSAR code generation
* CAN communication

The goal is to demonstrate AUTOSAR-inspired architecture, testing practices, and modern C++ engineering principles in a recruiter-visible repository.
