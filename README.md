## Design & Implementation-Of-Full-Custom-8-1-Multiplexer-Using-Cadence-EDA-Tools

### Abstract:
&emsp;&emsp;This project focuses on the design and simulation of an 8x1 multiplexer (MUX) implemented using basic logic gates (AND, OR, and NOT gates) in Cadence Virtuoso. An 8x1 MUX allows one of eight input signals to be selected and passed to the output based on the values of three select lines. The design was created using a combination of AND gates to select inputs, OR gates to combine the selected signals, and NOT gates to invert select lines as needed. The functionality of the MUX was verified through schematic simulations, and the design successfully meets the required performance and logical correctness.

### Tools Required:

  + Personal Computer
  + Cadence Virtuoso Software

### Circuit Diagram:

![image](https://github.com/user-attachments/assets/a468545a-a3ae-455b-866a-a2def51ae6b5)

### Circuit Description:

&emsp;&emsp;The 8x1 multiplexer uses basic logic gates to implement the selection of one of eight input signals based on three control (select) lines. Here’s how the design works:

#### Key Components:

  + Inputs (I0 to I7): These are the eight data inputs, from which one will be selected based on the state of the select lines.
  + Select Lines (S0, S1, S2): Three select lines determine which input (I0 to I7) is connected to the output. The binary combination of the select lines corresponds to one of the eight inputs
  + Output (Y): The output carries the value of the selected input.

#### Gate-level Implementation:

The MUX works as follows:

   - Inverters (NOT gates): The select lines (S2, S1, S0) are inverted using NOT gates to generate complementary signals (S2', S1', S0') for the AND gates.

   - AND Gates: The AND gates are used to "select" each input. Each input (I0 to I7) is connected to a unique AND gate, which also receives the select lines and their
    complements as inputs:
       + For instance, for input I0, the AND gate receives S2′S2′, S1′S1′, and S0′S0′ as inputs to select I0.
       + Similarly, for I1, the AND gate receives S2′S2′, S1′S1′, and S0S0, and so on for all inputs.

   - OR Gate: After the AND gates select the inputs, the outputs of these gates are fed into a single OR gate. The OR gate then combines the selected signals and produces the final output Y.

This approach effectively "routes" one of the eight inputs to the output based on the state of the select lines.

### Schematic Simulation: ( Commands to Open Cadence )

  - Right-click and open the terminal window.
  - Enter the following commands:
      + csh
      + source /cadence/install/cshrc
      + virtuoso

#### Steps for Creating an 8-Bit Multiplexer (MUX)

1. Creating a New Library

   + Go to the main Virtuoso window (CIW).
   + Navigate to File > New > Library.
   + Name the library, for example, "VLSILAB_MUX_EXP".
   + Enable Attach to an existing technology library, then click OK.
   + Select the technology library (e.g., gpdk045) and click OK.

2. Creating the Schematic for 8-Bit MUX Cell View

   - In the Virtuoso window, go to File > New > Cell View.
   - Set up the new file form with:
      + Library: Choose the library you created.
      + Cell: Name it, for example, "MUX8bit_Schematic".
      + Type: Select "Schematic" and press OK.

Adding Components

  - Use the shortcut key I (or go to Instance > Add).
  - In the Library Browser, add the required components:
      + Multiplexer logic gates (e.g., AND, OR, NOT) to construct the MUX logic.
      + Input and Output pins to represent the 8-bit inputs and outputs.
  - Make connections between the components using the wire tool.
    
![Screenshot (86)](https://github.com/user-attachments/assets/a1007542-65de-4536-8378-4d91e0ec04f4)

![Screenshot (87)](https://github.com/user-attachments/assets/3d9bee47-979c-4bb1-8d4c-c6be5633cd56)

<br>
<br>
<br>
<br>

![Screenshot (85)](https://github.com/user-attachments/assets/0048f4fc-0c32-4819-8509-1fed458ac923)


3. Creating a Symbol for the 8-Bit MUX Schematic

   - Go to Create > Cell View > From Cell View.
   - Ensure Lib Name, Cell Name, and From View are set to your schematic cell.
   - Click OK to open the Symbol Generation form.
   - Customize the symbol if desired.

![image](https://github.com/user-attachments/assets/e5a1c977-82d7-4df3-94a4-cee3a13f3d84)

<br>
<br>
<br>
<br>
<br>
<br>

4. Creating the Test Bench for the 8-Bit MUX

   - Go to File > New > Cell View in the Virtuoso CIW.
   - Set up the new cell view with:
       + Library: Choose your library.
       + Cell: Name it, for example, "MUX8bit_Test".
       + Type: Select "Schematic" and click OK.
   - In the test bench:
       + Instantiate the 8-bit MUX symbol you created.
       + Connect appropriate inputs, including an 8-bit data bus and control signals.
       + Set up input pins to simulate different input combinations.
   - Simulation and Testing

![Screenshot (83)](https://github.com/user-attachments/assets/4048865f-ba0a-4b7a-9b72-b33d0dffbbb8)

### Analog Simulation by Spectre

   - In the test cell view, go to Launch > ADE L (Analog Design Environment).

   - In ADE L:
       + Go to Setup > Simulation/Directory/Host, select Spectre as the simulator, and click OK.
       + Select Analysis > Choose, then select Transient or DC Analysis to define the simulation parameters.

<br>
<br>

   - For output plotting:
       + Choose Outputs > To be Plotted > Select on Schematic.
       + Select the MUX output pin to observe the final output waveform.

   - Run the simulation by choosing Simulation > Netlist and Run.

![Screenshot (84)](https://github.com/user-attachments/assets/c3a2d34c-d4eb-4b92-8cb5-2c77d8fffc03)

### Transient Analysis

   - In ADE L, set the Analysis to Transient.
   - Define the start and stop times for the transient analysis.
   - Run the simulation to observe the output waveforms and verify the MUX operation.

![Screenshot (91)](https://github.com/user-attachments/assets/ed32ea7f-0897-475f-956e-32b4c36d7916)

<br>
<br>

### Output Results:

![Screenshot (82)](https://github.com/user-attachments/assets/3fe2242f-0fee-4700-a6b3-75de9cac654a)

![Screenshot (81)](https://github.com/user-attachments/assets/b90c8903-5c2a-438e-97c3-c08e60dc46e9)

<br>

### Application:

The 8x1 multiplexer designed using logic gates has a wide range of applications:

  1) **Data Routing in Digital Systems:** MUXes are used to select and route data in digital circuits and systems, including microprocessors and FPGAs.
  2) **Control Systems:** The MUX can be used to select between different control lines or sensor inputs, especially in embedded systems.
  3) **Communication Systems:** In telecommunications, MUXes can be used to select data signals from multiple sources for transmission over a single channel.
  4) **Memory Systems:** MUXes are used to select memory locations or to multiplex address/data buses in memory circuits.
  5) **Signal Switching:** MUXes are used in switching applications where the need exists to select one signal from many, such as in audio processing or video signal routing.
  6) **Test and Debugging:** MUXes can also be used in testing and debugging systems to isolate and route signals to a specific output.


### Conclusion:

&emsp;&emsp;The design and simulation of the 8x1 multiplexer using basic logic gates (AND, OR, NOT) in Cadence Virtuoso was successfully completed. The MUX correctly selects one of eight inputs based on three control lines, with the circuit performing as expected in simulations. This design demonstrates a simple yet efficient method for routing digital signals, suitable for applications in data selection, control systems, and communication networks. Future work can focus on optimizing the design for power and speed, or scaling it to larger multiplexers for more complex systems.
