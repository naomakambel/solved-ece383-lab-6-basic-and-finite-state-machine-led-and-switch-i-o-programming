Download Link: https://assignmentchef.com/product/solved-ece383-lab-6-basic-and-finite-state-machine-led-and-switch-i-o-programming
<br>
<em>Goals: The goals of this lab are to continue to instruct students in a PIC24-based hardware system using PIO ports for switch input and LED output using basic and finite state machine (FSM) processing.</em>

<h1>1.     Introduction</h1>

This lab introduces basic PIO port configuration and utilization for switch-based input and LED output. A C-based software finite state machine is used for an LED/switch I/O problem. The tasks in this lab include:

<ul>

 <li>Modifying and expanding the PIC24HJ128GP502 reference system schematic and printed circuit board to include additional pushbutton and LED components.</li>

 <li>Programming the Microstick II to implement a basic LED problem.</li>

 <li>Programming the Microstick II to implement a software finite state machine for an LED/switch I/O problem using additional pushbutton and LED components on the breadboard.</li>

</ul>

<h1>2.     Prelab</h1>

For this lab assignment, Tasks 1, 2, and 3 should be completed as a pre-lab assignment prior to your assigned lab time. You are also strongly encouraged to have the majority of the software written for Task 4 and 5 complete before your assigned lab time.

<strong>TA check: As soon as you enter lab, provide the TA with a pre-lab report that includes the complete schematic, PCB layout, and C programs. Lab time will be devoted to debugging the program execution and correcting any errors within MPLAB noted by the lab instructor. Make sure your group member names and date are on the pre-lab report.</strong>

<h1>3.     TASK 1: Expanding the PIC24 Reference System Schematic</h1>

Using PCB Artist, expand and modify the basic PIC24 system previously created as shown in Figure 1 below. If your previous PIC24 system schematic was designed and constructed neatly and correctly you may use your schematic from the previous lab as a starting point for this design. Otherwise you should construct a new system. Note that the pushbuttons use a different component from previous labs. The pushbutton component to use for this design, named PUSHBUTTON, is located in the ECE383 PCB Artist library located on the class website.

<strong>TA check</strong>: <strong>Upon entering the lab, show the TA the schematic design. Use a screen capture tool to capture the schematic window and include it in your lab report.</strong>

<strong>Figure 1. Expanded PIC24 System Schematic</strong>

<h1>4.     TASK 2: Expanded PIC24 System Printed Circuit Board Layout</h1>

For this task we will create a printed circuit board layout from the PIC24 schematic created as a part of task 1. The board size should be 80mm x 80mm. The board part number should be “ECE383-LAB6” and the Revision Number should be “001”. These parameters can be set through the PCB wizard.

Use the <strong>Settings-&gt;Grids </strong>function to set the <strong>Working Grid </strong>and the <strong>Screen Grid </strong>to 1mm x 1mm. Use the

<strong>Settings-&gt;Coordinates </strong>function to set the Coordinate System Origin to the lower left corner of the board. Left click on the bottom edge of the board, press the “=” key and note the Y coordinate value. Left click on the left edge of the board, press the “=” key and note the X coordinate value. Enter the X and Y values for the Coordinate System Origin using the <strong>Settings-&gt;Coordinates </strong>function. This should set the origin to the lower left corner of the board as indicated by a ⊗ symbol. Another method for setting the system origin is to highlight an item (i.e. the bottom edge of the board), right click and select <strong>Origins-&gt;Set System Origin At Item</strong>.

We will create four mounting holes for this PCB using the <strong>Add-&gt;Board-&gt;Circle </strong>function. The diameter for each mounting hole should be 3mm and they should be placed in the four corners of the board with each hole being exactly 2mm from each edge of the board. Use the <strong>Tools-&gt;Measure </strong>function to assist you in this layout.

Each of the components should be placed in specific locations on the PCB. Highlight a component and press the “=” key. This will allow you to type in exact locations for the origins of each of the components. Table 1 gives the X and Y values for the location of each component in your design.

