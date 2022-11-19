#### Open control center from terminal:
```mate-control-center```
#### Set layout panel to Redmond with terminal
```mate-panel --reset --layout redmond && killall mate-panel```
#### Full update & clean
```sudo apt update ; sudo apt-get autoclean ; sudo apt-get clean ; sudo apt-get autoremove --purge -y```
#### Remove old recalcitrant kernels
```sudo apt-mark auto $(apt-mark showmanual | egrep 'linux-.*[0-9]' | grep -v "hwe") && sudo apt-get autoremove --purge -y```
#### Lock panel
```gsettings set org.mate.panel locked-down true```
#### Wine installer
```wine uninstaller```
#### Wine kill app
```wineserver -k```
#### Run wine app fullscreen
```
#!/bin/bash
export WINEPREFIX='/home/home/.wine/VirtualDesktopApplication'
wine explorer /desktop=POK,1366x768 '/home/home/.wine/drive_c/Games/jeux.exe'
```
