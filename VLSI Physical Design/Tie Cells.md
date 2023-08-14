##### What is a Tie cell?
The **tie cell** is a standard cell, designed specially to provide the high or low signal to the input (gate terminal) of any logic gate. The high/low signal can not be applied directly to the gate of any transistors because of some limitations of transistors, especially in the lower node.

##### Need for Tie Cells:
In the lower technology node , the gate oxide layer under the poly gate is very thin and most sensitive part of the transistor. We need to take special care of this thin gate oxide while fabrication as well as in operation too.
If the polysilicon gate directly connects to VDD or VSS for a constant high or low input signal and in case any glitch arises it will result in damage of sensitive gate oxide.
To avoid this direct connection Tie cell is used to connect the input of any logic to VDD or VSS.

##### There are two types of tie cells.

- Tie-high cell
- Tie- low cell

![[Tie Cell.png]]


#####                                                  Schematic of Tie Cell


##### Placement of Tie Cells:

Tie cells are not present in the synthesized netlist and not placed in the initial placement of standard cell. Tie cells are inserted in the placement stage and more specifically at the final stage of placement . Where ever netlist is having any pin connected to 0 logic or 1 logic.


https://teamvlsi.com/2021/08/tie-cells-in-physical-design.html#:~:text=A%20tie%20cell%20is%20used,to%20the%20VDD%20or%20VSS.&text=There%20are%20two%20types%20of%20tie%20cells.&text=As%20the%20name%20suggests%2C%20the,cell's%20output%20is%20always%20low.