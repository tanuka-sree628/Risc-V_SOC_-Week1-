## Day 2: Timing Libraries, Synthesis Strategies, and Flip-Flop Coding

Hello and welcome to Day 2 of the RTL Workshop!
Today, we are going to work on three prime areas that are crucial for designing for real-world scenarios:
All the lab screenshots are uploaded in the same folder.

Gaining an understanding of the timing libraries included in open-source PDKs.

Learning about the differences between hierarchical and flat synthesis techniques.

Acquiring efficient flip-flop coding styles for sound RTL design.

## Session Flow

Timing Libraries and the SKY130 PDK

Hierarchical vs. Flattened Synthesis

Efficient Coding for Flip-Flops

Simulation and Synthesis Flow

## Key Takeaways

1. Timing Libraries and the SKY130 PDK

The SKY130 Process Design Kit (PDK) is an open-source version based on SkyWater's 130nm CMOS technology. It is an open-source library that offers models and libraries that reflect how circuits behave under various process, voltage, and temperature (PVT) conditions.

Library name break down: sky130_fd_sc_hd__tt_025C_1v80:
tt → Typical process corner (typical manufacturing conditions).

025C → Temperature setting at 25°C.

1v80 → Nominal core voltage of 1.8V.

This naming informs you precisely what environment the library emulates—vital to correct timing and synthesis. 

Upon opening the .lib file, you will see delay, power, and function information for every standard cell. This forms the basis of technology mapping throughout synthesis.

2. Hierarchical vs. Flattened Synthesis
Hierarchical Synthesis

Maintains the original RTL structure.

Each module is synthesized separately, with preservation of the design boundaries.

Advantages: Quicker for large systems, easier debugging, modular for integration and reuse.

Disadvantages: Cross-module optimization is constrained, reports might require additional processing.

Flattened Synthesis

Combinations all modules into one design with no hierarchy.

The whole circuit is optimized as an aggregate block.

Advantages: Supports powerful, whole-design optimizations and in some cases simpler final netlists.

Disadvantages: Increases runtime and memory, and makes debugging harder from loss of structure.

Key Differences
Aspect	Hierarchical Synthesis	Flattened Synthesis
Hierarchy	Preserved	Collapsed
Optimization
Module-level only
Full design scope
Runtime
Faster for large designs
Slower for big circuits
Debugging
Easier (maps to RTL)
Harder
Output Netlist
Structured, modular
Single, complex block
Use Case
Analysis, modular design
Maximum optimization
3. Efficient Flip-Flop Coding Styles

Flip-flops are the core of sequential logic and are used for data storage over clock cycles. RTL coding style is highly responsible for proper synthesis and expected behavior.

Asynchronous Reset Flip-Flop

Reset immediately overrides the clock.

Output gets driven low as soon as reset is asserted.

Asynchronous Set Flip-Flop

Like reset, but the output is driven high rather.

Good for setting up registers to logic 1.

Synchronous Reset Flip-Flop

Reset occurs only on the active clock transition.

Guarantees reset synchronization with regular clocking activity.

Synchronous vs asynchronous resets depend on design needs and target technology.

4. Simulation and Synthesis Flow

Simulation
Designs are checked with Icarus Verilog by compiling the testbench and design. Waveforms are checked in GTKWave to ensure behavior.

Synthesis
The design is converted to a gate-level netlist with Yosys. The timing library is used to guide flip-flop mapping and logic cell mapping. The design can be viewed after synthesis at the gate level to observe what RTL structures map into actual hardware cells.

5. Key Learnings

✅ Realized the place of timing libraries in modeling process, voltage, and temperature swings.
✅ Understood the contrast between hierarchical and flattened synthesis methodologies, including their trade-offs.
✅ Went through optimal coding techniques for flip-flops with diverse reset/set behaviors.
✅ Saw the entire flow: simulation using Icarus Verilog and synthesis using Yosys.
