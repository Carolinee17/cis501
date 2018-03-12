# Lab 4 Schematic

In this lab, you'll complete a fully bypassed, 5-stage pipelined LC4 processor, as discussed in lecture. All branches will be predicted as not taken. We'll start by drawing a schematic as usual.

Create a detailed schematic of your pipelined datapath, with all wires, ports, and module instantiations labeled. This schematic will be much more complex than your single-cycle schematic, so we are giving you slightly different rules. The goals are to make sure your schematic has the necessary detail and legibility to help you implement the pipeline, and to make it useful preparation for exams.
+ Come up with a **clear, consistent naming scheme** for all your wires. We recommend a **short prefix that indicates the pipeline stage** to which the wire belongs. A prefix is slightly more useful than a suffix so you can sort the list of signals in the debugger by name to group signals by pipeline stage. We think that grouping is more helpful than grouping signals by purpose (you'd get this if you used a suffix for the pipeline stage), although we wish it were easy to group both ways.
+ Your schematics must be legible and tolerably neat, but they do not have to be beautiful.
+ You **do** need to mark the clock port as a triangle, but you do not need to draw the clock wires.
+ You **do not** have to include the `rst` and `gwe` ports and wires on these schematics.
+ You **do not** need to include the `switch_data` and `led_data` wires in your schematic (they are optional and not worth any points).
+ The register file, ALU and branch logic can be black boxes (but **be sure to label the ports**!).
+ You **do** need to include the `test_*` wires on your schematic. Getting these right the first time around can save you hours of debugging.
+ We recommend that you include a wiring table that lists every wire in your datapath, its width, source, and destination. For wires that connect directly to the port of a functional unit, list the instance's name as declared in your Verilog code, and the port name. A single mis-declared, mis-connected, or forgotten wire can easily cause the entire pipeline to fail; the extra effort you put into creating an accurate wiring table will almost certainly pay off during implementation.
+ We **encourage** you to break your schematic up into multiple parts. For instance, you could have one schematic for each pipeline stage. You could also create a high-level schematic with black boxes for many parts, and separate closeup schematics of those parts with the full detail and labeling. In that case, you need to label the wires leading into each black box, but you only need to specify ports if those boxes will be implemented as modules in Verilog. If they are not implemented as modules, note this clearly on your high-level schematic so TAs don't deduct points.
+ It's fine to number the rows in your wiring table, and give these numbers on the wires and ports in your schematic instead of writing the full names. If you do this for your ports, make sure the schematic clearly indicates whether it is an input or output port (e.g. with arrows on the wires). When you label multi-bit buses this way, you should still indicate the bus width on the schematic.
+ It's fine to draw a wire leaving one unit and entering another one, without drawing the line in between when it would be a long, confusing line. Make sure to label the wire and bus width in both cases. This is preferable to drawing the same functional unit (e.g. register file) in multiple places.
+ It's a good idea to color-code your wires. Once possibility is to color them based on the pipeline stage in which they originate. Another is to color them based on purpose: data, control, bypass, stall, squash, test, ... You may find it helpful to do a combination of these schemes or to draw multiple schematics.