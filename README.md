# Design-and-Implementation-of-an-8-Bit-Multiplexer-Using-Cadence-EDA-Tools
## Aim:
  To design and implement an 8-bit multiplexer circuit using Cadence EDA tools, simulate its functionality, and understand its role in digital logic circuits.
## Tools Required:
  + Personal Computer
  + Cadence Virtuoso Software

## Schematic Simulation:
### Commands to Open Cadence:

  - Right-click and open the terminal window.
  - Enter the following commands:
      + csh
      + source /cadence/install/cshrc
      + virtuoso

### Steps for Creating an 8-Bit Multiplexer (MUX)
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

3. Creating a Symbol for the 8-Bit MUX Schematic

   - Go to Create > Cell View > From Cell View.
   - Ensure Lib Name, Cell Name, and From View are set to your schematic cell.
   - Click OK to open the Symbol Generation form.
   - Customize the symbol if desired.

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
     
### Analog Simulation by Spectre

   - In the test cell view, go to Launch > ADE L (Analog Design Environment).

   - In ADE L:
       + Go to Setup > Simulation/Directory/Host, select Spectre as the simulator, and click OK.
       + Select Analysis > Choose, then select Transient or DC Analysis to define the simulation parameters.

   - For output plotting:
       + Choose Outputs > To be Plotted > Select on Schematic.
       + Select the MUX output pin to observe the final output waveform.

   - Run the simulation by choosing Simulation > Netlist and Run.

### Transient Analysis

   - In ADE L, set the Analysis to Transient.
   - Define the start and stop times for the transient analysis.
   - Run the simulation to observe the output waveforms and verify the MUX operation.

### Results:

The 8-bit multiplexer was successfully implemented using Cadence tools. Simulation results confirmed the correct functionality of the multiplexer for different input selections, allowing the desired 8-bit input to be routed to the output based on the control signals.
