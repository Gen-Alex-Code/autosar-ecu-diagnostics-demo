# Testing Strategy

## Purpose

Define the verification approach for the AUTOSAR ECU Diagnostics Demo project.

---

## Unit Testing

GoogleTest is the selected unit testing framework.

Current Status:

- GoogleTest integrated
- CTest integrated
- Placeholder test operational

Future unit tests will cover:

- DCM
- DEM
- RTE
- Diagnostic models

---

## Integration Testing

Integration testing will be introduced after core diagnostic functionality is implemented.

Planned coverage:

- Application → RTE
- RTE → DCM
- DCM → DEM
- End-to-end diagnostic flow

---

## Build Verification

The project shall be verified on:

- Linux (GCC)
- Windows (MSVC)

Verification includes:

- Configure
- Build
- Run
- Test execution

---

## Requirements Traceability

Requirements shall be linked to:

- Components
- Unit tests
- Integration tests

Reference:

`docs/requirements_traceability.md`

---

## Definition of Done

A feature is complete when:

- Requirements are implemented
- Unit tests pass
- Integration tests pass (when applicable)
- Documentation is updated

---

## Future Testing Improvements

Planned additions:

- DCM unit tests
- DEM unit tests
- RTE unit tests
- Integration tests
- CI execution
- Coverage reporting

---

## M2 Infrastructure Notes

GoogleTest is integrated using CMake FetchContent.

Tests can be enabled or disabled using:

```cmake
AUTOSAR_DEMO_ENABLE_TESTS
```

Default:

```text
ON
```