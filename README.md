# How to setup Folding at home
A guide on setting up FAH on Debian / Mint / Ubuntu

Download the packages from here https://foldingathome.org/start-folding/

Install the dependecies
```
sudo apt install equivs libart-2.0-2 python-cairo python-gtk python
```
Create the DEB control file python-gnome2
```
equivs-control python-gnome2
```
Open the created file
```
nano python-gnome2
```
Remove everything and type in the following
```
Section: misc
Priority: optional
Standards-Version: 3.9.2

Package: python-gnome2
Version: 1:42
Maintainer: Jack Ford <mike@clustergarage.io>
Architecture: all
Description: A fake package to make FAHControl install
```
Build the package
```
equivs-build python-gnome2
```
Install the built package
```
sudo dpkg -i python-gnome2_42_all.deb
```
After running the next command it will ask for a team number at some point so please use this team number 255553
```
sudo dpkg -i --force-depends fahclient_7.5.1_amd64.deb
```
Finish up the install
```
sudo update.rc.d FAHClient defaults
sudo dpkg -i --force-depends fahcontrol_7.5.1-1_all.deb
sudo dpkg -i --force-depends fahviewer_7.5.1_amd64.deb
```
To see your progress go [here](https://client.foldingathome.org/).

https://client.foldingathome.org/
