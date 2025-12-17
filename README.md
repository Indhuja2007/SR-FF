# SR-FF
AIM:

To implement SR flipflop using verilog and validating their functionality using their functional tables

SOFTWARE REQUIRED: Quartus prime

THEORY

SR Flip-Flop SR flip-flop operates with only positive clock transitions or negative clock transitions. Whereas, SR latch operates with enable signal. The circuit diagram of SR flip-flop is shown in the following figure.

1
This circuit has two inputs S & R and two outputs Qtt & Qtt’. The operation of SR flipflop is similar to SR Latch. But, this flip-flop affects the outputs only when positive transition of the clock signal is applied instead of active enable. The following table shows the state table of SR flip-flop.

2
Here, Qtt & Qt+1t+1 are present state & next state respectively. So, SR flip-flop can be used for one of these three functions such as Hold, Reset & Set based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of SR flip-flop. Present Inputs Present State Next State

3
By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. The three variable K-Map for next state, Qt+1t+1 is shown in the following figure.

4
The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=S+R′Q(t)Q(t+1)=S+R′Q(t)

PROGRAM:

module sr_flip_flop (
   input  wire clk, rst, S, R,
   output reg  Q
);
   always @(posedge clk) begin
       if (rst)
           Q <= 1'b0;         // Reset
       else begin
           case ({S,R})
               2'b00: Q <= Q;     // No change
               2'b01: Q <= 1'b0;  // Reset
               2'b10: Q <= 1'b1;  // Set
               2'b11: Q <= 1'bx;  // Invalid
           endcase
       end
   end
endmodule

RTL LOGIC FOR FLIPFLOP:
<img width="1920" height="1080" alt="SR_FF" src="https://github.com/user-attachments/assets/98b3434b-a3b8-4094-8604-0704cc50c7de" />


wave form sr flip flop :

[SR_WAVE.pdf](https://github.com/user-attachments/files/24207867/SR_WAVE.pdf)




NAME: INDHUJA K

REF NO: 25018219

RESULT: Thus the SR flipflop is implemented and verified.
