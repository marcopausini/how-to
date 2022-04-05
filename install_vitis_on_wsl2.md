# How to Install Vitis on Windows Subsystem Linux

## Environment
* Windows 11
* Ubuntu 20.04.4 LTS
* Vitis 2021.2

## Steps

1. Install missing libraries (not sure if they all are necessary, but otherwise the installation hangs at _generating installed device list_)  
```
   sudo apt install libncurses5
   sudo apt install libtinfo5
   sudo apt install libncurses5-dev libncursesw5-dev
   sudo apt install ncurses-compat-libs
   sudo apt-get install libstdc++6:i386
   sudo apt-get install libgtk2.0-0:i386
   sudo apt-get install dpkg-dev:i386
   sudo ln -s /usr/bin/make /usr/bin/gmake
   apt install python3-pip
```
2. Download Vitis 2021.2 from Xilinx website
3. Change permission to executable  
`chmod +x ./Downloads/Xilinx_Unified_2021.2_1021_0703_Lin64.bin`
4. Run the installer  
`sudo ./Downloads/Xilinx_Unified_2021.2_1021_0703_Lin64.bin`
5. After installation is complete, which can take up to 4 or 5 hourws, install if needed cable drivers
```
cd /tools/Xilinx/Vitis/2021.2/data/xicom/cable_drivers/lin64/install_script/install_drivers
   sudo ./install_drivers
```
6. Download platforms from links below

https://www.xilinx.com/support/download/index.html/content/xilinx/en/downloadNav/embedded-platforms.html

7. Unzip platform
```
cd /tools/Xilinx/
sudo mkdir platforms
cd platforms
sudo cp /mnt/d/inbox/xilinx_vck190_base_202120_1.zip ./
sudo unzip xilinx_vck190_base_202120_1.zip

6. Launch Vitis IDE
```
   source /tools/Xilinx/Vitis/2021.2/settings64.sh  
   vitis
```
