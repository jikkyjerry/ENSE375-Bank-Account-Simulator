# Testing Plan

## 1. Test Environment
Java 25
Maven
JUnit 5

## 2. Unit Testing / TDD
- classes under test
- TDD process
- test naming convention - Osherove test naming convention [UnitOfWork_State_UnderTest_ExpectedBehavior]

## 3. Boundary Value Analysis - Robert
- function
- boundaries
- test requirements
- test cases
- results

## 4. Equivalence Class Testing - Robert
- partitions/classes
- representatives
- expected outputs
- results

## 5. Decision Table Testing - Ethan
- transferring funds example
- conditions
    - amount > 0
    - source != destination
    - source has enough balance to send the money
- actions
    - transfer processing
    - reject amount
    - reject because of insufficient funds
- decision table
- derived tests
- results

## 6. State Transition Testing - Ethan
- diagram
- transitions
- test requirements
- test cases
- results

## 7. Use Case Testing - Jeremiah
- use cases
- derived cases
- results

## 8. Path Testing - Robert
- chosen method
- source/CFG
- coverage criterion
- test requirements/test paths
- JUnit mapping
- results

## 9. Data Flow Testing - Robert
- same chosen function
- defs/uses
- DU pairs / DU paths
- coverage
- results

## 10. Integration Testing - Jeremiah
- selected units
- integration cases
- results

## 12. Test Summary - Ethan
Total tests
Passed
Failed
Known limitations