# RTL8852BE
![github](https://img.shields.io/badge/Kernel<=6.0.0-build_pass_&_works-blue.svg?style=for-the-badge&logo=linux&logoColor=ffffff)  
![github](https://img.shields.io/badge/-bluetooth_partly_supported-blue.svg?style=for-the-badge&logo=bluetooth&logoColor=ffffff)**See Here:[HRex39/rtl8852be_bt](https://github.com/HRex39/rtl8852be_bt).**  
  
**![github](https://img.shields.io/badge/Kernel>6.0.0-Not_Longer_Maintain(but_you_can_try)-red.svg?style=for-the-badge&logo=linux&logoColor=ffffff)  
For kernel > 6.0.0, You should view [lwfinger/rtw8852be](https://github.com/lwfinger/rtw8852be).**   
## LTS
![github](https://img.shields.io/badge/-Ubuntu-555555.svg?style=for-the-badge&logo=ubuntu&logoColor=E95420)  
Support CI/CD based on Github-hosted runners: Ubuntu 18.04, Ubuntu 20.04, Ubuntu 22.04.  
  
## Unstable
![github](https://img.shields.io/badge/-Debian-555555.svg?style=for-the-badge&logo=debian)
![github](https://img.shields.io/badge/-Centos-555555.svg?style=for-the-badge&logo=centos)
![github](https://img.shields.io/badge/-Arch-555555.svg?style=for-the-badge&logo=archlinux&logoColor=ffffff)
![github](https://img.shields.io/badge/-Others-555555.svg?style=for-the-badge&logo=linux&logoColor=ffffff)
## Introduction
This code is cloned from [TinkerBoard2/kernel](https://github.com/TinkerBoard2/kernel) and it's author is Rock_Shen (rock_shen@asus.com).  
The default compilation option is i386_PC For Linux, you can also change the compilation options of MAKEFILE in line149.  
## Prerequisites (for Ubuntu/Debian)
```
build-essential 
linux-headers
bc
```
## Prerequisites (for Fedora)
```
kernel-headers
kernel-devel-`uname -r`
make
automake
cmake
gcc
gcc-c++
bc
```




## Build(for kernel < 5.18)
```
#Turn off Secure Boot in BIOS

git clone https://github.com/HRex39/rtl8852be.git
cd rtl8852be
make -j8
sudo make install
sudo modprobe 8852be
```

## Build(for kernel >= 5.18)
```
#Turn off Secure Boot in BIOS

git clone https://github.com/HRex39/rtl8852be.git -b dev
cd rtl8852be
make -j8
sudo make install
sudo modprobe 8852be
```

## For DKMS support (i.e. no need to rebuild and modprobe again after updating the kernel)
```
sudo dkms add -m rtl8852be -v r28.28daf8c
sudo dkms build -m rtl8852be -v r28.28daf8c
sudo dkms install -m rtl8852be -v r28.28daf8c
```
