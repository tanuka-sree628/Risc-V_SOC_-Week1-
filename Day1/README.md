## Day 1: Introduction to Verilog RTL Design & Synthesis

Welcome to the opening session of the RTL Workshop!
This is where your journey into digital design begins. Today’s focus is on the basics of Verilog, using Icarus Verilog (iverilog) for simulation, and exploring Yosys for synthesis. Along the way, you’ll understand the role of simulators, testbenches, and how logic gets mapped into real hardware.

## All the lab works doen are uploaded in the same folder

## Session Flow

Learning what a simulator, design, and testbench are

Initial experience with Icarus Verilog

Lab exercise: simulation of a 2-to-1 multiplexer

Dissecting the Verilog design

Yosys and technology library introduction

Hands-on synthesis process with Yosys

## Key takeaways and summary

## 1. Simulator, Design, and Testbench

Simulator: A program that simulates how your digital circuit operates, enabling you to verify correctness without hardware.

Design: The Verilog specification describing the desired behavior.

Testbench: A virtual world where you apply test signals to your design and verify the outputs, validating your logic.

## 2. Getting Started with Icarus Verilog

Icarus Verilog, or commonly referred to as iverilog, is an open-source digital design practice simulator. Its process is easy: you supply both design and testbench, simulate, and then view the outputs in a waveform viewer like GTKWave.

## 3. Lab Focus: 2-to-1 Multiplexer

For concreteness, the first real-world example is a 2:1 multiplexer. The design and its associated testbench are simulated with iverilog and the output is watched in GTKWave to verify that the logic acts correctly.

## 4. Design Walkthrough

The multiplexer has two data inputs and a single select line. The output mirrors whatever input the select signal picks. If the select line is high, the output tracks the second input; if not, it tracks the first input.

## 5. Introduction to Yosys and Gate Libraries

Yosys is an open-source synthesis environment that maps Verilog RTL to a gate-level netlist. It may optimize the design and map it onto individual technology cells available in standard cell libraries.

Why do libraries have multiple versions of identical logic gates?

To tradeoff speed, area, and power dissipation

To reserve high-performance gates for timing-critical paths

To utilize compact or low-power gates for optimization

To support multiple drive strengths and maintain signal integrity

## 6. RTL-to-Gates with Yosys

In the synthesis process, the Verilog design is loaded into Yosys first, then synthesized into a generic netlist. The design is then mapped to technology cells from the selected library to form a true gate-level netlist. Yosys also supports visualization of the synthesized schematic.

##  7. Summary of Day 1

Understood the purposes of simulators, designs, and testbenches

Ran a first digital simulation with Icarus Verilog and displayed results in GTKWave

Used a basic 2:1 multiplexer to see how it works

Realized what Yosys is used for and why technology libraries are needed

Discovered how a Verilog RTL description is synthesized into actual hardware gates
