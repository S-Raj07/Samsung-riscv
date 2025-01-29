# VSDSquadron Mini Internship 
<img align="right" width="300" height="138" src="https://github.com/VijayN53/VSDSquadron_Mini_Internship/assets/106604062/368c7a8d-7891-4838-8b8f-f9634078b7fc"> VSDSquadron Mini Board is a RISC-V based Architecture and consists of 32-bit RISC-V Core ,3 Groups of GPIO pins(15 I/O ports),RV32EC instruction set and supports CH32V305FBP6 single-wire programming protocol and other various communication protocols<br />



## Basic Details
**Name:**  Sushanthi Raj<br />
**College:** Dayananda Sagar College of Engineering<br />
**Email Id:** sushanthiraj07@gmail.com<br />
**GitHub Profile:** [S-raj07]https://github.com/S-Raj07/Samsung-riscv<br />
**Linkedin Profile:** https://www.linkedin.com/in/sushanthi-raj-a43779262?utm_source=share&utm_campaign=share_via&utm_content=profile&utm_medium=android_app<br />

***
RISC-V 

RISC-V internship using VSDSquardron Mini is based on RISC-V architecture and uses open source in teaching students VLSI SOC design and RISC-V
About the Mission RISC-V Mission 2025 aims to:

Build a skilled workforce of 1,000 RISC-V engineers in Karnataka. Train engineering students with hands-on expertise in RISC-V and semiconductor technologies. Strengthen India’s role in the global semiconductor ecosystem. My Journey Program Highlights 6-Week Training: Practical skills in RISC-V architecture and semiconductor technology. RISC-V Development Board: Exclusive access to VSD-provided boards. Remote Workshops: Hands-on training for Tier-2 and Tier-3 VTU colleges. Online Learning: Intensive courses to reinforce skills. 🎓 Key Learnings RISC-V Architecture: Core concepts, instruction sets, and applications. Hardware-Software Co-Design: Seamless integration of software and RISC-V hardware. VLSI Design: Techniques shaping the future of semiconductors. Hands-On Projects: Real-world applications with RISC-V boards and tools. Repository Highlights Code Samples: Projects and implementations from the program. Documentation: Insights, concepts, and assignments. Project Showcase: A comprehensive project leveraging RISC-V and VLSI skills. Vision Through this initiative, I aim to:

Contribute to India’s semiconductor growth. Deepen expertise in RISC-V and VLSI technologies. Join the next generation of semiconductor innovators. Let’s Collaborate! Explore this repository, share your thoughts, or collaborate on exciting RISC-V projects. Together, let’s drive the future of semiconductor technology!

Acknowledgments Grateful to:
Samsung Semiconductor India Research (SSIR) VLSI System Design (VSD) The entire RISC-V Mission 2025 team for this transformative experience.

