# LFSR-Tools: Linear Feedback/Feedforward Shift Registers in Python

Designed to test LFSR Mathematically for verification of Verilog Design.
This package provides an abstract base class for Linear Feedback/Feedforward Shift Registers (LFSRs) and two concrete implementations:  
- **Fibonacci LFSR** (linear feedback)
- **Galois LFSR** (linear feedforward)

Supports:
- Custom characteristic polynomials
- Arbitrary initial states
- State table generation
- Algebraic polynomial form
- Bitwise access to register positions

## Installation

Clone the repo and place the module in your project:

```bash
git clone https://github.com/anubhav-narayan/lfsr.git
```

Use `poetry`

```bash
poetry install
```

## Usage

General Usage
```python3
from lfsr_tools import Galois_LFSR as LFSR

lfsr = LFSR(poly=0b10011, state=0b1010)

# Get full cycle of states
print(lfsr.state_table)
# Access bits
print(lfsr[0]) # Read a bit
lfsr[4] = lfsr[3] & 0b1 # Write a bit
```
Usage with CoCoTB
```python3
from lfsr_tools import Galois_LFSR as LFSR
from cocotb import BinaryValue

lfsr = LFSR(poly=0b10011, state=0b1010)

# Assign state
dut.lfsr.value = BinaryValue(lfsr.state, n_bits=lfsr.field_order)
```

Extend the `LFSR` Abstract Class to create custom Feedback/Feedforward Shift Registers. Just override the `round` function.
