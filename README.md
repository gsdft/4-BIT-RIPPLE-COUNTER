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

1.Connections are given as per circuit diagram.
2.Logical inputs are given as per circuit diagram.
3.Observe the output and verify the truth table.

**PROGRAM**

Program for 4 Bit Ripple Counter and verify its truth table in quartus using Verilog programming.

module tff(q, clk, rst);

  output reg q;
  
  input clk, rst;
  
  wire d;

  dff dff1(q, d, clk, rst);
  
  not not1(d, q);
  
endmodule

module ripplecounter(clk, rst, q);

  input clk, rst;
  
  output [3:0] q;
  
  wire [3:0] q;

  tff tf1(q[0], clk, rst);
  
  tff tf2(q[1], q[0], rst);
  
  tff tf3(q[2], q[1], rst);
  
  tff tf4(q[3], q[2], rst);
  
endmodule

**RTL LOGIC FOR 4 Bit Ripple Counter**

<img width="1915" height="773" alt="Screenshot 2025-10-26 192758" src="https://github.com/user-attachments/assets/6aedd742-6b4b-4052-9e14-e53ede95d0ee" />

**TIMING DIGRAMS FOR 4 Bit Ripple Counter**

**RESULTS**

The 4 bit ripple counter is verified.
