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


**PROGRAM**

UP COUNTER:

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

DOWN COUNTER:

```

module ex12(out,clk,rst);
input clk,rst;
output reg [3:0]out;
always @ (posedge clk)
begin
   if(rst)
     out<=0;
   else 
     out <= out-1;
end
endmodule

```

/* Program for flipflops and verify its truth table in quartus using Verilog programming. 

Developed by: MAebicen Kirubakar C 

RegisterNumber: 24001839

*/

**RTL LOGIC UP COUNTER**

![WhatsApp Image 2024-12-26 at 21 39 53_92443263](https://github.com/user-attachments/assets/358aff06-0ed5-4144-9881-bca625232d4a)


**TIMING DIAGRAM FOR IP COUNTER**

![WhatsApp Image 2024-12-26 at 21 39 57_7bbcb260](https://github.com/user-attachments/assets/ecf9b74f-a87d-4db9-ad12-e35057ff80a8)

**TRUTH TABLE**

![WhatsApp Image 2024-12-20 at 13 55 11_4f98a151](https://github.com/user-attachments/assets/1ba0399e-1fd9-47e7-84a5-af4592914be6)


**RESULTS**

implemented 4 bit synchronous up counter and validate functionality.

