# JKFLIPFLOP-USING-IF-ELSE

**DATE :**  22/11/2024

**AIM:** 

To implement  JK flipflop using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

A JK Flip Flop is a type of digital memory circuit that stores a bit of information, with two inputs (J and K) and one output (Q). When J=0 and K=0, the flip flop remains in its current state; when J=1 and K=0, it sets to 1; when J=0 and K=1, it resets to 0; and when J=1 and K=1, it toggles its current state. This synchronous, edge-triggered, and sequential circuit is widely used in digital systems, counters, and registers, and its unique toggling feature makes it a fundamental building block of digital electronics.

**JK Flip-Flop**

JK flip-flop is the modified version of SR flip-flop. It operates with only positive clock transitions or negative clock transitions. The circuit diagram of JK flip-flop is shown in the following figure.

![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/a649c30b-232b-4558-b188-fd6c09845180)


This circuit has two inputs J & K and two outputs Qtt & Qtt’. The operation of JK flip-flop is similar to SR flip-flop. Here, we considered the inputs of SR flip-flop as S = J Qtt’ and R = KQtt in order to utilize the modified SR flip-flop for 4 combinations of inputs. The following table shows the state table of JK flip-flop.

![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/c4360742-e8a8-4937-b089-c46c0433f9a3)

 
Here, Qtt & Qt+1t+1 are present state & next state respectively. So, JK flip-flop can be used for one of these four functions such as Hold, Reset, Set & Complement of present state based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of JK flip-flop. Present Inputs Present State Next State
 
![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/6c275261-a6d5-4c37-a3a7-1e88ca11c4cd)

By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. Three variable K-Map for next state, Qt+1t+1 is shown in the following figure.
 
![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/5174f41b-0ce0-4329-a372-6d1943ea6673)

The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=JQ(t)′+K′Q(t)Q(t+1)=JQ(t)′+K′Q(t)

**Procedure**

1.Type the program in Quartus software.

2.Compile and run the program.

3.Generate the RTL schematic and save the logic diagram.

4.Create nodes for inputs and outputs to generate the timing diagram.

5.For different input combinations generate the timing diagram.

**PROGRAM**

Program for flipflops and verify its truth table in quartus using Verilog programming.

Developed by: DHANUSHKUMAR SIVAKUMAR

RegisterNumber: 24901013

```
module jk_ff(j, k, clk, rst, q);
  input j, k, clk, rst;
  output reg q;
  always @(posedge clk or posedge rst) begin
    if (rst)
      q <= 0; // Reset the flip-flop
    else if (j == 0 && k == 0)
      q <= q; // No change
    else if (j == 0 && k == 1)
      q <= 0; // Reset
    else if (j == 1 && k == 0)
      q <= 1; // Set
    else if (j == 1 && k == 1)
      q <= ~q; // Toggle
  end
 endmodule
```

**RTL DIAGRAM**

![image](https://github.com/user-attachments/assets/de61c14d-aa08-4ea6-bd3b-3feece21b234)


**TIMING WAVEFORM**

![image](https://github.com/user-attachments/assets/06350669-40df-41b6-bc82-9028a7857d54)


**RESULT :**

Thus the implementation of JK flipflop using verilog and validating their functionality using their functional tables is verified.
