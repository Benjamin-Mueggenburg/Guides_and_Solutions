## Lego Batman 3
### Intro
So this week the theme of Epic Game's weekly free games is Batman. These include the Lego Batman franchise - specifically Lego Batman 3 which trying to get running can be difficult on older hardware.
### Problem
After installing Lego Batman 3 from the Epic Games Store, and clicking the desktop shortcut an error dialog will appear:

![Error Dialog Box](https://i.imgur.com/Yh3BpxK.png)

`Sorry, but your machine is unable to run the DirectX 11 version of the game. It requires a graphics card which supports DirectX11. Please re-lanuch the game through the installed shortcut. The game will now exit.`

Obivously, as stated by the error, your PC has an outdated graphics card that does not support DirectX 11.

### Solution Overview
For Lego Batman 3, two executables (.exe) are installed - `LEGOBatman3.exe` and `LegoBatman3_DX9.exe`. Clicking and running `LegoBatman3_DX9.exe` will start the game and it will run. The `DX9` part signifies that version of the game uses DirectX 9, while the other uses DirectX 11.

Currently (and quite annoyingly) you cannot change which executable Epic Games will run, as there is no settings to change (apart from installation location). So my current solution is to manually run `LegoBatman3_DX9.exe`.

### Solution
#### Steps
1. Navigate to Lego Batman 3 installation. Default is `C:\Program Files\Epic Games\LegoBatman3`
2. Double click `LegoBatman3_DX9.exe` to get the game running.
#### Optional
3. Right click `LegoBatman3_DX9.exe` and select `Create shortcut`
4. New shortcut named `LegoBatman3_DX9.exe - Shortcut` is created.
5. Drag shortcut to desktop and rename to whatever. Appropriately `LEGO Batman 3 Beyond Gotham`
6. Yay! Now you can run the game by simply doubling clicking the new Desktop Shortcut you just made.



