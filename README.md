# Dual-port-RAM

module dual_port_ram: This line declares the module named dual_port_ram.
The module has seven inputs and two outputs:
input [7:0] data_a and input [7:0] data_b: These are the 8-bit data inputs for the two ports.
input [5:0] addr_a and input [5:0] addr_b: These are the 6-bit address inputs for the two ports.
input we_a and input we_b: These are the write enable signals for the two ports. When we_a or we_b is high, data is written to the RAM.
input clk: This is the clock signal.
output reg [7:0] q_a and output reg [7:0] q_b: These are the 8-bit data outputs for the two ports.
reg [7:0] ram [63:0]: This declares a 64x8-bit RAM array.
There are two always @(posedge clk) blocks, one for each port. Inside these blocks:
If the write enable (we_a or we_b) signal is high, the data is written to the RAM at the specified address.
Otherwise, the data at the specified address is assigned to the output q_a or q_b.

