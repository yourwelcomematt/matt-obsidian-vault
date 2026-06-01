What is electricity?
- Electricity is the flow of electrons
- Voltage
	- The pressure of electrons flowing from a power source through a wire (like water pressure)
	- Measured in volts (V)
	- Determined by the power source
- Current
	- The flow rate of electrons through a wire (i.e., how many electrons can flow through a wire)
	- Measured in amperes (I)
- Resistance
	- The "resistance" of a material to the flow of electrons
	- Higher resistance = less flow and decreased current
	- Lower resistance = more flow and increased current
	- Different materials have different resistances
	- Measured in ohms (r or omega)

Alternating current (AC) electricity
- Where the direction that the current is travelling in alternates
- Comes from wall outlets
- Powers big appliances like fridges and stoves
- Can be converted to DC
	- E.g., a phone charger will convert AC to DC to charge the phone's battery

Direct current (DC) electricity
- Where the current always travels in the same direction
- Comes from batteries
- Powers small electronic devices like phones and computers
- Can be converted to AC

Circuit
- Involves connecting the positive and negative terminals of a battery together, allowing current to flow and components connected along the way to be powered
- Current always flows from negative to positive
- An open circuit is where there's a gap in the circuit
- A closed circuit is a complete circuit with no gaps

Resistors
- Increase resistance in a circuit
- Used to reduce voltage to other components so that they don't break
- It does this by removing the extra voltage provided by the power source
- The coloured bands on a resistor tell us how much resistance it is adding

Light-emitting diodes (LEDs)
- Like little light bulbs
- Usually require a resistor in the circuit to reduce the current from a 9v battery (unless they have a built-in resistor)
- Have two metal legs:
	- Longer leg is called the anode, and must be connected to the positive side of the circuit (i.e., the side with the positive terminal)
	- Shorter leg is called the cathode, and must be connected to the negative side of the circuit (i.e., the side with the negative terminal)

Calculating the required resistance for a component to work
- Values you need to know:
	- The voltage (V) of the power source
	- The forward voltage of the component, which is the voltage required to get current to flow across it
	- The required current for the component
- E.g., for an LED powered by a 9v battery:
	- The voltage of the power source is 9v
	- The forward voltage and required current of the component can be found in the manufacturer's data sheet
- Formula to calculate resistance is R = (power source voltage - forward voltage) / required current
- Ideally you would use a resistor that matches the calculated resistance value, but you can be slightly over or under and still be fine

Required tools
* Needle-node pliers
* Bread boards
	* Used to cleanly prototype circuits
* Cables
* Multimeter
	* Used to measure various electricity-related values in a circuit (e.g., voltage, current, and resistance)
	* Auto-ranging multimeter is recommended
	* Has two probes which can be connected to a circuit to take measurements
	* Can be used to diagnose issues in a circuit

Schematic
- A blueprint of a circuit that you want to build
- Despite electrons actually flowing from negative to positive, schematics use conventional flow, where electricity flows from positive to negative

Switches
- Controlled way of opening or closing a circuit
- It doesn't matter which side of the circuit a switch is placed on, but the convention is to put it closer to the positive terminal of the power source
- A single pole single throw (SPST) switch opens or closes a single circuit
- A single pole double throw (SPDT) switch opens one circuit and closes another at the same time, and vice versa
- A double pole single throw (DPST) switch opens or closes two circuits simultaneously in an identical manner
- A double pole double throw (DPDT) switch is like a SPDT except doubled and occurring simultaneously

Measuring with a multimeter
- Voltage
	- Touch the probes to the leads of the component you want to measure
	- Red = positive side
	- Black = negative side
- Current
	- Be aware of the maximum current your multimeter can handle, as exceeding this can damage it
	- Start off with the highest-reading receptacle if you don't know what the current in your circuit will be
	- To measure current, the multimeter must become part of the circuit

Ohm's Law
- V = IR
- I = V/I
- R = V/I

Power
* The rate of energy usage or work being done
* Measured in watts (W)
* Larger resistors have a higher wattage
* P = VI

