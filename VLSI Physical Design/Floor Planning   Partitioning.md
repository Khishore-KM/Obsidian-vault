Each logic gate that is implemented in the design is called as a standard cell and is enclosed in a box . Stick diagram is enclosed in the box.

Any instance and is other than the standard cell and is loaded as a black box 
This is called as Ip.
IP - RAM,ROM,PLL,ESD etc.
 ![[Floor planing.png]]
MANUFACTURING GRADE: // learn more about it.
// Utilization
// Side row.

Aspect Ratio - ratio of length to the width of the design.
Ratio between vertical routing resources and horizontal routing resources.

##### Utilization:
Utilization defines the area occupied by the standard cell , macros and blockages.

core util = std cell area / row area + channel area.

In soc level the IO ports are called as IO pads which is connected to outside world via bumps in soc or block level these IO ports are placed in the multiple metal layers
M-4 - 4th metal layer from the beginning.

##### Ports:
- Data.
- Clock.
- Power.
- Analog.
- digital.

Based on direction:
- input.
- Output.
- Bidirectional.

 Port Placement:
 - Ports are placed equal width and equal spacing.
 - NDR applied for clock ports.
 - No unplaced ports in the design.
 - Blockages applied or not in the empty area.
 - Guard rings.
 - innovers -> check pin assignment.
 - There shouldn't be any undriven ports or dangling ports.

Macros are hard IPs and are designed by the IP teams and these are optimized for power , performance and area.


![[Macro placement.png]]

                                    Visualization of the Macro

P - Power
P - Performance
A - Area

standard cell routing is done is m0,m1 or the m2 layer
But the macro routing can be done  in the higher metal layer.

##### Macro placement Tips:
- Macros should not block interface.
- Macros should not be placed incentre -> detour.
- Connection with respect to cells respect.
- Macro pins should not be blocked.
- Macro orientation in horizontal rotation.
- DFM rule(Design for manufacturability Rule)  90 degree or 270 degree not allowed only 0 and 180 degree is allowed.
- Macros should be on corner.
- Connections to fixed cells when placing macros.
- Reserve enough room for Io routing , Macros should not block IO paths.
- Macros pins should face core and not the boundary.
- The degree rotation of macros should be followed for maintaining substrate continuity.
- Macros are not timing critical with respect to the IO pins.


 ![[Tips for macro placement.png]]

##### Pitch:
Distance between two metal layers measured from Centre to Centre.


![[pitch distance.png]]


![[Placement density.png]]



##### Channel length:
               = no of pins x metal pitch/effective routing layers.



![[Macro guideline.png]]


##### Macro Placement Guidelines (Cont):
- Irregular shape of macros.
- Blockage in notch.
- Hard blocks.
- Soft blocks.
- Allow buffer only.
- Partial Blockage.


What is Halo? => keep out margin.


The types of cells in a design can be broadly classified in standard cells(AND/OR etc basically the logic gates), complex cells like adders, multipliers, macros (memories, thermal sensors, ADC, DAC etc), physical only cells(tap cells, halo cells etc)


Halos are placed around macros in a design. They do not allow the placement of any other standard cells around a macro till a certain boundary(like 0.1-0.2 microns) . They do not have any functionality associated with them. They have a few uses at different stages of the place and route , physical verification stages of Physical design Flow.

Uses of Halo in different stages of Fabrication:

##### Placement stage:  
All the physical only cells are fixed prior to the placement stage. When the floorplan stage runs, it freezes the macro placement and inserts the array of halo cells depending on the size of the macro.

- Halos on the adjacent macros can overlap and whenever a macro is moved the halos also move with it.

The standard cells available in the netlist are placed after allotting space for the physical only cells and setting the don’t touch attribute on the macros, physical only cells. So halos can be considered similar to hard blockages at placement stage.  
Routing stage:  
Generally a few layers from the macro will not be available for external signal routing like till metal layer 5, so the halos also have similar constraints. It can also be considered as a routing blockage for the particular area at this stage.

##### Physical Verification perspective:  
PV deals with making a design ready for manufacturing or tape-out. Cleaning up the DRV, LVS, ensuring uniform base and metal densities.  
Halos are useful for ensuring DRC cleanliness for the macros and the standard/complex/filler cells around them. The metal widths might vary between macro, standard cells. Like metal layer 2 width in macro might be 0.02 micron and in standard/filler/complex cells it might be 0.015 microns(even in the same foundry or process).

The macro and standard cells might belong to different manufacturing processes. Like the macro might be from some IP company like ARM and you are using a different foundry for tape out, in that case halos balance out the DRC around those macros and the surrounding cells.


##### Common macro placement issues:
- Congestion --> around macros, in channel spacing, no blockages in channel.
- Improper macro placement --> macro splitting , timing violations, congestion.
- Pin placement ensure good pin placement.


 
### Basic Floorplan

- **ROWS:** Rows are the locations where cells get placed. Rows can be core or IO. Rows are created at the floorplan stage.
- **SITE:** Sites are the minimum unit of placement. Rows are multiples of site definition. You can say that the smallest unit of placement where the smallest cell can be placed is called as SITE. This is technology dependent and obviously varies when technology changes.
- Floorplan is the process of deriving the die size, allocating space for soft blocks, planning power, and macro placement etc.
- We specify the floorplan by Size or Die/IO/Core Co-ordinates. We derive core and module sizes based on the standard cell utilization.
- Total density is calculated as:  
    _**Core Size= (standard cell area + macro area + halo) /standard cell utilization**_
- Standard Cell Density is calculated as:  
    _**Core Size= (standard cell area/standard cell utilization) + macro area + halo**_  
    Benefit: Generates more accurate core and module sizes.
- We define Core Size By or Die Size By, where core size by is defined by aspect ratio (Height/Width) and core utilization or dimension where we define height and width of core.
- We define core margin by Core to IO boundary or Core to Die boundary.
- Create physical shape of power domains which is defined in the UPF we have committed.
- Rows can be defined with different orientation as R0, MX, R0/MX Flip and abut, etc.