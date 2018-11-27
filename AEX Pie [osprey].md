### Install java  
```
sudo apt-get update  
sudo apt-get install openjdk-8-jdk  
```
### Install needed tools (Ubuntu 18.04)  
```
sudo apt-get install git-core gnupg flex bison gperf build-essential zip curl zlib1g-dev gcc-multilib g++-multilib libc6-dev-i386 lib32ncurses5-dev x11proto-core-dev libx11-dev lib32z-dev libgl1-mesa-dev libxml2-utils xsltproc unzip
```
### Setup github
```
git config --global user.name "SayantanRC"  
git config --global user.email "bin.sayantan@gmail.com"  
```
### Get `repo` tool
```
mkdir -p ~/bin 
curl https://storage.googleapis.com/git-repo-downloads/repo > ~/bin/repo  
chmod a+x ~/bin/repo  
```
### Edit .bashrc
```
nano ~/.bashrc
```
Add the following to the end of the file:
> #Android Tools  
> export PATH=${PATH}:~/bin  

Save the file. `source` it.
```
source ~/.bashrc
```
### Install python (2.7) if not present
```
sudo apt install python
```
### Make directory for ROM source
```
mkdir -p ~/aex_rom  
```
### Get the AEX source (9.x)
``` 
cd ~/aex_rom  
repo init -u git://github.com/AospExtended/manifest.git -b 9.x  
repo sync -c -f --force-sync --no-clone-bundle --no-tags -j10  
```
### Get device sources (osprey)
```
cd ~/aex_rom  
git clone https://github.com/ishubhamsingh/android_kernel_motorola_msm8916 -b 9.x kernel/motorola/msm8916  
git clone https://github.com/TheMuppets/proprietary_vendor_motorola -b lineage-16.0 vendor/motorola  
git clone https://github.com/AospExtended-Devices/device_motorola_osprey -b 9.x device/motorola/osprey  
```