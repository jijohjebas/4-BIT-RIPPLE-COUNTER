# 4-BIT-RIPPLE-COUNTER

**AIM:**

To implement  4 Bit Ripple Counter using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**4 Bit Ripple Counter**

A binary ripple counter consists of a series connection of complementing flip-flops (T or JK type), with the output of each flip-flop connected to the Clock Pulse input of the next higher-order flip-flop. The flip-flop holding the least significant bit receives the incoming count pulses. The diagram of a 4-bit binary ripple counter is shown in Fig. below.

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/cb4b74d4-31ab-4359-95d0-d22e67daba13)

In timing diagram Q0 is changing as soon as the negative edge of clock pulse is encountered, Q1 is changing when negative edge of Q0 is encountered(because Q0 is like clock pulse for second flip flop) and so on.

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/a573a7d6-014e-4e54-93e6-e2ac9530960b)

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/85e1958a-2fc1-49bb-9a9f-d58ccbf3663c)

**Procedure**

1.Open Quartus Prime and create a new project.

2.Create a new Verilog HDL File and enter the code for the 4-bit Ripple Counter.

3.Save the file with a .v extension and set it as the Top-Level Entity.

4.Compile the design using Processing → Start Compilation.

5.Verify that the compilation completes without errors.

6.Open Tools → Netlist Viewers → RTL Viewer to view the RTL schematic.

7.Create a waveform file and add the clock (clk) and output (q[3:0]) signals.

8.Apply a clock waveform and run the simulation.

9.Observe the timing diagram and verify that the counter counts from 0000 to 1111 in binary.

**PROGRAM**

 Developed by: 212225040156 
```
module bitripple(
   input  wire clk,      
   input  wire reset_n,  
   output reg  [3:0] q   
);


   always @(negedge clk or negedge reset_n) begin
       if (!reset_n)
           q[0] <= 1'b0;
       else
           q[0] <= ~q[0];
   end


   always @(negedge q[0] or negedge reset_n) begin
       if (!reset_n)
           q[1] <= 1'b0;
       else
           q[1] <= ~q[1];
   end


   always @(negedge q[1] or negedge reset_n) begin
       if (!reset_n)
           q[2] <= 1'b0;
       else
           q[2] <= ~q[2];
   end


   always @(negedge q[2] or negedge reset_n) begin
       if (!reset_n)
           q[3] <= 1'b0;
       else
           q[3] <= ~q[3];
   end

endmodule
```
**RTL LOGIC FOR 4 Bit Ripple Counter**
<img width="1077" height="598" alt="image" src="https://github.com/user-attachments/assets/14b310c2-5ac6-43d3-bd31-32e26028960e" />

**TIMING DIGRAMS FOR 4 Bit Ripple Counter**
<img width="1067" height="590" alt="image" src="https://github.com/user-attachments/assets/54526219-3bc5-4c9c-be1f-4006bcfeb08d" />

**RESULTS**

Thus we got the output.
