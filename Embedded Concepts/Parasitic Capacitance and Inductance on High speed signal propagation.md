#### What is parasitic Capacitance and inductance?
Parasitic capacitance and inductance are unavoidable elements that exist in any electronic circuit. In high-speed hardware designs, these parasitic components 
can have a significant impact on signal propagation and integrity

##### Parasitic Capacitance:
In high speed designs, parasitic capacitance arise between conductive elements
such as traces or planes in PCBs made for high speed designs.
The presence of capacitance can cause signal to slow down as it charges and discharges the capacitive elements. This leads to signal distortion, increased rise and fall times and potential timing errors.
The presence of capacitance also form a low pass filter affecting the signals frequency response . It attenuates high frequency components causing signal loss and signals bandwidth.
Capacitive coupling between adjacent traces can result in crosstalk , signals from one trace interfere with neighboring traces leading to data corruption of false signal transitions.

##### Parasitic Inductance:
Conductive trace causes parasitic inductance.
Inductance can cause voltage drops and self induced magnetic field.
Inductive coupling can cause or occur between traces running parallel to each other.
The presence of inductance can cause resonance.


##### How to mitigate parasitic capacitance and inductance:

									- Careful PCB layout practices , such as minimizing trace lengths reducting the ditance between signal and return paths, and maintaining appropriate spacing between high speed traces.
									- Proper grounding and power distribution techniques.
									- Using controlled impedance transmission lines to reduce characteristic impedance.
									- Employing shielding techniques and ground planes.
									- Strateguc use of bypass capacitors and decoupling techniques.


