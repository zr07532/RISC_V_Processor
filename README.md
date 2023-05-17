# RISC_V_Processor
Computer Architecture Project: Pipelined Processor and Bubble Sort Implementation

In our Computer Architecture course, we undertook an exciting project where we designed and implemented a 5-stage pipelined processor capable of executing the bubble sort algorithm. Our objective was to enhance the performance of a single-cycle processor by introducing pipelining with hazard detection. We also compared the execution time of our pipelined processor with a RISC-V processor.

Methodology:

Bubble Sort Algorithm: We first validated the bubble sort algorithm in assembly language and modified the single-cycle processor to execute the sorting algorithm.
Pipelined Processor: Next, we transformed our single-cycle processor into a pipelined processor and verified the successful execution of each instruction in isolation.
Hazard Detection: We incorporated hazard detection modules, including forwarding unit, hazard detection, and triple mux, to detect and handle data hazards during the execution of the bubble sort algorithm.
Performance Comparison: Finally, we compared the execution time of the bubble sort algorithm on our single-cycle processor with the RISC-V processor.

Single Cycle Processor:
Using the Venus simulator (venus.kvakil.me/), we obtained machine code for the sorting algorithm instructions. We modified the bubble sort algorithm to accommodate the simulator's limitations and included branch instruction detection in the single-cycle processor.

Pipelined Processor:
Expanding on the single-cycle processor, we added IFID, IDEX, EXMEM, and MEMWB modules for a five-stage pipeline. Rigorous testing confirmed the functionality using two instructions independently. We implemented forwarding for correct register forwarding in each cycle.

Hazard Detection:
We developed modules for the forwarding unit, hazard detection, and triple mux to handle data hazards. The hazard detection module identifies hazards caused by reading from registers written by preceding instructions. Detected hazards trigger a stall by setting the output to 0. The forwarding unit determines dependencies between instructions and forwards data accordingly. The resulting data is sent to two muxes for ALU selection.
