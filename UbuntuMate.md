#### Reset environment, layout and desktop
```
dconf write /org/mate/marco/general/theme "'Yaru'"
dconf write /org/mate/desktop/interface/gtk-theme "'Yaru'"
mate-panel --reset --layout redmond
sleep 5s
killall mate-panel
sleep 5s
dconf reset -f /
```
#### Open control center from terminal
```mate-control-center```
#### Reinstall desktop's files system
```sudo apt install ubuntu-mate-desktop```
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