<table width="293">

 <tbody>

  <tr>

   <td width="136">Component</td>

   <td width="83">X location</td>

   <td width="75">Y location</td>

  </tr>

  <tr>

   <td width="136"><strong>PIC24 (U1)</strong></td>

   <td width="83">10</td>

   <td width="75">60</td>

  </tr>

  <tr>

   <td width="136"><strong>LM2937-3.3 (U2)</strong></td>

   <td width="83">70</td>

   <td width="75">65</td>

  </tr>

  <tr>

   <td width="136"><strong>SW1</strong></td>

   <td width="83">57</td>

   <td width="75">72</td>

  </tr>

  <tr>

   <td width="136"><strong>SW2</strong></td>

   <td width="83">47</td>

   <td width="75">72</td>

  </tr>

  <tr>

   <td width="136"><strong>SW3</strong></td>

   <td width="83">37</td>

   <td width="75">72</td>

  </tr>

  <tr>

   <td width="136"><strong>LED1</strong></td>

   <td width="83">70</td>

   <td width="75">44</td>

  </tr>

  <tr>

   <td width="136"><strong>LED2</strong></td>

   <td width="83">20</td>

   <td width="75">10</td>

  </tr>

  <tr>

   <td width="136"><strong>LED3</strong></td>

   <td width="83">30</td>

   <td width="75">10</td>

  </tr>

  <tr>

   <td width="136"><strong>LED4</strong></td>

   <td width="83">40</td>

   <td width="75">10</td>

  </tr>

  <tr>

   <td width="136"><strong>LED5</strong></td>

   <td width="83">50</td>

   <td width="75">10</td>

  </tr>

  <tr>

   <td width="136"><strong>R1</strong></td>

   <td width="83">24</td>

   <td width="75">30</td>

  </tr>

  <tr>

   <td width="136"><strong>R2</strong></td>

   <td width="83">9</td>

   <td width="75">68</td>

  </tr>

  <tr>

   <td width="136"><strong>R3</strong></td>

   <td width="83">30</td>

   <td width="75">30</td>

  </tr>

  <tr>

   <td width="136"><strong>R4</strong></td>

   <td width="83">36</td>

   <td width="75">30</td>

  </tr>

  <tr>

   <td width="136"><strong>R5</strong></td>

   <td width="83">42</td>

   <td width="75">30</td>

  </tr>

  <tr>

   <td width="136"><strong>R6</strong></td>

   <td width="83">48</td>

   <td width="75">30</td>

  </tr>

  <tr>

   <td width="136"><strong>C1</strong></td>

   <td width="83">64</td>

   <td width="75">67</td>

  </tr>

  <tr>

   <td width="136"><strong>C2</strong></td>

   <td width="83">6</td>

   <td width="75">33</td>

  </tr>

  <tr>

   <td width="136"><strong>C3</strong></td>

   <td width="83">22</td>

   <td width="75">33</td>

  </tr>

  <tr>

   <td width="136"><strong>C4</strong></td>

   <td width="83">71</td>

   <td width="75">56</td>

  </tr>

  <tr>

   <td width="136"><strong>C5</strong></td>

   <td width="83">22</td>

   <td width="75">54</td>

  </tr>

 </tbody>

</table>




<strong>Table 1. Expanded PIC24 System Component Locations.</strong>




Use your experience from previous labs to create a PCB similar to the diagram shown in Figure 2 below. After the PCB has been completed, use <strong>Tools-&gt;Design Rule Check </strong>to verify the design passes all the basic electrical design rules checks built into PCB Artist. Checking the <strong>Spacing</strong>, <strong>Nets </strong>and <strong>Manufacturing </strong>checkboxes should ensure all design rule checks are performed. The design rule check file created should indicate “No errors found” under the Results section if all design rule checks successfully pass. Generate a bill of materials CSV by running the <strong>Output-&gt;Reports-&gt;User Reports-&gt;bill of materials CSV </strong>report. This report

should list all components in the design. Include the report output in an appendix of your lab report.

Generate  a   component  positions   report   by   running   the   <strong>Output-&gt;Reports-&gt;User  Reports-</strong> <strong>&gt;component positions cvs </strong>report. This report should list the exact positions of all components in the design. Include the report output in an appendix of your lab report. Note that the positions reported may differ slightly from the location values from Table 1. They will only be identical if the center of the component is also the origin for that component.




<h2>Figure 2. Expanded PIC24 System Printed Circuit Board</h2>




<strong>TA check</strong>: <strong>Upon entering the lab, show the TA the printed circuit board you completed. Include a printout of your PCB in your lab report.</strong>




<h1>5.     TASK 3: A Basic LED Problem</h1>




This task will require you to write a C program to implement a basic LED problem. Perform the following steps:




