# Release Notes v0.1

## Release Objective

Establish an AUTOSAR-inspired ECU diagnostics simulator using modern C++17, CMake, and automated testing.

---

## Scope

Included:

- Repository foundation
- Documentation baseline
- Requirements baseline
- Traceability foundation
- Cross-platform CMake build
- GoogleTest infrastructure

Excluded:

- DCM implementation
- DEM implementation
- RTE implementation
- Diagnostic services
- Integration testing

---

## Added

### M1 — CMake Operational

- Root CMake configuration
- Cross-platform build support
- Desktop executable target
- Build verification on Linux and Windows

### M2 — GoogleTest Operational

- GoogleTest integration using FetchContent
- CTest integration
- Placeholder test executable
- Conditional test enablement using:

```cmake
AUTOSAR_DEMO_ENABLE_TESTS
```

---

## Changed

- Project now supports automated unit test execution.

---

## Known Limitations

- No diagnostic functionality implemented.
- No DCM module.
- No DEM module.
- No RTE module.
- No integration tests.

---

## Verification Summary

### M1 — CMake Operational

Status: PASS

Linux:

- Configure: PASS
- Build: PASS
- Run: PASS

Environment:

- Ubuntu 24.04.1
- GCC 13.3.0
- CMake 3.28.3

Windows:

- Configure: PASS
- Build: PASS
- Run: PASS

### M2 — GoogleTest Operational

Status: PASS

Linux:

- Tests Enabled: PASS
- Tests Disabled: PASS
- CTest Execution: PASS

Windows:

- Tests Enabled: PASS
- Tests Disabled: PASS
- CTest Execution: PASS

---

## Next Steps

M3 — Diagnostic Models