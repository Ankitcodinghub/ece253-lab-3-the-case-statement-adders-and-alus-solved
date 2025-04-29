# ece253-lab-3-the-case-statement-adders-and-alus-solved
**TO GET THIS SOLUTION VISIT:** [ECE253 Lab 3-The case statement, Adders and ALUs Solved](https://www.ankitcodinghub.com/product/ece253-laboratory-exercise-3-solved/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;109992&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;1&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (1 vote)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;ECE253 Lab 3-The case statement, Adders and ALUs Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (1 vote)    </div>
    </div>
The case statement, Adders and ALUs

This is an exercise in designing multiplexers using the Verilog case statement, using hierarchy in Verilog, and developing a simple adder and an ALU, where you can learn about the many Verilog operators.

1 Work Flow

2 Part I

For this part of the lab, you will be learning how to use always blocks (textbook Section 2.10.2, A.11.1) and case statements (textbook Section 4.6.3, A.11.4) to design a 7-to-1 multiplexer.

Like a module, an always block can have inputs and outputs. A module can contain any number of always blocks just the same as any module can contain any number of other module instantiations. The difference is that an always block can only instantiate logic within the module where it is defined. In contrast, a module can be instantiated in any other module, i.e., a module can be reused.

A key requirement of using an always block is that any output of an always block must have been declared as a reg type in the module containing the always block.

The model Verilog code for a 7-to-1 multiplexer built using a case statement is shown in Figure 1. The seven inputs are from the signals named Input[6:0]. The output is called Out. The select lines are called MuxSelect[2:0].

An always block is triggered to execute in simulation whenever there is a change in the sensitivity list. This list is denoted by the asterisk character in Figure 1. This means that

reg Out; // declare the output signal for the always block

always @(*) begin // declare always block

case (MuxSelect[2:0]) // start case statement

3’b000: Out = Input[0]; // case 0

3’b001: Out = Input[1]; // case 1

3’b010: Out = Input[2]; // case 2

3’b011: … // case 3

3’b100: … // case 4

3’b101: … // case 5

3’b110: … // case 6

default: …

endcase end // default case

Figure 1: Model Verilog code for a 7-to-1 multiplexer using a case statement.

whenever any input to the always block is changed, the code in the always block will be simulated. We can change the asterisk to certain inputs to limit when this code is triggered, but this can lead to simulations that do not match the real hardware. This is one of the (bad) features of the language. The accepted practice today is to always use the asterisk in your always block for combinational logic, i.e., any logic where the outputs rely strictly on the inputs. You will learn more about combinational and sequential logic later. For now, always use the asterisk in the always block for a case statement as shown above.

It is important to have a default case to ensure that all cases are covered. Otherwise, you can again have simulations that do not match the hardware. Yet another Verilog feature! Your goal is to write Verilog that will generate hardware that exactly matches the simulation, so please put in the default statement.

2.1 What to Do

The module you are writing for Part I should have the following signature declaration:

module part1(MuxSelect, Input, Out);

To build your module, perform the following steps:

1. Draw a schematic showing your code structure with all wires, inputs and outputsclearly labeled.

2. After drawing your schematic, write the Verilog code that corresponds to your schematic.Your Verilog code should use the same names for the wires and instances shown in the schematic. You can use the code fragment from Figure 1 as a starting point.

3. Simulate your circuit with ModelSim for different values of MuxSelect and Input. How many different patterns of inputs do you need to simulate to have confidence that your circuit is working? When you are satisfied with your simulations, you can submit to the Automarker. Keep in mind that this part does not need Quartus; there is no need to compile your code in Quartus each time you make a change. You can just re-run the wave.do file to redo simulation.

5. Compile the project to generate a bitstream to make sure your code can at leastbe synthesized. It is possible, and not uncommon, to write Verilog that simulates properly, but it cannot be synthesized to working hardware. If you can successfully create a bitstream, your code can create some kind of hardware. Whether it works is another question!

Figure 2: A ripple-carry adder circuit.

7. If you do not have a board, you can use fake fpga to test that your circuit behaves as expected. Review what you did in Lab 2 to use fake fpga.

3 Part II

Figure 2(a) shows a circuit for a full adder (textbook Section 3.2), which has the inputs a, b, and ci, and produces the outputs s and co. Parts (b) and (c) of the figure show a circuit symbol and truth table for the full adder, which produces the two-bit binary sum cos = a+b+ci. Figure 2(d) shows how four instances of this full adder module can be used to design a circuit that adds two four-bit numbers. This type of circuit is called a ripple-carry adder because of the way that the carry signals are passed from one full adder to the next. Write Verilog code that implements the circuit of Figure 2(d) following the steps below. Be sure to use what you learned about hierarchy in Lab 2.

3.1 What to Do

The module for your four-bit ripple-carry adder design should have the following signature declaration:

module part2(a, b, c in, s, c out);

To build your part2 module, perform the following steps:

1. Draw a schematic that will reflect your code structure with all wires, inputs and outputslabeled. It should look much like Figure 2.

2. After drawing your schematic, write the Verilog code that corresponds to your schematic.You should make use of there being four instances of the same full adder block. First, write a Verilog module for the full adder sub-circuit and then write the part2 module that will instantiate four instances of your full adder module. Your Verilog code should use the same names for the wires and instances as shown in your schematic.

3. Simulate your adder with ModelSim for intelligently chosen values of the inputs a, b and cin. Note that as circuits get more complicated, you will not be able to simulate or test all possible cases. How many input combinations would you need to simulate all possible input combinations for this four-bit adder? What about a 32-bit adder? When it is not possible to simulate all input combinations then you can test only a subset. Here intelligently chosen means to find particular corner cases that exercise key aspects of the circuit. An example would be a pattern that shows that the carry signals are working. When you are satisfied with your simulations, you can submit to the Automarker.

4. Create a new Quartus project for your circuit. You will need a top-level module tomake connections from the instantiation of your part2 module to the switches and LEDs of the DE1-SoC board. Use switches SW7−4 and SW3−0 to represent the inputs a and b, respectively. Use SW8 for the carry-in, cin, of the adder. Connect the outputs of the adder, cout and s, to the LEDs LEDR9 and LEDR3−0 respectively.

5. Compile the project to generate a bitstream to make sure your code can at least besynthesized.

6. If you have a board, download the compiled circuit into the FPGA chip. Test thefunctionality of the circuit by toggling the switches and observing the output LEDs.

7. If you do not have a board, you can use fake fpga to test that your circuit behaves as expected.

4 Part III

Using Parts I and II from this lab and the HEX decoder from Lab 2 Part III, you will implement a simple Arithmetic Logic Unit (ALU). An ALU has two inputs and can perform multiple operations on the inputs such as addition, subtraction, logical operations, etc. The output of the ALU is selected by function bits that specify the function to be performed by the ALU. The easiest way to build an ALU is to implement all required functions and connect the outputs of the functions to a multiplexer. Choose the output value for the ALU using the ALU function inputs to drive the multiplexer select lines. The output of the ALU will be displayed on the LEDs and HEX displays.

Shown in the pseudo-code, i.e., not exact syntax, case statement below are the operations to be implemented in the ALU for each function value. The ALU has two 4-bit inputs, A and B and an 8-bit output, called ALUout[7:0]. Note that in some cases, the output will not require the full 8 bits so do something reasonable with the extra bits, such as making them 0 so that the value is still correct.

always @(*) // declare always block begin case (function) // start case statement

0: A + B using the adder from Part II of this Lab

1: A + B using the Verilog ‘+’ operator

2: Sign extension of B to 8 bits // textbook page 167

3: Output 8’b00000001 if at least 1 of the 8 bits in the two inputs is 1 using a single OR operation

4: Output 8’b00000001 if all of the 8 bits in the two inputs are 1 using a single AND operation

5: Display A in the most significant four bits and B in the lower four bits default: … // default case endcase

end

4.1 Things to Watch For

Note that in this part of the lab, you will need to learn about number representations in Verilog (textbook Section A.5) and various other Verilog operators (textbook Section 4.6.5). You will need to learn about several operators including Verilog concatenation for the additions to stick in the extra bits you need and to create other 8-bit values, and Verilog reduction operations for ORing and ANDing multiple bits without typing out the operation for each bit individually.

The case statement must always be inside an always block. If you look at the operations for the ALU, four of the cases can be implemented with logic expressions, which can be described within an always block, so they can be expressed within the relevant cases in the case statement. However, for Case 0 you have to use the adder module you built for Part II. You cannot instantiate a module within an always block, so how do you make this work? If you come up with the correct schematic for your circuit, that will tell you what to do. Remember to label all the internal wires of your circuit to help you figure this part out.

4.2 What to Do

The module you are writing for Part III should have the following signature declaration:

module part3(A, B, Function, ALUout);

To build your module, perform the following steps:

1. Draw a schematic that will reflect your code structure with all wires, inputs and outputslabeled.

2. After drawing your schematic, write the Verilog code that corresponds to your schematic.Your Verilog code should use the same names for the wires and instances as shown in your schematic.

3. Simulate your ALU with ModelSim to satisfy yourself that your circuit is working.Be prepared to justify that your test cases are enough to give confidence that your circuit is working. When you are satisfied with your simulations, you can submit to the Automarker.

4. Create a new Quartus project for your circuit. You will need a top-level module tomake connections from the instantiation of your part3 module to the switches, LEDs and HEX displays of the DE1-SoC board. The A and B inputs should connect to switches SW7−4 and SW3−0 respectively. Use KEY2−0 for the function inputs. Display ALUout[7:0] in binary on LEDR7−0; have HEX0 and HEX2 display the values of B and A respectively and set HEX1 and HEX3 to 0. HEX4 and HEX5 should display

ALUout[3:0] and ALUout[7:4], respectively.

5. Compile the project to generate a bitstream to make sure your code can at least besynthesized.

6. If you have a board, download the compiled circuit into the FPGA chip. Test thefunctionality of the circuit by toggling the switches and observing the outputs.

7. If you do not have a board, you can use fake fpga to test that your circuit behaves as expected.

Note: Be aware that KEY3−0 are inverted. Remember that the DE1-SoC board recognizes an unpressed pushbutton as a value of 1 and a pressed pushbutton as a 0.

5 Submission

When submitting to the Automarker make sure you have modules declared as shown below as the Automarker will be looking for modules with these exact signatures.

5.1 Part I

For Part I, you need to submit a file named part1.v with the following module in it:

1. module part1(MuxSelect, Input, Out);

5.2 Part II

For Part II, you need to submit a file named part2.v with the following module in it:

1. module part2(a, b, c in, s, c out);

5.3 Part III

For Part III, you need to submit a file named part3.v with the following module in it:

1. module part3(A, B, Function, ALUout);
