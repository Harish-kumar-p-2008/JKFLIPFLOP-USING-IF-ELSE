# JKFLIPFLOP-USING-IF-ELSE

**AIM:** 

To implement  JK flipflop using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

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

1. Define Inputs/Outputs: Inputs: J (Set), K (Reset), c1k (clock); Outputs: q, qbar (~q).
2. Initialization: Set q = 0 and qbar = 1 at the start of the simulation.
3. JK Flip-Flop Logic: On posedge c1k, compute q
4. Complementary Output: Update qbar = ~q to maintain complementarity.
5. Testbench: Simulate with combinations of J, K, and c1k to verify JK Flip-Flop functionality.

**PROGRAM**

/* Program for flipflops and verify its truth table in quartus using Verilog programming. 

Developed by: Harish Kumar P

RegisterNumber: 212225230095

```
module deexp4(j,k,clk,q,qbar);
input j,k,clk;
output q,qbar;
reg q;
assign qbar = ~q;
always @(posedge clk)
begin
    case ({j,k})
        2'b00: q <= q;      // No change
        2'b01: q <= 1'b0;   // Reset
        2'b10: q <= 1'b1;   // Set
        2'b11: q <= ~q;     // Toggle
    endcase
end
endmodule

```
*/

**RTL LOGIC FOR FLIPFLOPS**

![alt text](<Screenshot 2026-05-24 140534.png>)

**TIMING DIAGRAMS FOR FLIP FLOPS**

![alt text](<Screenshot 2026-05-24 140800.png>)

**RESULTS**
Thus the JK flipflop is implemented and verified.