<details>
<summary><b>Task 1:</b>The task is to install the necessary tools for this internship such as Ubuntu on VMBox, Visual C++ and write a sample C code and analysing RISC asssemby code for the sample C code</summary><br />
  
  **1.Installing Ubuntu on VMBox**<br />
  After installing the tools then open the terminal on Ubuntu to type the command.<br />
  ![Installing Ubuntu   VMBox](https://github.com/VijayN53/VSDSquadron_Mini_Internship/assets/106604062/51924514-846f-4fe7-8d96-2619dad511f0)

  
  **2.Command for Installing Leafpad**<br />
  ```
  $ sudo apt install leafpad
  ```
  
  **3.Command for Opening Leafpad**<br />
  ```
  $ cd
  $ leafpad filename.c &
  ```
  ![Sample_C_code]![task1 1](https://github.com/user-attachments/assets/a9c4919d-1fbf-4654-809f-433bb87348ca)


  
  **4.Command for Compiling and Analyzing the Output**<br />
  ```
  $ gcc filename.c
  $ ./a.out
  ```
  ![Output of Sample code]![task1 riscv 1 1](https://github.com/user-attachments/assets/c4923d7e-bf30-42f9-8c18-738f6746ef8b)


    
  **5.Command for Compiling the Code using RISCV Compiler**<br />
  ```
  $ riscv64-unknown-elf-gcc -O1 -mabi=lp64 -march=rv64i -o filename.o filename.c
  $ ls -ltr filename.o
  ```
  ![Installing RISC Compiler]![task1](https://github.com/user-attachments/assets/c18c45c1-ce22-491f-8583-1df3cd343521)

  **6.Command to View the Assembly Code**<br />
  ```
  $ riscv64-unknown-elf-objdump -d filename.o //Gives bunch of Code
  $ riscv64-unknown-elf-objdump -d filename.o | less // Gives Reduced Code
  /main //to view the main function of the code
  ```
  ![Main Function Assembly code](https://github.com/VijayN53/VSDSquadron_Mini_Internship/assets/106604062/d925b284-359e-444e-a7bb-62dd9a135d06)![ricvfast task1](https://github.com/user-attachments/assets/790d3a6f-3f62-4a89-8201-5d5cb64073da)

    
  **7. Command to View the Assembly Code**<br />
  ```
  $ riscv64-unknown-elf-gcc -Ofast -mabi=lp64 -march=rv64i -o filename.o filename.c
  $ riscv64-unknown-elf-objdump -d filename.o | less 
  /main 
  ```
  ![Assembly code for ofast command]![task1 riscv 1 1](https://github.com/user-attachments/assets/9bde0f01-a9b5-4c5c-ba33-fdb23b8c01ec)
![ricvfast task1](https://github.com/user-attachments/assets/642cc909-1bb8-4092-99de-e5a11713dac4)

  
</details>

***


<details>
<summary><b>Task 2:</b> Running the SPIKE Simulation and observe the performance under the -O1 and -Ofast Compiler optimization flags.
</summary><br />
  **1.Sample C Code on LeafPad**<br />
 
 ![Task 2](https://github.com/user-attachments/assets/e1cf0c8a-646f-454a-9817-cef7c006e169)

 Sum of Integers from 1 to n
<b>Debugging sum.o for O1</b>
<pre><code>riscv64-unknown-elf-gcc -O1 -mabi=lp64 -march=rv64i -o sum.o sum.c
![Task 2 for O1 command](https://github.com/user-attachments/assets/1b936003-fcff-4eaf-90c4-2fbdb765cfaf)

ls -ltr sum.o
spike pk sum.o
spike -d pk sum.o</code></pre>
<b>O1 assembly output</b>
<pre>0000000000010184 &lt;main&gt;:
   10184:       ff010113                addi    sp,sp,-16
   10188:       00113423                sd      ra,8(sp)
   1018c:       04600793                li      a5,70
   10190:       fff7879b                addiw   a5,a5,-1
   10194:       fe079ee3                bnez    a5,10190 &lt;main+0xc&gt;
   10198:       00001637                lui     a2,0x1
   1019c:       96f60613                addi    a2,a2,-1681 # 96f &lt;register_fini-0xf741&gt;
   101a0:       04500593                li      a1,69
   101a4:       00021537                lui     a0,0x21
   101a8:       19050513                addi    a0,a0,400 # 21190 &lt;__clzdi2+0x48&gt;
   101ac:       26c000ef                jal     ra,10418 &lt;printf&gt;
   101b0:       00000513                li      a0,0
   101b4:       00813083                ld      ra,8(sp)
   101b8:       01010113                addi    sp,sp,16
   101bc:       00008067                ret
</pre>
**2.Checking The Output**<br />
 ![task 2 O1](https://github.com/user-attachments/assets/92121fc4-40b9-416c-813a-9dbc10b34ad8)

<p>15 instructions for O1</p>
<br>

<br><br>
<b>Debugging sum.o for Ofast</b>
<pre><code>riscv64-unknown-elf-gcc -Ofast -mabi=lp64 -march=rv64i -o sum.o sum.c
spike pk sum.o
spike -d pk sum.o</code></pre>

![task 2](https://github.com/user-attachments/assets/905deefe-5f77-4dd6-b5f2-367dcedd37a4)

<b>Ofast assembly output</b>
<pre>00000000000100b0 &lt;main&gt;:
   100b0:       00001637                lui     a2,0x1
   100b4:       00021537                lui     a0,0x21
   100b8:       ff010113                addi    sp,sp,-16
   100bc:       96f60613                addi    a2,a2,-1681 # 96f &lt;main-0xf741&gt;
   100c0:       04500593                li      a1,69
   100c4:       18050513                addi    a0,a0,384 # 21180 &lt;__clzdi2+0x44&gt;
   100c8:       00113423                sd      ra,8(sp)
   100cc:       340000ef                jal     ra,1040c &lt;printf&gt;
   100d0:       00813083                ld      ra,8(sp)
   100d4:       00000513                li      a0,0
   100d8:       01010113                addi    sp,sp,16
   100dc:       00008067                ret
</pre>
<p>12 instructions for Ofast</p>
<br>
</details>

<details>
<b>Task 2 Example:</b>To Write a Simple C code for the project "Area of a square" and to analyze instructions in  assembly code using RISC-V Compiler by following the same procedures in the task1<br />

  **1.Sample C Code on LeafPad**<br />
 
  ![1 Simple C code]![task 2-own example](https://github.com/user-attachments/assets/e4160c27-2c98-4b0c-a097-6b3066ce59c4)


**2.Checking The Output**<br />
  > The Output Clock signal is produced in the Output and verified for O1 command.<br />
  ![2 Output for the  C code]![task 2-own eg O1](https://github.com/user-attachments/assets/4cc3d991-f8b9-4b15-8b57-621d9d329060)



**4.Run the code using Ofast Command**<br />
  > Compiling the C code on RISC-V compiler using the below shown command.<br />
  ![6 Ofast cmnd to run code on RISC-V]![task 2-own eg Ofast](https://github.com/user-attachments/assets/cf698040-3395-4199-af55-aea72bca513c)


 </details>

 
 ***

 
<details>
  <summary><b>Task 3:</b>Identify instruction type of all the instructions of the Object dump with its exact 32 bits instruction code in the desired instruction type format.</summary><br />

Instruction 1

![task3 ins 1](https://github.com/user-attachments/assets/8e249637-ac3e-4379-9757-4ad81e0ac178)

Instruction:
lui a0, 0x21

Address:
100b0 (This is the memory address where this instruction is located.)

Operation:
lui (This is the mnemonic for the "Load Immediate Upper" instruction.)

Purpose:
The lui instruction loads an immediate value into the upper 20 bits of the specified register. In this case, it loads the immediate value 0x21 into register a0.

Result in a0:
a0 = 0x210000 (The immediate value 0x21 is placed in the upper 20 bits of a0, and the lower 12 bits are filled with zeros.)

Instruction Format (U-type):
The lui instruction follows the U-type format in RISC-V:

[imm[31:12]] [rd] [opcode]

Immediate (imm[31:12]): A 20-bit immediate value that is left-shifted by 12 bits to form the final 32-bit immediate value.

Destination Register (rd): Specifies the register where the result is stored.

Opcode: Specifies the operation (lui).

Immediate (imm[31:12]):

The immediate value 0x21 is converted to binary:
0x21 → 0010 0001
This binary value is placed in the top 20 bits of the instruction.

Destination Register (rd):
a0 is the destination register.

Opcode:
The opcode for the lui instruction is 0110111.

Encoded Instruction

The instruction lui a0, 0x21 is encoded as follows:
Immediate (20-bit value): 0000 0010 0001 0000 0000.

Destination Register (rd = x10): 01010.

Opcode: 0110111.

Binary Representation:
Combining the fields into binary:
[imm[31:12]] [rd] [opcode]
0010 0001 00000 0110111

Hexadecimal Representation:
Converting the binary representation into hexadecimal:
0010 0001 00000 0110111 → 00210013

In Summary:
At memory address 100b0, the lui a0, 0x21 instruction loads the immediate value 0x21 into the upper 20 bits of register a0, effectively setting a0 to 0x210000. This instruction is commonly used for loading address offsets and constants into registers in RISC-V programs.



Instruction 2
addi sp, sp, -16
![task3 ins 2](https://github.com/user-attachments/assets/93a97db7-5e2d-4502-afc7-86f915276b5a)

Instruction 2
addi sp, sp, -16

Address:
100b4 (This is the memory address where this instruction is located.)

Machine Code:
ff010113 (This is the binary representation of the instruction in hexadecimal format.)

Operation:
addi (This is the mnemonic for the "Add Immediate" instruction.)

Purpose:
The addi instruction is used to add an immediate value to a register. In this case, it's adding -16 to the sp register.

Result in sp:
sp = sp - 16 (This instruction subtracts 16 from the current value of the sp register.)

Instruction Format (I-type):
The addi instruction follows the I-type format in RISC-V:

[imm[11:0]] [rs1] [funct3] [rd] [opcode]

Immediate (imm[11:0]): A 12-bit immediate value.

Source Register 1 (rs1): Specifies the source register for the operation.

Funct3: Specifies the operation type (in this case, addition).

Destination Register (rd): Specifies the register where the result is stored.

Opcode: Specifies the operation (addi).

Immediate (imm[11:0]):
The immediate value is -16, which in binary is 1111111111110000.

Source Register 1 (rs1):
sp (stack pointer) is the source register.

Funct3:The funct3 for the addi instruction is 000.

Destination Register (rd):sp (stack pointer) is also the destination register.

Opcode:The opcode for the addi instruction is 0010011.

Binary Representation:
Combining the fields into binary:
[imm[11:0]] [rs1] [funct3] [rd] [opcode]
1111111111110000 00000 00000 0010011

Hexadecimal Representation:
Converting the binary representation into hexadecimal:
1111111111110000 00000 00000 0010011 → ff010113

In Summary:
The addi sp, sp, -16 instruction subtracts 16 from the stack pointer register (sp), effectively adjusting the stack pointer for function calls or local variable allocation.



Instruction 3
![task 3 ins 3](https://github.com/user-attachments/assets/5c31038a-410f-464f-9688-ce5d89ea8f9b)

instruction: li a2, 15
This loads the immediate value 15 into the register a2.
It is translated into the actual RISC-V instruction:
addi a2, x0, 15

Instruction Breakdown
Opcode (0010011):
This identifies the instruction as addi (add immediate).

Immediate (15):
The immediate value 15 is encoded as a 12-bit unsigned value: 0000 0000 1111.

Source Register (rs1 = x0):
The source register is x0 (the zero register), which always contains the value 0.

Funct3 (000):
Specifies the operation type as addition for the addi instruction.

Destination Register (rd = a2):
The destination register is a2 (also known as x12).

Operation
The addi instruction performs the following operation:
a2=x0+15
Since x0 always contains 0, the result is simply 15.
The value 15 is then stored in the a2 register.

Encoded Instruction
The pseudo-instruction li a2, 15 is therefore implemented as:
addi a2, x0, 15
This loads the immediate value 15 into the a2 register.

Instruction Address
Address: 100b8
The instruction is located at memory address 0x100b8.
If the machine code representation is required, it would be encoded as a 32-bit binary value based on the breakdown above.



Instruction 4
![task3 ins 4](https://github.com/user-attachments/assets/6dab570f-8665-4877-ba0f-107011ecfe65)

Instruction: li a1, 5
This loads the immediate value 5 into the register a1.

It is translated into the actual RISC-V instruction:
addi a1, x0, 5

Instruction Breakdown
Opcode (0010011):
Identifies this as an addi (add immediate) instruction.

Immediate (5):
The immediate value 5 is encoded as a 12-bit unsigned value: 0000 0000 0101.

Source Register (rs1 = x0):
The source register is x0 (the zero register), which always contains the value 0.

Funct3 (000):
Specifies the operation type as addition for the addi instruction.

Destination Register (rd = a1):
The destination register is a1 (also known as x11).

Operation
The addi instruction performs the following operation:
a1=x0+5
Since x0 always contains 0, the result is simply 5.
The value 5 is then stored in the a1 register.

Encoded Instruction
The instruction li a1, 5 is therefore implemented as:
addi a1, x0, 5
This loads the immediate value 5 into the a1 register.

Instruction Address
Address: 100bc
The instruction is located at memory address 0x100bc.
If the machine code representation is required, it would be encoded as a 32-bit binary value based on the breakdown above.



Instruction 5
![task 3 ins 5](https://github.com/user-attachments/assets/ad1ec906-0c74-4eaf-8a9d-ef843298084a)

Instruction: addi a0, a0, 384
This adds the immediate value 384 to the contents of register a0 and stores the result back in a0.

Instruction Breakdown
Opcode (0010011):
Identifies this as an addi (add immediate) instruction.

Immediate (384):
The immediate value 384 is encoded as a 12-bit signed value.

In binary, 384 is represented as 0001 1000 0000.

Source Register (rs1 = a0):
The source register is a0 (also known as x10).

Funct3 (000):
Specifies the operation type as addition for the addi instruction.

Destination Register (rd = a0):
The destination register is also a0 (also known as x10).

Operation
The addi instruction performs the following operation:
a0=a0+384

The value in a0 (source register) is added to the immediate value 384, and the result is stored back into a0.

Encoded Instruction
The instruction addi a0, a0, 384 is encoded as:
addi a0, a0, 384

Immediate (12-bit signed): 0001 1000 0000

Source Register (rs1 = x10): 01010

Destination Register (rd = x10): 01010

Funct3: 000

Opcode: 0010011

Instruction Address

Address: 100c0
The instruction is located at memory address 0x100c0.
The encoded machine code would follow the 32-bit RISC-V encoding format based on the breakdown above



 Instruction 6
 ![task 3 ins 6](https://github.com/user-attachments/assets/ffbf0ecc-3129-4229-bd71-8987ab93707c)

Instruction: sd ra, 8(sp)
This stores the value in the ra register (return address) at the memory address computed by adding 8 to the value in the sp (stack pointer) register.

Instruction Breakdown
Opcode (0100011):
Identifies this as a store instruction (S-type format).

Immediate (8):
The immediate value 8 is split into two parts for encoding:
Lower 5 bits: Stored in bits [11:7] of the instruction.
Upper 7 bits: Stored in bits [31:25] of the instruction.

In binary, 8 is represented as 0000 0000 1000.

Source Register 2 (rs2 = ra):
The value to be stored comes from the ra register (also known as x1).

Source Register 1 (rs1 = sp):
The memory address is computed using the sp register (also known as x2).

Funct3 (011):
Specifies the sd (store doubleword) operation.

Operation
The sd instruction performs the following operation:
Memory[sp+8]=ra
The effective memory address is calculated by adding the immediate value 8 to the value in the sp register.
The value in the ra register is then stored at that computed memory address.

Encoded Instruction
The instruction sd ra, 8(sp) is encoded as follows:

Immediate (12-bit signed):

Lower 5 bits: 01000 (bits [11:7]).

Upper 7 bits: 0000000 (bits [31:25]).

Source Register 2 (rs2 = x1): 00001

Source Register 1 (rs1 = x2): 00010

Funct3: 011

Opcode: 0100011

Instruction Address
Address: 100c4
The instruction is located at memory address 0x100c4.
The encoded machine code would follow the 32-bit RISC-V S-type format based on the breakdown above.



Instaruction 7
![task 3 ins 7](https://github.com/user-attachments/assets/f4f72d0f-6247-483a-a353-156b5c472cb2)

Instruction: jal ra, 10408
The jal (jump and link) instruction causes a jump to the specified address (label <printf> located at 10408).
It also stores the return address (address of the next instruction) into the ra register (return address, also known as x1).

Instruction Breakdown

Opcode (1101111):
Identifies this as a jal (jump and link) instruction.

Immediate (10408):
The immediate value specifies the offset to the jump target relative to the address of the jal instruction.

The target address 10408 is relative to the current instruction address 100c8.
Offset=10408−100c8=0x3E0=992(in decimal)

In the jal instruction, the immediate is encoded as a 20-bit signed value split across several fields:
Bit 20: Sign bit.
Bits [19:12]: Upper immediate bits.
Bit 11: Lower immediate bit.
Bits [10:1]: Remaining immediate bits.

Destination Register (rd = ra):
The destination register is ra (return address, also known as x1).

Operation
The jal instruction performs two operations:
Stores the address of the next instruction (100c8 + 4 = 100cc) into the ra register.
Jumps to the target address 10408.

Encoded Instruction
The instruction jal ra, 10408 is encoded as follows:

Immediate (20-bit signed):
Encoded offset: 0x3E0 (binary: 0000 0011 1110 0000).

Split into fields:
Bit 20 (sign bit): 0.
Bits [19:12]: 0000 0011.
Bit 11: 1.
Bits [10:1]: 1110 0000.

Destination Register (rd = x1): 00001.

Opcode: 1101111.

Instruction Address
Address: 100c8
The instruction is located at memory address 0x100c8.
The encoded machine code would follow the 32-bit RISC-V J-type format based on the breakdown above.



Instruction 8
![task 3 ins 8](https://github.com/user-attachments/assets/21e12bba-1e11-406e-803c-0a23ec07f360)

Instruction: ld ra, 8(sp)
The ld (load doubleword) instruction loads a 64-bit value from the memory address computed by adding 8 to the value in the sp (stack pointer) register.
The loaded value is stored in the ra (return address) register.

Instruction Breakdown
Opcode (0000011):
Identifies this as a load instruction (I-type format).

Immediate (8):
The immediate value 8 is encoded as a 12-bit signed value: 0000 0000 1000.

Source Register (rs1 = sp):
The base address for the memory load is held in the sp register (stack pointer, also known as x2).

Destination Register (rd = ra):
The value loaded from memory will be stored in the ra register (return address, also known as x1).

Funct3 (011):
Specifies the ld (load doubleword) operation.

Operation
The ld instruction performs the following operation:
ra=Memory[sp+8]

The effective memory address is calculated by adding the immediate value 8 to the value in the sp register.
The 64-bit value at this memory address is loaded into the ra register.

Encoded Instruction
The instruction ld ra, 8(sp) is encoded as follows:

Immediate (12-bit signed): 0000 0000 1000.

Source Register (rs1 = x2): 00010.

Destination Register (rd = x1): 00001.

Funct3: 011.

Opcode: 0000011.

Instruction Address
Address: 100cc
The instruction is located at memory address 0x100cc.
The encoded machine code would follow the 32-bit RISC-V I-type format based on the breakdown above.



Instruction 9
![task 3 ins9](https://github.com/user-attachments/assets/3a19f5ce-ee43-4fed-9c81-8c07380268b2)

Instruction: li a0, 0
This loads the immediate value 0 into the a0 register.
It is translated into the actual RISC-V instruction:
addi a0, x0, 0.

Instruction Breakdown
Opcode (0010011):
Identifies this as an addi (add immediate) instruction.

Immediate (0):
The immediate value 0 is encoded as a 12-bit signed value: 0000 0000 0000.

Source Register (rs1 = x0):
The source register is x0 (the zero register), which always contains the value 0.

Destination Register (rd = a0):
The destination register is a0 (also known as x10).

Funct3 (000):
Specifies the operation type as addition for the addi instruction.

Operation
a0=x0+0
Since x0 always contains 0, the result is simply 0.
The value 0 is then stored in the a0 register.

Encoded Instruction
The pseudo-instruction li a0, 0 is implemented as:
addi a0, x0, 0

This instruction can be encoded as follows:

Immediate (12-bit signed): 0000 0000 0000.

Source Register (rs1 = x0): 00000.

Destination Register (rd = x10): 01010.

Funct3: 000.

Opcode: 0010011.

Instruction Address

Address: 100d0
The instruction is located at memory address 0x100d0.
The encoded machine code would follow the 32-bit RISC-V I-type format based on the breakdown above.



Instruction 10
![task 3 ins10](https://github.com/user-attachments/assets/0967a69b-49ce-4f2b-92cd-24d0fc53292a)

Instruction: addi sp, sp, 16
This adds the immediate value 16 to the value in the sp (stack pointer) register and stores the result back in the sp register.

Instruction Breakdown
Opcode (0010011):
Identifies this as an addi (add immediate) instruction.

Immediate (16):
The immediate value 16 is encoded as a 12-bit signed value: 0000 0001 0000.

Source Register (rs1 = sp):
The source register is sp (stack pointer, also known as x2).

Destination Register (rd = sp):
The destination register is also sp (stack pointer, also known as x2).

Funct3 (000):
Specifies the operation type as addition for the addi instruction.

Operation
The addi instruction performs the following operation:
sp=sp+16

The value 16 is added to the current value of the sp register, and the result is stored back into sp.

Encoded Instruction
The instruction addi sp, sp, 16 can be encoded as follows:

Immediate (12-bit signed): 0000 0001 0000.

Source Register (rs1 = x2): 00010.

Destination Register (rd = x2): 00010.

Funct3: 000.

Opcode: 0010011.

Instruction Address
Address: 100d4
The instruction is located at memory address 0x100d4.
The encoded machine code would follow the 32-bit RISC-V I-type format based on the breakdown above.



Instruction 11
![task 3 ins 11](https://github.com/user-attachments/assets/070f2ad0-af69-474d-b70a-5cab4a8d00cf)

Instruction: ret
The ret instruction is a pseudo-instruction in RISC-V.

It is translated into the actual instruction:
jalr x0, ra, 0.

Instruction Breakdown

Opcode (1100111):
Identifies this as a jalr (jump and link register) instruction.

Immediate (0):
The immediate value 0 is encoded as a 12-bit signed value: 0000 0000 0000.

Source Register (rs1 = ra):
The base address for the jump is held in the ra (return address) register, also known as x1.

Destination Register (rd = x0):
The destination register is x0 (zero register), which discards the result of the jump. This is used to indicate that no link is required.

Funct3 (000):
Specifies the operation type as an indirect jump for the jalr instruction.

Operation
The jalr instruction performs the following operation:
PC=ra+0
The program counter (PC) is set to the address stored in the ra register (return address) with an offset of 0.

Encoded Instruction
The ret pseudo-instruction is implemented as:
jalr x0, ra, 0

This instruction can be encoded as follows:

Immediate (12-bit signed): 0000 0000 0000.

Source Register (rs1 = x1): 00001.

Destination Register (rd = x0): 00000.

Funct3: 000.

Opcode: 1100111.

Instruction Address

Address: 100d8
The instruction is located at memory address 0x100d8.
The encoded machine code would follow the 32-bit RISC-V I-type format based on the breakdown above.

</details>


***


<details>
  <summary><b>Task 4:</b>To Use the RISC-V Core Verilog Netlist and Testbench for Functional simulation experiment by analysing and verifying the Output Waveform in GTKWave simulator.</summary> 

## 4. FUNCTIONAL SIMULATION

### 4.1 About iverilog and gtkwave
- Icarus Verilog is an implementation of the Verilog hardware description language.
- GTKWave is a fully featured GTK+ v1. 2 based wave viewer for Unix and Win32 which reads Ver Structural Verilog Compiler generated AET files as well as standard Verilog VCD/EVCD files and allows their viewing.

### PROCEDURES TO PERFORM FUNCTIONAL SIMULATION

### 4.2 Installing iverilog and gtkwave

- **For Ubuntu**

 Open your terminal and type the following to install iverilog and GTKWave
 ```
 $   sudo apt get update
 $   sudo apt get install iverilog gtkwave
 ```

- **To clone the repository and download the netlist files for simulation , enter the following commands in your terminal.**

 ```
 $ git clone https://github.com/vinayrayapati/iiitb_rv32i
 $ cd iiitb_rv32i
 ```
- **To simulate and run the verilog code , enter the following commands in your terminal.**

```
$ iverilog -o iiitb_rv32i iiitb_rv32i.v iiitb_rv32i_tb.v
$ ./iiitb_rv32i
```
- **To see the output waveform in gtkwave, enter the following commands in your terminal.**

`$ gtkwave iiitb_rv32i.vcd`
### 4.3 The output waveform

 The output waveform showing the instructions performed in a 5-stage pipelined architecture.
 
 Instruction 1:add r6,r2,r1
 ![task4 add1 1](https://github.com/user-attachments/assets/7ea19585-e8f5-4341-9271-a585e736f730)

Instruction 2:and 
![task4 and](https://github.com/user-attachments/assets/9a4fe579-cfeb-4465-8815-13d1f9ae01ef)

Instruction 3:beq
![task4 sw](https://github.com/user-attachments/assets/522aa9f1-4060-442f-ba4f-48524235d87f)

Instruction 4: lw
![task4 sw](https://github.com/user-attachments/assets/d7820a03-4d37-4f4c-a434-8c85620d5c5b)

Instruction 5: or
![task4 or](https://github.com/user-attachments/assets/06127f48-3e07-464c-b25f-85c85e106108)

Instruction 6: sub
![task4 sub](https://github.com/user-attachments/assets/478b6503-9d1c-4d4b-b7b0-9af79e506c5d)

Instruction 7: sw
![task4 sw](https://github.com/user-attachments/assets/d25cfcbc-a826-4bab-b283-520fc0e9c2ec)

Instruction 8: xor
![task4 xor](https://github.com/user-attachments/assets/7fbba2d5-edab-4436-bb34-53fdc34e03ca)

Output waveform:
![task4 1 1](https://github.com/user-attachments/assets/e315972b-ee62-4de2-ab79-3db5ea2d5cb5)

</details>

***

















































