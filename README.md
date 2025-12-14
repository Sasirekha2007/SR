AIM:

To implement SR flipflop using verilog and validating their functionality using their functional tables

SOFTWARE REQUIRED:

Quartus prime

THEORY


<img width="715" height="446" alt="Screenshot 2025-12-14 162626" src="https://github.com/user-attachments/assets/77b1e98d-79e5-4883-b34e-3c7e492a93bd" />

SR Flip-Flop SR flip-flop operates with only positive clock transitions or negative clock transitions. 
eas, SR latch operates with enable signal. The circuit diagram of SR flip-flop is shown in the following figure.

image



<img width="798" height="421" alt="Screenshot 2025-12-14 162641" src="https://github.com/user-attachments/assets/7f80bdf0-0cbb-44ee-b80a-fd0719e9af39" />

This circuit has two inputs S & R and two outputs Qtt & Qtt’. The operation of SR flipflop is similar to SR Latch. But, this flip-flop affects the outputs only when positive transition of the clock signal is applied instead of active enable. The following table shows the state table of SR flip-flop.



<img width="658" height="549" alt="Screenshot 2025-12-14 162656" src="https://github.com/user-attachments/assets/c0285b6c-8265-4fa0-ae4a-299abc2edb5a" />


Here, Qtt & Qt+1t+1 are present state & next state respectively. So, SR flip-flop can be used for one of these three functions such as Hold, Reset & Set based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of SR flip-flop. Present Inputs Present State Next State

image

By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. The three variable K-Map for next state, Qt+1t+1 is shown in the following figure.

image<img width="387" height="262" alt="Screenshot 2025-12-14 162139" src="https://github.com/user-attachments/assets/bc919645-46a3-49d2-80c2-3f09d5a49db2" />

The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=S+R′Q(t)Q(t+1)=S+R′Q(t)


PROGRAM
module SR (
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



 Developed by:B.SASIREKHA
 
 RegisterNumber: 25015734

RTL LOGIC FOR FLIPFLOPS

TIMING DIGRAMS FOR FLIP FLOPS

RESULTS