<ul>

 <li>Start the MPLAB IDE. Use <strong>Project-&gt;Project Wizard </strong>for the creation of an MPLAB project.

  <ul>

   <li>Step One: Select the device <em>PIC24H128GP502 </em>for the MicroStick II. o Step Two: Select the Active Toolsuite as <em>Microchip C30 Toolsuite</em>.</li>

   <li>Step Three:  <em>Create  a  New  Project  File  </em>in  a  unique  directory  on  the  local  hard  disk (<em>C:temptask3a.mcp </em>as an example).</li>

   <li>Step Four: Skip the addition of existing files to the project. After the project is open, use <strong>Project-&gt;Build Options </strong>to add the <em>C:microchiplibinclude </em>directory to the <em>Include Search Path </em></li>

   <li>Step Five: Configure the clock source for the processor. Select <em>Configure-&gt;Configuration Bits… </em>Uncheck the “Configuration Bits Set in code” checkbox. Change to FNOSC filed by clicking on the “Setting” area showing “Internal Fast RC (FRC) with divide by N”. Change the setting to “Internal Fast RC (FRC) w/ PLL”. Recheck the “Configuration Bits Set in code” checkbox.</li>

  </ul></li>

 <li>Enter the C program below and save it with the name <em>c </em>as a part of the project.</li>

</ul>




#include “pic24_all.h”

#if <u>__</u>PIC24HJ128GP502<u>__</u>

#define LED1 _LATA0     // MicroStick II definitions

#define CONFIG_LED1() CONFIG_RA0_AS_DIG_OUTPUT() #endif




int main(void) {

CONFIG_LED1(); LED1=0;

while (1) {              // Infinite while loop

LED1 = !LED1;       // Toggle LED1

DELAY_MS(100);      // Delay 100ms

} return 0;

}

<ul>

 <li>Use <strong>Project-&gt;Add Files to Project </strong>to add the following files to your project:</li>

</ul>

o C:microchiplibcommonpic24_clockfreq.c o C:microchiplibcommonpic24_serial.c o C:microchiplibcommonpic24_uart.c o C:microchiplibcommonpic24_util.c

<ul>

 <li>Compile the project by selecting <strong>Project-&gt;Build All</strong><em>.</em></li>

 <li>Enable the MPLAB IDE debugger by selecting <strong>Debugger-&gt;Select Tool-&gt;Starter Kit on </strong></li>

</ul>

<strong>Board </strong>for the MicroStick II.

<ul>

 <li>Download your code into a device on the board by selecting <strong>Debugger-&gt;Program</strong>. (Note: This is an important step to follow. Do not just click <strong>Run </strong>because it will run the previous program in the PIC24 memory. Every time, you edit the code. Build first, and then click <strong>Program</strong>).</li>

 <li>Run the application by selecting <strong>Debugger-&gt;Run</strong>. This should toggle an LED on the PIC24 board.</li>

</ul>




<strong>TA check</strong>: <strong>Show the TA the operation of the flashing LED program.</strong>




Using the procedure described above, create a new project (task3b.mcp), containing a C program (task3b.c). This program should alternate the rate at which the LED should toggle. The program should toggle the LED at a rate of 10 times per second for 5 seconds then change to 5 times per second for another 5 seconds. The process should then repeat. Use a variable that keeps track of elapsed time by counting the number of times the DELAY_MS() function is executed.




<strong>TA check</strong>: <strong>Show the TA the operation of the modified flashing LED program. </strong>

<strong> </strong>




<h1>6.     TASK 4: Software-Based Finite State Machine for LED/Switch I/O</h1>




For this task you use the MicroStick II and the breadboard and interface the following components. Two pushbuttons will be connected to RB12 and RB14 similar to the schematic created in Task 1. You will use the pushbuttons purchased as a part of your lab components. Two LEDs will be connected to RB1 and RB15. Resistors (910 ohm) should be connected to the cathode of each LED. The other terminal of the resistor should be connected to a Vss (GND) pin of the PIC24, which is either pin 19 or 8. The constructed circuit should resemble the circuit shown in Figure 3. Note: All power will be provided to the PIC24 system via the USB cable.

Implement the following LED/Switch I/O problem:

<ol>

 <li>Turn on LED1 (RB15). On a press and release of pushbutton SW1, turn off the LED1 and go to step 2.</li>

 <li>After a press and release of a pushbutton (SW1), blink LED1 two times and the freeze the LED1 on.</li>

 <li>After a press and release of a pushbutton (SW1), if SW2 = 0, go to (1), else go to the next step.</li>

 <li>When the pushbutton (SW1) is pressed and <u>held down</u>, blink LED2 five times per second. LED2 should be off if SW1 is not pressed. After the <strong>second release</strong>, go to (5).</li>

 <li>Blink LED2 rapidly (twice as fast as step 4). On press and release of the pushbutton (SW2), go to (1).</li>

</ol>

Your first task should be to determine the states required and construct an <strong>ASM chart</strong> for implementing your assigned LED/switch I/O problem.




