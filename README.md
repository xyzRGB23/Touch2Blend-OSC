# Touch2Blend-OSC
 Stream parameters from Touchdesigner to Blender to use as Drivers via OSC. Tested in Blender 4.2.2 LTS (latest 1.10.2024) and TouchDesigner 2023.11510

 ## Dependencies:
 python-OSC

## How to use
### 1. Make sure python-OSC is present in Blenders Python Bundle.
   How to set this up:
   Open Blender > Change Viewport to Text Editor > Create new File > Run the following code > close Blender
   ```
   import subprocess
   import sys
   import os
 
   python_exe = os.path.join(sys.prefix, 'bin', 'python.exe')
   target = os.path.join(sys.prefix, 'lib', 'site-packages')
    
   subprocess.call([python_exe, '-m', 'ensurepip'])
   subprocess.call([python_exe, '-m', 'pip', 'install', '--upgrade', 'pip'])

   subprocess.call([python_exe, '-m', 'pip', 'install', '--upgrade', 'python-OSC')
    
   print('DONE')
   ```
   > from https://blender.stackexchange.com/questions/56011/how-to-install-pip-for-blenders-bundled-python

   If permission errors occur, run Blender as Admin
  
### 2. Create a new .toe File
  with an OSC-Out CHOP set to **Port 10001** (can be changed in the code on line 68) and feed any value (eg. Noise) into the OSC-Out.
  renaming the channel will resilt in a corresponding name in Blender

### 3. Create a new Blend File
   go into text Editor and run the code from [Touch2Blend](Touch2Blend). A firewall request may pop up.

### 4. Use Values as Drivers
  The shared Values will now be visible in the properties Panel under Object and OSC Properties. They will only be updated of the underlying object is selected.
  To use these values, right-click and Copy as New Driver and then Paste them in any Parameter you want to control.

### Parameters
Retry Rate: How often Blender checks for OSC updates.

_Samplerate: The Samplerate in wich Data is sent from TouchDesigner. This Value can only be changed within Touchdesigner

## Gallery
![image](https://github.com/user-attachments/assets/bb9d89d7-0d83-4c75-9cc6-33cdc55ae72f)
![image](https://github.com/user-attachments/assets/be6c32f7-7f0d-4469-a332-31b6cd1713ed)


