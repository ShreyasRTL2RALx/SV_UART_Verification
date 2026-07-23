# SV_UART_Verification
Self-checking UART Verification Environment using System Verilog with OOP, Mailboxes, Events, Virtual Interface, and Scoreboard.

## Features

- UART Transmitter Verification
- UART Receiver Verification
- Constrained Random Test Generation
- Self-checking Scoreboard
- Functional Transaction Flow
- Mailbox-based Communication
- Event Synchronization
- Virtual Interface
- Object-Oriented Testbench

---
## Verification Architecture

```
                +----------------+
                |   Generator    |
                +----------------+
                        |
                        | Transaction
                        v
                +----------------+
                |    Driver      |
                +----------------+
                        |
                        | Interface
                        v
                +----------------+
                |    UART DUT    |
                +----------------+
                        |
                        v
                +----------------+
                |    Monitor     |
                +----------------+
                        |
                        v
                +----------------+
                |  Scoreboard    |
                +----------------+
```

---

## Testbench Components

### Transaction

- Stores UART transaction information
- Randomizes operation type
- Randomizes transmitted data
- Supports deep copy using copy() function

---

### Generator

- Generates constrained-random transactions
- Sends transactions to Driver
- Waits for Driver and Scoreboard completion before generating the next transaction

---

### Driver

- Drives randomized stimulus to DUT
- Performs UART Write operation
- Performs UART Read operation
- Sends expected data to Scoreboard

---

### Monitor

- Passively observes DUT signals
- Captures transmitted and received data
- Sends actual DUT output to Scoreboard

---

### Scoreboard

- Compares expected data from Driver with actual data from Monitor
- Reports PASS/FAIL automatically

---

### Environment

- Instantiates all verification components
- Connects mailboxes
- Connects events
- Executes Reset → Test → Finish sequence

---

## Verification Flow

1. Apply Reset
2. Generator creates random transaction
3. Driver drives transaction to UART
4. UART processes transaction
5. Monitor captures DUT output
6. Scoreboard compares expected and actual data
7. PASS/FAIL reported automatically

---
## Technologies Used

- SystemVerilog
- Object-Oriented Programming
- Mailbox Communication
- Events
- Virtual Interface
- Randomization
- Self-checking Testbench

---

## Simulation Tool

- Siemens QuestaSim 2025.2
- EDA Playground

---

## Sample Simulation Output

## Learning Outcomes

Through this project, I learned:

- SystemVerilog OOP
- Transaction-based verification
- Driver-Monitor architecture
- Mailbox communication
- Event synchronization
- Virtual interfaces
- Self-checking verification methodology
- UART protocol verification


