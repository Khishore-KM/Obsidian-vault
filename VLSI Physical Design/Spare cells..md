Spare cells generally consist of a group of standard cells mainly inverter, buffer, Nand, nor, and, or, exor, mux, flip flops and maybe some specially designed configurable spare cells. Ideally, spare cells do not perform any logical operation in the design and act as a filler cell only.

![[Spare cells.png]]


The inputs of spare cells are tied either VDD or VSS through the tie cell and the output is left floating.
Input cannot be left floating as a floating input will be prone to get affected by noise and this could result in unnecessary switching in space cells which leads to extra power dissipation.

##### Use of spare cells:
Spare cells enable us to modify/improve the functionality of a chip with minimal changes in the mask. We can use already placed spare cells from the nearby location and just need to modify the metal interconnect. There is no need to make any changes in the base layers. Using metal ECO we can modify the interconnect metal connection and make use of spare cells. We only need to change some metal mask, not the base layer masks.

##### Placement of Spare cells:
Spare cells can be added either by the netlist or by PnR tool command (or GUI too). In Physical design, we prefer to add the spare cells using tool command. These cells are added before the placement of standard cells throughout the design.


https://teamvlsi.com/2020/08/spare-cells-in-physical-design.html#:~:text=Spare%20cells%20generally%20consist%20of,as%20a%20filler%20cell%20only.