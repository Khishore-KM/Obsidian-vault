

##### CTS Algorithms:
- RC Tree based CTS.
- H Tree based CTS.
- Pi Configuration.
- Fishbone Structure.



##### Spec file:
- Inv & Buffer (CTS)
-> set_lib_cell_purpose
        - exclude - all lib cells
        - include - only list of buf/inv
- CTS exceptions 
-> List of endpoints(FF clk pin)
- Skew Group.
- Target-> Skew Target
-> Latency -> Transition.
-> Capacitance.
- min/max layer. > set_routing_layer.
- NDR(Non Default Rules) -> Prone to noise
- Generated and virtual clocks.


Skew in VLSI is the difference in clock arrival time across the chip. Clock Skew in VLSI is the temporal difference between the arrival of the same edge of a clock signal at the Clock pin of the capture and launch flops.   Signal  takes time to move from one location to another. Clock latency is the time taken by a clock signal to  move from the clock source to the clock pin of a particular flip-flop. Clock skew can alternatively be defined as the difference between capture and launch flop delay.

For example, The capture clock delay is 2.5ns while the launch clock latency is 0ns. The difference between them is 2.5ns-0ns = 2.5ns, which is the clock skew value.

## Skew values for pre-CTS and post-CTS:

Clock skew in VLSI is part of the uncertainty at the pre-CTS stage. The clock should ideally reach the clock pin of all the flip-flops in a design at the same time, resulting in a zero skew. However, this is not attainable owing to varying wire-interconnect lengths and temperature changes.

## What is the reason for skew in VLSI design?

A skew in a design occurs when a flip-flop is put near the clock source and another flip-flop is placed at the far end of the core region. In practice, the skew cannot be zero due to the disparity in connecting lengths. To address this, a user-specified number is provided to obtain correct pre-CTS timing data. After the clock tree is constructed, the real skew values are accessible, and the uncertainty is limited to the Jitter value alone.

### Local Skew and Global Skew in VLSI:

The disparity in latency between two related flops in a design is referred to as local skew. Global skew is the difference in clock delay between two unrelated flops or the difference between the longest and shortest clock paths in the design.

### Positive and negative skew in VLSI:

Positive clock skew, In this case, the capture clock delay is greater than the launch clock latency. Positive skew is advantageous for setup timing. Due to the inclusion of skew, the capture clock is delayed by a few ns. Therefore the timing path requires  one clock period and Skew margin to match the setup requirement.

Negative Skew is beneficial for hold time since it delays the fresh launch. Because of the delay in launching the new data, the prior data will be effectively recorded and will not be overwritten. However, negative skew is detrimental to setup timing.

### Useful Skew:

Useful skew in VLSI is the skew that is purposefully introduced into the design to satisfy timing. It is particularly introduced in clock pathways where timing is failing, so that timing is passed in that path. However, useful skew cannot be applied arbitrarily. This must be done with caution, ensuring that the margin is accessible in both the preceding and subsequent time paths. The uncontrolled insertion of skew might result in further timing violations rather than resolving them. It may be used to correct both setups and hold errors.

### Harmful Skew in VLSI:

While introducing some skew to the failed pathways might aid in the resolution of timing violations, too much distortion can result in violations. If a large positive skew is introduced into the design, the capture clock will arrive late, and if the data path delay between the two flops is small, the data may reach the D pin of the capture flop even before the capture edge reaches the clock pin of the capture flop. This overwrites the previously latched data, resulting in a Hold violation. If a significant negative is included in the design, the clock edge will arrive at the capture flop before the launch flop. Hence, too much skew can cause violations that lead to harmful skew

##### Float Pin:
Float pins are clock pins that have special delay insertion requirements and balancing is done according to the delay. This is same as sync pin but internal clock latency of the pin is taken into consideration while building the clock tree.
To adjust the clock arrival for specific endpoints with respect to all other endpoints.


![[Float pin.png]]



##### Stop pin:


![[Stop pin.png]]


Stop pins are endpoints of clock tree that are used for delay balancing in CTS, the tool uses stop pins in calculation & optimization for both DRC and clock tree timing.

The optimization is done only upto the stop pin. The clock signal should not propagate after reaching the stop/sync. This pin needs to be considered for building the clock tree.