Create an MPLAB project <em>task4.mcp</em> and the corresponding C program <em>task4.c </em>to implement the finite state machine. Download your code to your PIC24 system and test the operation of your software design using the debugging capabilities of MPLAB and the Microstick II.




<strong>TA check</strong>: <strong>Show the TA your ASM chart and that your LED/switch code functions as expected. </strong>




<strong>Figure 3. Task 4 schematic </strong>

<strong> </strong>

<strong> </strong>

<h1>7.     TASK 5: Variable Rotating LED</h1>




For this task, you will implement a rotating LED program using the RGB LED interfaced with the PIC24 system. RGB (Red-Green-Blue) LEDs are actually three LEDs in one. Most RGB LEDs have four pins: one for each color and a common cathode pin. In this task, you will use a common cathode RGB LED which is shown in Figure 4. The data sheet link: <a href="http://www.kingbrightusa.com/images/catalog/SPEC/WP154A4SUREQBFZGC.pdf">http://www.kingbrightusa.com/images/catalog/SPEC/WP154A4SUREQBFZGC.pdf</a>




<strong>                           Figure 4. Common Cathode RBG LED</strong>




In this task, you are required to control the RGB LED using both binary codes and gray codes. Since there are only 3 leds in one RGB LED, we only consider binary codes and gray codes with 3-bits. Table 2 shows each 3-bit binary code and its corresponding gray code.




<table width="730">

 <tbody>

  <tr>

   <td width="82">Binary</td>

   <td width="81">000</td>

   <td width="81">001</td>

   <td width="81">010</td>

   <td width="81">011</td>

   <td width="81">100</td>

   <td width="81">101</td>

   <td width="81">110</td>

   <td width="81">111</td>

  </tr>

  <tr>

   <td width="82">Gray</td>

   <td width="81">000</td>

   <td width="81">001</td>

   <td width="81">011</td>

   <td width="81">010</td>

   <td width="81">110</td>

   <td width="81">111</td>

   <td width="81">101</td>

   <td width="81">100</td>

  </tr>

 </tbody>

</table>

<h2>Table 2. Three-bit Binary Code and Gray Code</h2>

<strong> </strong>

You are required to write a function in C which converts a binary code to its corresponding gray code. The input parameter of this function is a char type data which represents a binary code while the output is the gray code also in data type char. There are numerous methods for this conversion process. One possible approach is by bit shifting and an XOR operation. One example is given below.




<u>Example:</u>

Suppose we want to convert binary code ‘010’ to gray code ‘011’.

Step 1:                                                00000010

Step 2:                                                <strong><u>0</u></strong>0000001      (shift the code to right by 1bit, system would add <strong><u>0</u></strong> to last digit)

Step 3:                                                00000011      (XOR)




Once the code convert function is written write a program that implements the functionality given in Table 3 below.




SW1                      SW2                                                     Y location




<table width="642">

 <tbody>

  <tr>

   <td width="139">Not pressed</td>

   <td width="101">Not pressed</td>

   <td width="402">Turn on all LEDs (R,G,B) </td>

  </tr>

  <tr>

   <td width="139">Not pressed</td>

   <td width="101">Pressed</td>

   <td width="402">Repeatedly display binary code from ‘000’ to ‘111’ on RGB LED with each combination on for 0.5 sec</td>

  </tr>

  <tr>

   <td width="139">Pressed</td>

   <td width="101">Not pressed</td>

   <td width="402">Repeatedly display gray code from ‘000’ to ‘100’ on RGB LED with each combination on for 0.5 sec</td>

  </tr>

  <tr>

   <td width="139">Pressed</td>

   <td width="101">Pressed</td>

   <td width="402">Blink the RGB led (all three colors) at the rate of 10 times per second</td>

  </tr>

 </tbody>

</table>




<h2>Table 3. Task Five Program Functionality</h2>




Name the project task5.mcp and the corresponding C program task5.c. Download your code to your PIC24 system and test the operation of your software design. <u>Note that all the gray codes must be converted from the</u> <u>binary code instead of coming from Table 2 directly. </u>

The constructed circuit should resemble the circuit in Figure 5.

<strong>                                                                                                  </strong>

<strong> </strong>Figure 5. Task 5 schematic

Provide answers to the following questions in your lab report.




<ol>

 <li>What are the advantages of binary codes and gray codes respectively?</li>

 <li>Can we convert a gray code value back to binary code? If the answer is yes, please describe one possible method. Otherwise please explain the reason.</li>

</ol>

<strong> </strong>

<strong>TA check</strong>: <strong>Show the TA that your program functions as expected. </strong>