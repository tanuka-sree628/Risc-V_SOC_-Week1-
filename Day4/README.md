## Day 4: Gate-Level Simulation (GLS), Blocking vs. Non-Blocking in Verilog, and Synthesis-Simulation Mismatch

Welcome to Day 4 of the RTL Workshop!
During this session, we embark on three key topics of digital design: Gate-Level Simulation (GLS), Blocking vs. Non-Blocking Assignments, and Synthesis-Simulation Mismatch. These topics not only build design skills but also enable you to tackle real-world verification problems.

## All the lab works done are uploaded in the same folder.

## Table of Contents

Gate-Level Simulation (GLS)

Synthesis-Simulation Mismatch

Blocking vs. Non-Blocking Assignments in Verilog

Blocking Assignments

Non-Blocking Assignments

Comparison

Labs

Summary

## 1. Gate-Level Simulation (GLS)

GLS simulates a synthesized netlist to check for functionality and timing prior to physical design, ensuring that the RTL design, after synthesis, continues to function as intended.

Why GLS is Important:

Validation: Verifies RTL and gate-level equivalence.

Timing Verification: Simulates with actual delays to catch setup/hold violations.

Power & Testability: Verifies scan chains and power-aware options.

When Done:

Directly following synthesis.

Prior to physical implementation.

Types of GLS:

Functional GLS: Zero/Unit delay simulation for correctness purposes.

Timing GLS: Applies back-annotated timing to simulate real-world hardware behavior.

## 2. Synthesis-Simulation Mismatch

This mismatch occurs when RTL simulation results do not match post-synthesis or hardware results.

Causes:

Employment of non-synthesizable constructs (delays, initial blocks).

Incomplete coding styles (incomplete sensitivity lists, no else).

Tool-based interpretation differences.

Best Practice:
Always write code in a synthesizable, unambiguous manner to prevent mismatches between simulation and hardware.

## 3. Blocking vs. Non-Blocking Assignments in Verilog

Verilog has two assignment styles, and the appropriate one to use is critical for proper behavior.

3.1 Blocking (=)

Runs sequentially, sequentially.

Most often used in combinational logic.

Changes take effect immediately.

3.2 Non-Blocking (<=)

Ran in parallel, scheduled at timestep's end.

Standard for sequential logic (e.g., flip-flops).

Guarantees parallel updates to registers.

3.3 Quick Comparison
Blocking (=)\tNon-Blocking (<=)
Executes immediately\tExecutes at timestep's end
Sequential behavior\tParallel behavior
Apt for combinational logic\tApt for sequential logic
Prone to dependency problems\tAvoids dependency problems

## 4. Labs

Lab 1: 2:1 MUX implemented with ternary operator – shows straightforward combinational logic.

Lab 2: Synthesis of the MUX with Yosys.

Lab 3: Gate-Level Simulation of synthesized MUX.

Lab 4: "Bad MUX" example – shows coding errors like absence of sensitivity lists and incorrect use of non-blocking in combinational logic.

Lab 5: GLS of bad MUX – reflects mismatches and possible warnings.

Lab 6: Blocking assignment caveat – demonstrates dependency of results on assignment sequence.

Lab 7: Synthesis of the corrected caveat module – confirms optimized behavior.

## 5. Summary

Gate-Level Simulation: Confirms post-synthesis design correct, timing, and testable.

Synthesis-Simulation Mismatch: Avoided through clear, synthesizable coding practice.

Blocking vs. Non-Blocking: Blocking (=) for combinational logic; Non-blocking (<=) for sequential logic.

Labs: Hands-on experiments reinforced correct usage and revealed usual pitfalls.
