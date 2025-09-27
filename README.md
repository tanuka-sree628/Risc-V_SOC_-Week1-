## DAY-1 INTRODUCTION TO VERILOG RTL DESIGN AND SYNTHESIS
THis is my Day 1 lab works done in the workshop conducted by VLSI System Design. 

Day 1 started with the introduction of working with the verilog files integrated in the library sky130

I learnt what is a simulator,Design and Testbench. I had a hands on lab session on working on simulating the 2 to 1 multiplexer

Welcome to the opening session of the RTL Workshop!
Today’s focus is on the basics of Verilog, using Icarus Verilog (iverilog) for simulation, and exploring Yosys for synthesis. Along the way, you’ll understand the role of simulators, testbenches, and how logic gets mapped into real hardware.

## Session Flow

Understanding the definitions of a simulator, design, and testbench

Introduction to Icarus Verilog and getting started

Lab exercise: Simulating a 2-to-1 multiplexer

Analyzing the Verilog design

Introduction to Yosys and technology libraries

Practical synthesis with Yosys

Key takeaways and summary

1. Simulator, Design, and Testbench

Simulator: A tool that simulates how your digital circuit functions, so you can verify correctness without real hardware.

Design: The Verilog description that defines the intended behavior.

Testbench: A simulation environment that drives test stimuli into your design and verifies the outputs, assisting in the validation of your logic.

2. Getting Started with Icarus Verilog

Icarus Verilog, commonly referred to as iverilog, is an open-source simulator that is commonly used in the practice of digital design. Its operation is straightforward: you supply both design and testbench, simulate the design, and then view the outputs on a waveform viewer like GTKWave.

3. Lab Focus: 2-to-1 Multiplexer

To put things into perspective, the initial working example is a 2:1 multiplexer. The implementation and its associated testbench are simulated with iverilog, and the output is seen in GTKWave to ensure that the logic is working as planned.

4. Design Walkthrough

The multiplexer has two data inputs and one select line. The output mirrors whatever input the select signal selects. When the select line is high, the output mirrors the second input; otherwise, it mirrors the first input.

5. Introduction to Yosys and Gate Libraries

Yosys is an open-source synthesis platform that converts Verilog RTL to a gate-level netlist. It also optimizes the design and maps it onto given technology cells available in standard cell libraries.

Why do libraries contain multiple versions of the same logic gates?

To strike a balance between speed, area, and power consumption

To accommodate high-speed gates for timing-critical paths

To employ compact or low-power gates for efficiency

To accommodate different drive strengths and maintain signal integrity

6. RTL-to-Gates with Yosys

Within the synthesis workflow, the Verilog design is loaded into Yosys first, then synthesized to a generic netlist. The design is next mapped onto technology cells of the selected library to produce a real gate-level netlist. Visualization of the synthesized schematic is also supported by Yosys.

7. Summary of Day 1

Understood the roles of simulators, designs, and testbenches

Ran a first digital simulation with Icarus Verilog and observed results in GTKWave

Reviewed how a simple 2:1 multiplexer operates

Explored what Yosys was used for and why technology libraries matter

Learned how a Verilog RTL description is translated into actual hardware gate
