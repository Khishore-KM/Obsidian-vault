
![[Design flow.png]]


#### PHYSICAL DESIGN FLOW


##### Inputs given to physical design team?
- Netlist.
- Constrain file.(clock details, DRV/transition )
- LEF(Library Exchange Format, Physical Overview)
- LIB(use this lib for timing library timing view like clock , delays , propagation delay etc.)
- TF(Technology File, RC values, Spacing rules etc)
- ITF (Interconnect Parasitic File, Mapping file)
- List of Macros is provided as library.
- DEF(design Exchange Format)


 ##### What Does a netlist consist of?
 A net is a connection of two or more interconnected components and this is the textual 
 description of the circuit and the file extension is .v or .vg.
   This file will look like structural modelling file.

##### What is a timing library?

Standard cell library = physical + timing view.

How do we know delay through the gate in a logic path?
The delay is calculated using input transition and output transition.
This is given in the liberty format.
There will be cells for it and it is used for specifying delays.
NLDM - Non Linear Delay Model.
Here propagation delay is dependent on input transition and output load.
this is very fast in delay calculation.
Disadvantage: Accuracy will le lost below 130nm.
Finite number of transition values are taken in the input side and the output side.

Tool uses binary version(.ldb) of ascii format (lib)

CCS model (Composite Current Source Model)
Miller capacitance cannot be ignored.
Here propagation delay is not only dependent on transition and load but also additional parameter of time at which data is being sampled.


LEF (Library Exchange Format)
It contains the layout view of all the cells , this will mostly look like a stick diagram. 
This has very much less details.

##### Design Constrains:
- Design rule constrains.(Physical layout constrains, logical constrains(maximum capacitance, maximum transition))
- Optimization constrains.(timing constrains, exceptions, false path, multi cycle path, multi cycle path, input and output delays are mentioned, input and output transition of the ports and input and output load of the ports, dynamic or leakage power related constrains ) 

##### SDC File(Synopsis Design Constrain )


#### Refer about technology file it is also most widely used one.



#### DEF file:(Design Exchange Format):
- Provides detailed view of physical design.
- Generally used to represent physical structure of the design such as die, core and placement of cells, routes etc.

#### LEF(Library Exchange Format):
- Abstract view of physical design.
- Generally used to represent macros or any portion of the design which is black-boxed and we only see its top layer pins for access.


![[File model.png]]
