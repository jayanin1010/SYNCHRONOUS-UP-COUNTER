Developed by: JAYANI N
RegisterNumber: 212224100025


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

1. Create a new project and name it.
2. Go to file, choose new file and click on the verilog HDL file.
3. Now have the program for 4-bit synchronous up counter and compile and run it.
4. Next, generate the RTL diagram for that go to Netlist viewers and select RTL diagram.
5. For the waveform/timing diagram insert the nodes and give the inputs for clock and reset and run it.

**PROGRAM**

      module sync_up_counter (
          input clk,
          input reset,
          output reg [3:0] count
      );
      
      always @(posedge clk or posedge reset) begin
          if (reset)
              count <= 4'b0000;
          else
              count <= count + 1;
      end
      
      endmodule


**RTL LOGIC UP COUNTER**
![Screenshot 2025-05-06 100140](https://github.com/user-attachments/assets/11dbbc34-1a43-4703-9d76-8a050b2ae5c6)


**TIMING DIAGRAM FOR IP COUNTER**
![Screenshot 2025-05-06 101725](https://github.com/user-attachments/assets/d5ed4d48-af0b-4443-931f-9e5d2f52bb47)


**TRUTH TABLE**

![image](https://github.com/user-attachments/assets/33fe9063-b902-4983-a0dd-280db8f4cb51)


**RESULTS**
Thus the simulation, logic diagram and waveform has been verified for syncronous up-counter using quartus.
