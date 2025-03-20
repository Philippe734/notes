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
#### Full update & clean
```sudo apt update ; sudo apt full-upgrade -y ; sudo apt-get autoclean ; sudo apt-get clean ; sudo apt-get autoremove --purge -y```
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
#### Change login background
Basically, you need to edit a file with the path to your desired background and then run another command.
To do so, in a terminal, enter:
```
sudo nano /usr/share/glib-2.0/schemas/30_ubuntu-mate.gschema.override
```
and edit line 2 (background='/usr/share/backgrounds/ubuntu-mate-common/Green-Wall-Logo.png') , replacing the path with the one to your wallpaper and save the changes. Don't screw up or it could cause trouble.
Then in a terminal:
```
sudo glib-compile-schemas /usr/share/glib-2.0/schemas/
```
And that's it.
