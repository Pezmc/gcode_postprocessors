# Scripts that post-process g-code

* wood.py to add temperature changes and simulate wood
* colormix.py to change the extruding ratios (e.g. on a diamond hotend)

## Changes in this fork

This fork ([Pezmc/gcode_postprocessors](https://github.com/Pezmc/gcode_postprocessors)) updates `wood.py` to work with modern slicers on top of the original [MoonCactus/gcode_postprocessors](https://github.com/MoonCactus/gcode_postprocessors). In short:

* Fixed the wood effect being silently disabled by pre-print bed lifts / repositioning (e.g. PrusaSlicer for the Prusa CORE One).
* Read g-code as UTF-8, fixing the long-standing non-ASCII / Windows encoding crash.
* Reject binary `.bgcode` files with a clear message instead of corrupting them.
* Guard the Z-hop look-ahead against the end of the file.
* Echo the temperature graph to the console after patching.

See [wood/README.md](wood/README.md#changes-in-this-fork) for the full list and the reasoning behind each change.