Series and parallel circuits
* Series
	* Where there's only one path that current can flow along
	* Involves connecting all components one after the other
	* Current (I) is the same at all points of the circuit, whereas voltage (V) differs
	* Total resistance is the sum of all resistance in the circuit, and as such will increase as resistors are added, resulting in a decrease in current
	* Major disadvantage is that if one component fails, the circuit breaks
* Parallel
	* Where there are multiple paths that current can flow along
	* Current (I) differs at different points of the circuit, whereas voltage (V) remains the same
	* Total resistance decreases as resistors are added, resulting in an increase in current
	* Major advantage is that if one component fails, the other components along the other paths will continue to work

Buttons
- Simple button with two leads:
	- Connection is open when the button is not pushed down
	- Connection is closed when the button is pushed down
- Tactile buttons are good for prototyping and breadboards

Potentiometers
- Three terminals attached to a casing with a turnable knob or screw on the top
- Essentially a variable resistor, where the resistance depends on what position the knob or screw is in
- Outer two terminals are connected together within the potentiometer by a resistive strip
- Middle terminal is connected to a wiper, which is moved along the resistive strip by the turnable screw or knob, giving us a connection to somewhere along the strip
- If the wiper is at 9 o'clock and there are connections to the left and middle terminals, then electricity doesn't have to travel far to reach the wiper and middle terminal (i.e., less resistance), whereas if there are connections to the middle and right terminals, then electricity has to travel far to reach the wiper and middle terminal (i.e., more resistance)
- As such, you only need at least two terminals to be connected for a potentiometer to work - either the left and middle terminals or the middle and right terminals
- Connecting the outer terminals will provide maximum resistance and remove the variable aspect, as the middle terminal connected to the wiper which provides this is not being used

Capacitors
- Temporarily store electrical charge, kind of like mini batteries
	- Consist of two neutral conductive layers separated by a non-conductive layer that acts as an insulator
	- When connected to a power source, positive charge accumulates on one side and negative charge on the other (electrons move to this side leaving positive ions on the other side)
	- When disconnected from the power source and then connected to a circuit, charge flows from the negative side, through the circuit, and to the positive side to restore neutrality in the conductive layers
	- RC time constant (Tau) is the number of seconds it takes for a capacitor to reach 63% charge, and is calculated using resistance x capacitance
	- A capacitor is usually able to reach 98% charge after four RC time constants
- Have a voltage rating, which means they shouldn't be placed in circuits with a voltage greater than this
- Have a capacitance rating, which is measured in Farads (F)
	- Most capacitors we use have values in the microfarads or nanofarads
- Electrolytic capacitors
	- Most common
	- Have an anode (longer lead) and a cathode (shorter lead)
- Ceramic disc capacitors
	- Second-most common
	- Not polarised, meaning either lead can be connected to either side of the circuit
- Poly film capacitors
	- Not polarised
- Polarised capacitors are drawn differently to non-polarised capacitors in schematics

Diodes
- Only allows current to flow in one direction
- Forward bias operating mode
	- Anode is connected to positive side, cathode is connected to negative side
	- Allows current to flow from positive to negative, while blocking any backwards flow
	- When placed right after a power source, it can be used to protect the rest of the circuit if the power source is accidentally connected in reverse, as it will block the incorrect flow
- Reverse bias operating mode
	- Anode is connected to negative side, cathode is connected to positive side
	- Doesn't allow current to flow from positive to negative
- Has:
	- Voltage limit (maximum circuit voltage it can handle before breaking down)
	- Voltage drop (amount of voltage it uses or takes away from the circuit)

Relays
- An electronically-operated switch
	- Contains an electromagnet with it's own positive and negative terminals, as well as one or more switches with their own positive and negative terminals
	- When electricity is run through the electromagnet, it powers on, which causes the switch to move and close it's part of the circuit, allowing electricity to flow across it
- Comes in the same variants as switches (e.g., single pole single throw, single pole double throw, double pole single throw, double pole double throw)
- Always drawn in their off position
- Useful in logic gates

Transistors


 



