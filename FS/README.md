# Full Subtractor using Verilog

## Overview

A Full Subtractor is a combinational logic circuit that performs subtraction of three binary bits:

- Minuend (A)
- Subtrahend (B)
- Borrow Input (Bin)

It produces:

- Difference (Diff)
- Borrow Output (Bout)

---

## Truth Table

| A | B | Bin | Diff | Bout |
|---|---|-----|------|------|
|0|0|0|0|0|
|0|0|1|1|1|
|0|1|0|1|1|
|0|1|1|0|1|
|1|0|0|1|0|
|1|0|1|0|0|
|1|1|0|0|0|
|1|1|1|1|1|

---

## Verilog Equation

Difference:

```
Diff = A ^ B ^ Bin
```

Borrow:

```
Bout = (~A & B) | (~A & Bin) | (B & Bin)
```

---

## Files

- `full_subtractor.v` → Verilog design
- `full_subtractor_tb.v` → Testbench
- `simulation_output.png` → Waveform screenshot
- `README.md`

---

## Simulation

Compile:

```
iverilog -o full_subtractor full_subtractor.v full_subtractor_tb.v
```

Run:

```
vvp full_subtractor
```

Generate waveform (optional):

```
gtkwave waveform.vcd
```

---

## Expected Output

```
A B Bin | Diff Bout
-------------------
0 0 0 | 0 0
0 0 1 | 1 1
0 1 0 | 1 1
0 1 1 | 0 1
1 0 0 | 1 0
1 0 1 | 0 0
1 1 0 | 0 0
1 1 1 | 1 1
```

---

