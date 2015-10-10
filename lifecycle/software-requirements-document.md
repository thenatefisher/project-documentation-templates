# Software Requirements Document

## Introduction

This document is **complete** when all of the following criteria are met:
- [ ] Definition of the software responses to all conceivable inputs (valid and invalid) in all conceivable situations.
- [ ] All requirements specified in the system requirements document have been addressed. 
- [ ] All TBD's are commented with description of the blocking items and assigned to a responsible party for resolution.

### Purpose

- Enable service provider to satisfy the customer. This document establishes a basis for agreement, between customer and service provider, on what the resulting software product should do. 
- Reduce development effort by mitigating churn.
- Provide a basis for cost estimation.
- Provide a baseline for V&V.
- Failitate transfer of software development effort and usage to other parties.
- Serve as a basis for modification.

### References

- System Requirements Document
- IEEE 830: Recommomended Practice for Software Requirements Specifications
- IETF RFC 2119: Key words for use in RFCs to Indicate Requirement Levels

## Overview

> **NOTE:** A block diagram might be helpful showing major components of the larger system. 

<< Brief description of the system to be implemented. >>

## Specific Requirements

> **NOTE:** A good requirement is verifiable, unambiguous and traceable to a system requirement.   

> **NOTE:** Take care to not over-constrain the system. For example, avoid creating requirements becuase they sound like good practice, only add them if requested by the customer or mandated to fulfill a system requirement.

> **NOTE:** Each requirement should be tagged with an identifier, to be traced to system requirements and code units. This allows for impact analysis and coverage analysis. During initial development, it may be easier to simply add SW_XXXXXX to requirements for backfill as review time nears.

### External Interfaces

> **NOTE:** This section could also be broken up into user interface, machine-machine interface, software component interface  

> **NOTE:** For complex interfaces, especially a machine interface, the details should probably be captured in its own Interface Control Document.

**SW_000100** All character inputs SHALL be interpreted with UTF-8 encoding. 

**SW_000200** All text input fields SHALL be marked as invalid if they do not consist only of characters a-z or A-Z. 

**SW_000300** The device SHALL expose an interface which commands the processor to enter the reset vector within 2 seconds of the request received, 75% of the time.

### System Features

> **NOTE:** Validity     checks, sequence of operations, response to various inputs

**SW_000400** Upon reset and before the operating system scheduler is started, the device SHALL allocate IMU_SENSOR_INSTANCES_COUNT of the IMU driver and initialize all member data objects to default values. 

**SW_000500** The IMU driver instance MAY expose any of the following data items:
- XYZ Acceleration Raw Value
- XYZ Angular Rate Raw Value
- XYZ Position Estimate
- Quaternion Orientation Estimate

**SW_000600** All widget data objects within the system SHALL have a unique identification number assocatied.

**SW_000700** If the user selects a beverage option with a valid amount of money in the session coin counter, the session module SHALL signal a dispense instruction to the actuation module. 

**SW_000900** The air sensor module SHALL signal changes to the user interface layer when disturbances are in excess of 2ppm.

### Performance Requirements

**SW_000800** The display refresh rate SHALL never be less than 100Hz. 

**SW_001000** New air sensor data SHALL be recorded in the database within 10ns of the converted input read from the ADC. 

**SW_001100** Unintentional resets SHALL NOT occur more than once in 100 operating hours.

**SW_001300** The device SHALL recover from all unintentional reset within 200 milliseconds of the reset event.

> **NOTE:** TBDs can be used as placeholders, however they should be accompanied by a description and assigned to an individual for resolution.

**SW_001600** Maximum RAM usage of the implementation SHALL not exceed a value of TBD. *TBD is currently blocked by processor selection excercise. This TBD is assigned to George.*

### Software System Attributes

> **NOTE:** Reliability, availability, maintainability, security, portability

**SW_001200** All source code SHALL be valid per the MISRA-C standard.

**SW_001500** All source code SHALL be formatted per the stylistic guidlines specified in Appendix A.

**SW_001300** Software products SHALL be portable to the following processor instruction sets: ARM, x86, PowerPC.

**SW_001400** Source code SHALL not contain any functions with a cyclomatic complexity greater than 5.

### Constraints

> **NOTE:** Regulatory policy, certifications, implementation details, specific technology requirements, communication protocols

**SW_002000** Software SHALL be written in COBOL.

**SW_002000** This device SHALL be compliant with FCC Guidline XXX.

**SW_002000** All requirements defined for this device SHALL be satisfied by software whill will execute on the ZR123 microprocessor.

## Use Cases

All use cases are itemized in the use-cases directory.

## Glossary

|Item|Definition|
|---|---|
|IMU_SENSOR_INSTANCES_COUNT|2|

