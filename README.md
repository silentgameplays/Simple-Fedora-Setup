# Simple-Fedora-Setup
simple Fedora Setup for Gaming and multimedia stuff
After point and click install.
# 1. Optimizing DNF config for faster downloads and usage go to terminal:
* sudo nano /etc/dnf/dnf.conf
# Add some lines or copy/paste withouth the (*):
* [main]
* gpgcheck=1
* installonly_limit=3
* clean_requirements_on_remove=True
* best=False
* skip_if_unavailable=True
* fastestmirror=True
* max_parallel_downloads=10
* defaultyes=True
# Ctrl+O,Ctrl+X
* sudo dnf update
# 2. Enabling RPM repos free and non-free:
 * sudo dnf install \
  https://download1.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm

 * sudo dnf install \
  https://download1.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm
  
 * sudo dnf update --refresh
 * sudo dnf upgrade --refresh -y
  
 # 3. Installing NVIDIA drivers with other stuff:
 * sudo dnf install akmod-nvidia xorg-x11-drv-nvidia-cuda vulkan-tools vulkan-headers vulkan-loader vulkan-validation-layers
 # 4. installing codecs and other dependencies for playing videos:
 * sudo dnf install gstreamer1-plugins-{bad-\*,good-\*,base} gstreamer1-plugin-openh264 gstreamer1-libav --exclude=gstreamer1-plugins-bad-free-devel
 * sudo dnf install lame\* --exclude=lame-devel
 * sudo dnf group upgrade --with-optional Multimedia
 * sudo dnf install x265 x264 wavpack xvidcore faad2 faad2-libs
 * sudo dnf install rpmfusion-free-release-tainted
 * sudo dnf install libdvdcss
 * sudo dnf install \*-firmware
 * sudo dnf update 
 * sudo dnf upgrade
 * sudo dnf groupupdate sound-and-video
 # 5. Installing multimedia players and stuff.
 * sudo dnf install mpv vlc celluloid dragon
 # Installing meson will be required by some apps like nvfbc OBS plugin and celluloid.
 * sudo dnf install meson
 # 6.(Optional) Installing stuff for gaming:
 * sudo dnf install steam lutris wine
 # 7.(Optional) Installing OBS Studio for recording the screen and other utilities:
 * sudo dnf install obs-studio shotcut kdenlive gimp krita kate 
 * sudo dnf install ktorrent fragments transmission
 # 8. NVFBC plugin for OBS Studio:
 # Get nvidia-patch: https://github.com/keylase/nvidia-patch
 # Extract and go to the folder
 # Open in terminal
 * sudo ./patch-fbc.sh
 # Get obs-nvfbc: https://gitlab.com/fzwoch/obs-nvfbc
 # Extract and go to folder
 # Open in terminal in case you have installed them,ninja build seems to be installed by default:
 * sudo dnf install meson ninja-build 
 * sudo dnf install mesa-libGL-devel mesa-libGLU-devel
 * meson build
 * ninja -C build
 # Go back to GUI and copy nvfbc.so
 # Enable hidden files and fodlers
 # Go to /home/user/.config/obs-studio
 # Create the following folders plugins->nvfbc->bin->64bit
 # paste nvfbc.so into 64bit
 # Go to OBS Studio and add the NvFBC Source to your scene
 
 Ok you are good to use Fedora for gaming and watching videos properly!Congrats!
 #silentgamepls

 


