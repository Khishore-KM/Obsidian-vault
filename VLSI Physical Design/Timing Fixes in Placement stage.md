

###### Types of Timing Violation:
- Setup Timing violation.
- Hold Timing Violation.


CLK Uncertainty -> skew + jitter.

setup time -> MAX constrain.
Hold Time -> MIN constrain.

*Timing violation will occur only when the arrival time AT > Required Time RT*



![[Timing violations.png]]



*Setup Time depends on the clock and the hold time only depends on the uncertainty.*

RT = Tuncertainity + Thold.

Hold = AT -RT.

##### Common setup fixes:
- Break the net(insert a buffer).
- Split the load and reduce the capacitance.
- Clone the cell to split fanout.
- Upside the cell to increase drive strength.
- Vt swap to a lower vt cell.

##### Common hold fixes:
- Downsize the cell.
- Vt swap to a higher vt cell.
- Insert buffer at endpoint to increase the data path delay.


![[Concurrent Clock and Data Optimization.png]]


Interview Question:
