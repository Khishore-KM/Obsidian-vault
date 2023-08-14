![[Scan Chain.png]]


 ![[Scan chain opt.png]]

 ##### Cell Density of Standard cells:
 if cell density is high then we will face route ability issues. Sometimes this may cause timing will be good.
if high cell density this may lead to routing congestion to avoid that we can spread the cells and spreading will reduce clumping density.



*Higher cell density leads to less availability of resources, because most of lower layer resources would already be consumed by cells*

##### CMOS Latchup:

![[Latch up.png]]


 *the latch-up issue can be defined as a formation of a direct path from VDD to GND terminal in the design, which will cause a huge current flow between the power and ground terminal*


Inside a CMOS circuit two parasitic BJT get formed and connected in such a way that these BJT form a PNPN device or SCR or Thyristor.


Both the BJTs are connected in such a way that they form a PNPN device.

*Technically latch-up is the phenomena of activating the parasitic BJTs in a CMOS circuit which forms a low impedance path between the power and ground terminals. This low impedance path draws a large current and heats up the IC (Integrated Chip) which cause permanent damage of IC.*

##### Reasons for Latchup:
- Noise at the output terminal.
- Electrostatic Discharge.
- Ionizing radiation.


[[Well Tap cell]]