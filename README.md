# FULL_ADDER_SUBTRACTOR

Implementation-of-Full-Adder-and-Full-subtractor-circuit

**AIM:**

To design a Full Adder and Full Subtractor circuit and verify its truth table in Quartus using Verilog programming.

**Equipments Required:**

Hardware – PCs, Cyclone II , USB flasher

Software – Quartus prime

**Full Adder and Full Subtractor**

**Full Adder**

Full adder is a digital circuit used to calculate the sum of three binary bits. It consists of three inputs and two outputs. Two of the input variables, denoted by A and B, represent the two significant bits to be added. The third input, Cin, represents the carry from the previous lower significant position. Two outputs are necessary because the arithmetic sum of three binary digits ranges in value from 0 to 3, and binary 2 or 3 needs two digits. The two outputs are sum and carry.

Sum =A’B’Cin + A’BCin’ + ABCin + AB’Cin’ = A ⊕ B ⊕ Cin 

Carry = AB + ACin + BCin

![image](https://github.com/naavaneetha/FULL_ADDER_SUBTRACTOR/assets/154305477/0f30ba51-5ffb-4198-845f-18e054f675e7)

**Figure -1 FULL ADDER**

**Full Subtractor**

A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow.

![image](https://github.com/naavaneetha/FULL_ADDER_SUBTRACTOR/assets/154305477/02b24f51-ab51-4304-9ad6-7b81ffc1ead5)

Diff = A ⊕ B ⊕ Bin 

Borrow out = A'Bin + A'B + BBin

**Truthtable**

full adder:
<img width="305" height="234" alt="image" src="https://github.com/user-attachments/assets/b3d1b724-dde8-406a-aa29-a65973d17eb6" />

full subtractor:
<img width="300" height="161" alt="image" src="https://github.com/user-attachments/assets/cac1940b-5507-4793-ae18-c92145c7169e" />


**Procedure**

Create a New Project
Open Quartus.
Click File → New Project Wizard.
Select a project folder and type the project name (e.g., FA_FS).
Choose Empty Project and finish.

2. Create a Block Diagram/Schematic File

Go to File → New.
Select Block Diagram/Schematic File (.bdf) and click OK.
A blank design window will appear.

3. Insert Logic Gates

Press Ctrl + Shift + L or go to Edit → Insert → Symbol.
In the library, choose:
xor gate
and gate
or gate
not gate (for subtractor)
Place the required gates on the schematic for both:
Full Adder
Full Subtractor

4. Draw the Full Adder Circuit

Connect A, B, Cin to XOR gates to form Sum.
Connect AND + OR gates to produce Carry.
Add Input pins for A, B, Cin and Output pins for Sum and Carry.

5. Draw the Full Subtractor Circuit

Connect A, B, Bin to XOR gates to form Difference.
Connect NOT, AND, OR gates to produce Borrow.
Add Input pins for A, B, Bin and Output pins for Difference and Borrow.

6. Save and Compile

Save the schematic as FA_FS.bdf.
Click Processing → Start Compilation.
Ensure there are no errors.

7. Simulate the Design

Go to File → New → University Program VWF (Vector Waveform File).
Add inputs and outputs using Edit → Insert Node or Bus.
Set the input waveforms (0 and 1).
Run simulation using Simulation → Run Functional Simulation.

8. Verify Outputs

Observe Sum, Carry, Difference, and Borrow waveforms.
Compare with the truth table.

DEVELOPED BY:Tejasvi S

register number:25018602

**Program:**
full adder
```
module full_adder(
    input A, B, Cin,
    output Sum, Carry
);

    assign Sum   = A ^ B ^ Cin;
    assign Carry = (A & B) | (Cin & (A ^ B));

endmodule
```
full subractor
```
module full_subtractor(
    input A, B, Bin,
    output Difference, Borrow
);

    assign Difference = A ^ B ^ Bin;
    assign Borrow     = (~A & B) | (~A & Bin) | (B & Bin);

endmodule
```
**RTL Schematic**
full adder
<img width="1920" height="1080" alt="Screenshot (125)" src="https://github.com/user-attachments/assets/950e13ee-a20d-4e93-a3e1-58f66df855d0" />

full subractor
<img width="1920" height="1080" alt="Screenshot (130)" src="https://github.com/user-attachments/assets/01dd5184-08cc-4714-ac84-bd0459e1bb69" />

**Output Timing Waveform**
<img width="1920" height="1080" alt="Screenshot (132)" src="https://github.com/user-attachments/assets/e668c924-5e18-4f43-bce8-5a38c46ad11e" />
<img width="1920" height="1080" alt="Screenshot (128)" src="https://github.com/user-attachments/assets/951e6f17-242e-496c-bcfe-5e51d18a46f0" />

**Result:**

Thus the Full Adder and Full Subtractor circuits are designed and the truth tables is verified using Quartus software.



