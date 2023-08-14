
##### Sanity checks:
- Netlist related checks.
- SDC checks.
- Netlist vs SDC.
- Linking related checks.

##### Netlist related checks:
- output should not be tied to ground.
- inputs should not be floating.(glitches in signal, functionality issues, dynamic power consumption)
- No multi driver nets in design

![[Sanity check.png]]

- Combinational feed back should not be present in the design.

![[Sanity Checks.png]]


##### SDC related checks:
- IO delays should be proper.( set_input_delay, set_output_delay)
- Unconstrained endpoints.
- No clk reaching to FF clk pin.
- No multidriven nets(clk).
- Input transition and output load defined on all input and output ports.

##### Linking related checks:
- Cell is not defined in the LEF(No physical view available for the cell).
- Missing dimension.
- Missing direction.
- Missing geometrics.
- missing .lib views and timing views
- Missing timing arc.
- Missing transition or capacitance value.
- Unconnected ti high and ti low terminals.
