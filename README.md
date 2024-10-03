# Touch2Blend-OSC
 Stream parameters from Touchdesigner to Blender to use as Drivers via OSC.

 ## Dependencies:
 python-OSC

## How to use
### 1. Make sure python-OSC is present in Blenders Python Bundle.
   How to set this up:
   Open Blender > Change Viewport to Text Editor > Create new File > Run the following code > close Blender
   ```
   code will be pasted here
   ```
   > from https://blender.stackexchange.com/questions/56011/how-to-install-pip-for-blenders-bundled-python

   If permission errors occur, run Blender as Admin
  
### 2. Create a new .toe File
  with an OSC-Out CHOP set to **Port 10001** (can be changed in the code on line 68) and feed any value (eg. Noise) into the OSC-Out.
  renaming the channel will resilt in a corresponding name in Blender

### 3. Create a new Blend File
   go into text Editor and run the code from [Touch2Blend](Touch2Blend-OSC/Touch2Blend). A firewall request may pop up.

### 4. Use Values as Drivers
  The shared Values will now be visible in the properties Panel under Object and OSC Properties. They will only be updated of the underlying object is selected.
  To use these values, right-click and Copy as New Driver and then Paste them in any Parameter you want to control.

### Parameters
Retry Rate: How often Blender checks for OSC updates.

_Samplerate: The Samplerate in wich Data is sent from TouchDesigner. This Value can only be changed within Touchdesigner
