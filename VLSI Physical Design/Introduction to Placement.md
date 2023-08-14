
 ##### Quality Checks:
 - IO ports placed and fixed.
 - Macro placement should be fixed.
 - Row creation should be done.
 - Adding place blockage.
 - Power routing.
 - PG shorts.
 - Macro Overlap.

##### Preplacement of cells:
- Add end cap cells.
- Tap cells.
- IO buffering.
- Feed through - buffers.
- Add spare cells.
- Then only we will start to place the standard cells.

#### Placement of Standard cells:

 ###### Strategies in placement of Std cells:
  - Timing driven -> timing critical.
  - Congestion driven.
  - Area driven.
  - Power driven.

##### Placement  stages:
- Global Placement.
-> Coarse placement.
-> Overlapping of cells.
-> Approx initial location.
-> Optimization based on timing.
- Detail Placement.
-> Legalization.


##### Placement and optimization stage:
- Initial Place (coarse placement)
-> no legalization.
-> Scan chain optimization.
-> Buffer aware timing driven placement.
- Initial-DRC(High Fan Out Net (HRN) buffering)
-> Removal of existing buffer tree.(HFN Synthesis)
-> Logical DRC fixing.(It is called as fan out fixing this is basically design rule violation)
- Initial opto.
-> Quick timing optimization.
- Final place.
-> Incremental Timing Driven optimization.
-> Global route congestion place and scanning optimization.
- Final optimization.


[[Scan chain optimization]]