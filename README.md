# Easy Multi Plus
Extremely easy multi/single instancing software for minecraft speedrunning, updated to not kill your eyes by JimTheScientist.

![img.png](img.png)

A couple of goals of this project:
- Setup multi in minutes
- No file editing to adjust settings
- Easy

I believe I have met all of these goals.


## Usage

### Hotkeys
- Pressing the "Reset" hotkey will do various things:
    - Reset the instance you currently have open and move to the next instance.
        - Manually changing the opened window will not have an effect on this.
    - If automatic world clearing is enabled, all speedrun worlds except for the latest 5 in each instance will be cleared upon resetting.
    - All borderless windows will have their position and size reset, essentially unhiding them (see hiding below).
    - When moving to the next instance, Easy Multi will press alt + the number corresponding to the next instance (eg. alt+1, alt+2, etc...). This is to help obs know which instance you are on.
- Pressing the "Hide" hotkey will set all borderless instances to 1x1 pixels to hide them, other than the one currently opened.

### Control Panel
- "Setup Instances" will find all open Minecraft instances. It will also rename them to their instance number (eg. "1", "2", "3"...).
- "Go Borderless" will set all current instances to a borderless window with the set window size in reset options.
- "Restore Windows" will set all current instances to the default Minecraft size and stack them in a row.

### Reset Options Panel
- Pressing either "Reset: ___" and "Hide: ___" will let you set the hotkeys for the respective action.
- Pressing "Window Size: ___x___" will pop up a window which lets you select the size of a borderless window when it is not in a hidden state.
- The checkboxes in "Scene Switching" determine what key will be pressed when switching to an instance. For example, with both "Use Alt" and "Use Numpad" selected, Alt + Numpad 2 will be pressed when switching to instance 2. This option is to help obs know which instance Easy Multi switched to.

### Log Panel
- The large box taking the majority of the panel shows the output of the app, including resets, world clearings, etc...
- "Current Instances: x" shows the amount of instances the app currently controls.
- Pressing "Copy Log" will copy the currently visible lines from the log.

### MultiMC Clearing Panel
- Pressing "Clear Speedrun Worlds" will clear out all select types of speedrun worlds from the selected MultiMC instances folder except for the latest 5 speedrun worlds in each instance.
- Enabling "Automatically Clear" will do the above action on every single reset.
- You can set the MultiMC Instances Folder by pressing the small folder icon.
    - Easy Multi will do its best to locate the instances folder if you do not select the correct folder. For example selecting a ".minecraft" will probably lead Easy Multi to find the instances folder.
- In the "World Typeps to Clear" section, you can enable various types of speedrun world names which will get detected by the world clearing.

## Notes

- Wall is not supported, and probably never will be.
- F3+ESC will never be supported, nor will background resetting.



## Acknowledgements

Thanks to all the following individuals and teams for their projects which helped make this project possible:
- Specner, Four, and many others who have worked on reset and multi macros over the past year.
- [Mr-Technician's Borderless Minecraft](https://github.com/Mr-Technician/BorderlessMinecraft)
- [btsdev's Global Hotkeys module](https://github.com/btsdev/global_hotkeys)
- [boppreh's keyboard module](https://github.com/boppreh/keyboard)
- [terryyin's clipboard module](https://github.com/terryyin/clipboard)
- [rdbende's sun valley theme](https://github.com/rdbende/Sun-Valley-ttk-theme)
- The incredible amount of contributors of [pywin32](https://github.com/mhammond/pywin32)
- Those who worked on Python, and the default Python modules.

## Development

1. Install the above libraries.

2. Add the contents of "theme" from rdbende's theme above to the theme folder located in this project

The below works as long as long as you place the theme folder with the final output:
(Tkinter will load .tcl files normally instead of in the temp directory that is used by the .exe for built-in files)

```pyinstaller --noconfirm --onefile --windowed --icon "EasyMulti.ico" --add-data "EasyMulti.ico;." --add-data "theme;theme/"  "EasyMulti.pyw" --distpath "output/" --add-data="theme;theme"```