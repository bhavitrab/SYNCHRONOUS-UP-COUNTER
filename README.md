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
1.Understand: All flip-flops are triggered by the same clock (synchronous operation).

2.Define module with inputs clk, rstn and output out[3:0].

3.Use always block triggered on the posedge of clk.

4.Apply reset: if rstn = 0, set output to 0000.

5.Count up: else increment output by 1 on every clock pulse.

6.Simulate: Apply clock and reset signals to test the counter.

7.Verify: Check that output counts 0000 → 1111 → 0000 repeatedly.

**PROGRAM**

 Program for flipflops and verify its truth table in quartus using Verilog programming. 
 ```
module ex11(out,clk,rst); 
input clk,rst; 
output reg [3:0]out; 
always @ (posedge clk) 
begin 
   if(rst) 
     out<=0; 
   else  
     out <= out+1; 
end 
endmodule
```

Developed by: BHAVITRA B RegisterNumber:25012160


**RTL LOGIC UP COUNTER**
<img width="1535" height="840" alt="Screenshot 2025-12-03 133242" src="https://github.com/user-attachments/assets/5f2fecdc-0142-4cdb-b233-09850617f602" />



**TIMING DIAGRAM FOR IP COUNTER**
<img width="1325" height="215" alt="Screenshot 2025-12-03 133909" src="https://github.com/user-attachments/assets/d9e62462-0930-4527-b0dc-70d597c7bf2f" />







<img width="673" height="719" alt="image" src="https://github.com/user-attachments/assets/46e7c8fd-d708-437e-8e52-1b14e8dc3acd" />








**RESULTS**
The given Sychronous Up Counter is successfully implemented using Verilog HDL in the Quartus Prime.

