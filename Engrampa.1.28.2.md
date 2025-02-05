## Build Engrampa 1.28.2 for Ubuntu Mate 24.04

To fix [this issue](https://github.com/mate-desktop/engrampa/issues/510) in Ubuntu Mate 24.04, build the release 1.28.2

Instructions from lah7 [here](https://ubuntu-mate.community/t/when-engrampa-1-28-2-in-24-04/28919/8)

1. Update the system

       sudo apt update && sudo apt full-upgrade -y

1. Install a metapackage with tools for building packages:

       sudo apt install devscripts git
   
1. Open Software & Updates, subscribe to "All updates" and check the "Source Code" option. Save & refresh the cache.

       software-properties-gtk

3. Get the source code for engrampa - let's store this on the desktop.

       cd ~/Desktop
       mkdir engrampa && cd engrampa
       apt-get source engrampa

4. Download the engrampa repository checked out to the desired version (1.28.2). Their source code also needs some git submodules.

       git clone --depth 1 --branch v1.28.2 --recurse-submodules https://github.com/mate-desktop/engrampa.git

5. Extract the Debian tarball (this describes how to build the package, any patches, changelog, etc)

       tar -xJf engrampa_*debian*.tar.xz

6. Edit this file and replace the number on the first line reads to `1.28.2`

       nano debian/changelog
   
6. Check it

       head -1 debian/changelog
       engrampa (1.28.2-1) unstable; urgency=medium 

8. Install the build dependencies needed to build engrampa

       sudo apt build-dep engrampa

9. Move the `debian` folder inside the `engrampa` (repository) folder. Delete the 1.26.2 sources as we don't need them.

       rm engrampa_1.26.2.orig.tar.xz
       mv debian engrampa

7. Build your package! Sit back as a lot of text flies flies across the screen!

       cd engrampa
       debuild -b

10. All being well, you can install the new package with:

        sudo apt install ../*.deb

![2025-02-05_16-58](https://github.com/user-attachments/assets/4c06bd70-a7f8-40d2-a60d-42950d8ed263)
