# VEE FLASH READ WRITE FORMAT #
# Introduction #
This Software Building Block (SBB) demonstrates the use of the Renesas RA Virtual EEPROM (VEE) Flash Driver using the Renesas Flexible Software Package (FSP). The SBB provides reusable middleware integration and reference application code that illustrates how to store, retrieve, maintain, and manage non-volatile data within Data Flash memory.

---

# 1. What Use Case Does This SBB Demonstrate?

This SBB demonstrates how an application can use the RA Virtual EEPROM middleware to store persistent configuration or application data in Data Flash memory without directly managing flash erase/write operations.

The demonstrated operations include:
- Writing multiple data types to different Virtual EEPROM Record IDs.
- Reading data back from Virtual EEPROM Record IDs.
- Formatting the Virtual EEPROM region.
- Querying Virtual EEPROM status.
- Performing a refresh operation.
- Displaying informational, success, and error messages through a serial terminal.

Typical customer use cases include:
- Production configuration storage
- Device settings persistence
- Calibration data storage
- Product serial number storage
- Event counters
- Runtime parameter retention across resets

# 2. What Does the SBB Core Code Do?

The core SBB implementation provides an abstraction layer on top of the Renesas VEE middleware.

It demonstrates write, read, status, format, and refresh operations while managing persistent data in Data Flash.

# 3. What Is Demo/Reference Application Code Versus Reusable SBB Code?

## Reference Application Code
- Menu handling
- User command processing
- Terminal interaction
- Printed status messages
- Demonstration data structures
- Example Record ID definitions

## Reusable SBB Code
- Virtual EEPROM initialization
- Read APIs
- Write APIs
- Status APIs
- Format APIs
- Refresh APIs
- Flash middleware integration
- Error handling

# 4. Which Public Functions Should I Look At First?

Recommended review order:
1. Initialization routine
2. Write operation functions
3. Read operation functions
4. Status functions
5. Format functions
6. Refresh functions

# 5. What Configuration Assumptions Were Made for the Reference Board?

## Terminal Configuration
- Baud Rate: 115200
- Data Bits: 8
- Parity: None
- Stop Bits: 1
- Flow Control: None

## Board-Specific Assumptions
### SBB-RA0L1
- Set J9 to pins 1-2.

### FPB-RA2E3
- Close E25, E28, E46, and E47.

### FPB-RA4E2
- Standard USB debug connection.

### FPB-RA6E2
- Standard USB debug connection.

### FPB-RA8E1
- Restore factory partition settings before execution.

# 6. What Must I Change For My Board?

Review and update as needed:
- Pin assignments
- UART configuration
- Clock settings
- Data Flash allocation
- VEE middleware configuration
- Task priorities and RTOS integration
- Application-specific record definitions

# 7. What Dependencies Does the SBB Have?

## Software Dependencies
- Renesas FSP
- Virtual EEPROM Middleware
- Flash Drivers

## Hardware Dependencies
- RA MCU Data Flash
- UART / Virtual COM Port
- USB Debug Interface

# 8. What Behavior and Performance Were Demonstrated?

Demonstrated behavior includes:
- Data storage and retrieval
- EEPROM formatting
- Status monitoring
- Refresh handling
- User-triggered and automatic refresh operations

No formal benchmark or performance measurements are provided.

# 9. What Files Are Safe to Modify?

## Safe to Modify
- Application logic
- Data structures
- Record definitions
- User interface/menu code

## Modify with Care
- FSP-generated configuration files
- Pin and clock configuration files

## Demo-Only Files
- Example menus
- Sample workflows
- Demonstration datasets

# 10. What Happens If I Modify the Source and Later Want to Adopt a Newer SBB Release?

Keep application customizations separate from reusable SBB code.

Recommended:
- Preserve standard SBB interfaces.
- Isolate product-specific logic.
- Minimize changes to core SBB modules.

This approach simplifies future upgrades and integration of bug fixes.

# Board Support Summary

| SBB | Board-Specific Requirement |
|-----|---------------------------|
| FPB-RA0L1 | J9 set to pins 1-2 |
| FPB-RA2E3 | Close E25, E28, E46, E47 |
| FPB-RA4E2 | Standard USB debug connection |
| FPB-RA6E2 | Standard USB debug connection |
| FPB-RA8E1 | Restore factory partition settings |
