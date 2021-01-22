Above is my tweaked version of https://github.com/Vertabreak/Verts-Marlin for the GEEETECH A10 3D printer, with the BL Touch/3D Touch enabled.

Note: In this update i have also fixed the issue with the G29 g.code issue on Marlin 2.0 in which for some users, the touchprobe decides to go off the bed when creating a mesh or activating UBL (Unified Bed Levelling).

#define X_MIN_POS -10

#define Y_MIN_POS -9 
  
These are the values that i use on my printer, however yours may be subject to change.
  
The above commands are used in order to fix the G29 issue. In addition if you are using Cura for you're slicing software i recommend that you input these commands after the G28 - Auto Home command.

G29 L1 - Loads the mesh stored in slot 1.
G29 J - Tells G29 to probe the specified 3 points and tilt the mesh according to what it finds.

To find more information visit: https://marlinfw.org/docs/features/unified_bed_leveling.html
 
Since storing a mesh on my 3D Printer in the EEPROM, i have had great success with my test prints. I like to use the 3D Benchy as it really helps me to indentify slight errors in my prints which i can swiftly rectify. 
 
Here is the 3D Benchy Thingiverse link for anyone interested!: https://www.thingiverse.com/thing:763622

Other changes that i made to configuration.h include:

#define GTA10 - Defining the chosen printer, in this case the GEEETECH A10

#define TOUCHPROBE - Defining the touchprobe i.e (BL Touch or 3D Touch)

#define PLR- Enabled Power Loss Resume 

#define RUNOUT - Enabled the Filament Runout Sensor- detects when there is no filament

#define GRIDSIZE 7 - Changed the mesh diamentions from a 5X5 to 7X7 as it provides a higher level of accuracy when printing once the mesh is loaded.

Other changes that i made to the configuration_adv.h include:

#if PROBE_SELECTED && !IS_KINEMATIC

#define PROBING_MARGIN_LEFT PROBING_MARGIN

#define PROBING_MARGIN_RIGHT PROBING_MARGIN

#define PROBING_MARGIN_FRONT PROBING_MARGIN

#define PROBING_MARGIN_BACK PROBING_MARGIN

These are the settings in which i enabled to ensure that the probe performs correctly when carrying out G29-auto bed-levelling before my prints begin.


Feel free to ask me any questions! Hope you enjoy my take on Marlin 2.0 for the GEEETECH A10.
 

