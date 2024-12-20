### SYNCHRONOUS-UP-COUNTER

**AIM:**

To implement 4 bit synchronous up counter and validate functionality.

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**4 bit synchronous UP Counter**

If we enable each J-K flip-flop to toggle based on whether or not all preceding flip-flop outputs (Q) are “high,” we can obtain the same counting sequence as the asynchronous circuit without the ripple effect, since each flip-flop in this circuit will be clocked at exactly the same time:

![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/d5db3fa0-e413-404c-b80e-b2f39d82e7e8)


![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/52cb61eb-d04b-442d-810c-31185a68410b)

Each flip-flop in this circuit will be clocked at exactly the same time.
The result is a four-bit synchronous “up” counter. Each of the higher-order flip-flops are made ready to toggle (both J and K inputs “high”) if the Q outputs of all previous flip-flops are “high.”
Otherwise, the J and K inputs for that flip-flop will both be “low,” placing it into the “latch” mode where it will maintain its present output state at the next clock pulse.
Since the first (LSB) flip-flop needs to toggle at every clock pulse, its J and K inputs are connected to Vcc or Vdd, where they will be “high” all the time.
The next flip-flop need only “recognize” that the first flip-flop’s Q output is high to be made ready to toggle, so no AND gate is needed.
However, the remaining flip-flops should be made ready to toggle only when all lower-order output bits are “high,” thus the need for AND gates.

**Procedure**

 1.Type the program in Quartus software.
 
 2.Compile and run the program.
 
 3.Generate the RTL schematic and save the logic diagram.
 
 4.Create nodes for inputs and outputs to generate the timing diagram.
 
 5.For different input combinations generate the timing diagram

**PROGRAM**

```
module syncntr(clk, rst, q); 
    input clk; 
    input rst; 
    output [3:0]q; 
  reg [3:0]q; 
  reg [3:0]x=0; 
  always @ (posedge(clk) or posedge(rst)) 
  begin 
  if (rst==1'b1) 
  begin 
  q=4'b0; 
  end 
  else  
  begin 
  x=x+1'b1; 
  end 
  q=x; 
  end 
  endmodule 
```

Developed by:Shyamkumar.S

RegisterNumber:24001160

**RTL LOGIC UP COUNTER**

![Sync1](https://github.com/user-attachments/assets/08a36f4d-7d7b-4c46-9551-38596dabf24b)


**TIMING DIAGRAM FOR IP COUNTER**

![Sync1 1](https://github.com/user-attachments/assets/51b9b689-88be-4b49-9c2c-9cead3b15351)


**TRUTH TABLE**

![truth table](https://github.com/user-attachments/assets/dbbcbf32-d861-4364-8f0e-9224b84fbd4b)

**RESULTS**

Hence 4 bit synchronous up counter is verified,using Verilog programming.
