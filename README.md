# Build_MacOS_On_Window_Linux

WINDOWS

Method 1-VMWare Virtual Machine 

https://github.com/paolo-projects/auto-unlocker



_______________________________________________________________________________________________________________________________________________


Method 2-Oracle Virtual Box

cd "C:\Program Files\Oracle\VirtualBox\"

VBoxManage.exe modifyvm "MacOS" --cpuidset 00000001 000106e5 00100800 0098e3fd bfebfbff

VBoxManage setextradata "MacOS" "VBoxInternal/Devices/efi/0/Config/DmiSystemProduct" "iMac19,1"

VBoxManage setextradata "MacOS" "VBoxInternal/Devices/efi/0/Config/DmiSystemVersion" "1.0"

VBoxManage setextradata "MacOS" "VBoxInternal/Devices/efi/0/Config/DmiBoardProduct" "Mac-AA95B1DDAB278B95"

VBoxManage setextradata "MacOS" "VBoxInternal/Devices/smc/0/Config/DeviceKey" "ourhardworkbythesewordsguardedpleasedontsteal(c)AppleComputerInc"

VBoxManage setextradata "MacOS" "VBoxInternal/Devices/smc/0/Config/GetKeyFromRealSMC" 1

VBoxManage setextradata "MacOS" VBoxInternal2/EfiGraphicsResolution 1920x1080


Bug Fixed

VBoxManage.exe setextradata "MacOS" "VBoxInternal/Devices/smc/0/Config/GetKeyFromRealSMC" 0

________________________________________________________________________________________________________________________________________________________________


Method 3- Docker OSX

Pre-requisite Article:

https://boxofcables.dev/accelerated-kvm-guests-on-wsl-2/

Need KVM accelerator / WSL / QEMU & Docker

YouTube Video Reference:

https://youtu.be/wLezYl77Ll8

GitHub Library: https://github.com/sickcodes/Docker-OSX

________________________________________________________________________________________________________________________________________________________________



LINUX

Method 1

sudo apt-get install qemu-system qemu-utils python3 python3-pip  # for Ubuntu, Debian, Mint, and PopOS.

sudo pacman -S qemu python python-pip python-wheel  # for Arch.

sudo xbps-install -Su qemu python3 python3-pip   # for Void Linux.

sudo zypper in qemu-tools qemu-kvm qemu-x86 qemu-audio-pa python3-pip  # for openSUSE Tumbleweed

sudo dnf install qemu qemu-img python3 python3-pip # for Fedora

sudo emerge -a qemu python:3.4 pip # for Gentoo



Step-1 

./jumpstart.sh --mojave

Step-2

qemu-img create -f qcow2 MyDisk.qcow2 64G


In basic.sh, add 

   -drive id=SystemDisk,if=none,file=MyDisk.qcow2 \
    -device ide-hd,bus=sata.4,drive=SystemDisk \

GitHub Repository: https://github.com/foxlet/macOS-Simple-KVM

Reference: https://youtu.be/FbOc1cqIQcI


________________________________________________________________________________________________________________________________________________________________


Method 2- Sosumi Method

YouTube Video Reference: https://youtu.be/QWZ_LjzT39k

GitHub Repository: https://github.com/popey/sosumi-snap




