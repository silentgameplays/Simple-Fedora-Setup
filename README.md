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
  
 # 3. Installing NVIDIA drivers with other stuff:
 * sudo dnf install akmod-nvidia vulkan-tools vulkan-headers vulkan-loader vulkan-validation-layers
 # 4. installing codecs and other dependencies for playing videos:
 * sudo dnf install gstreamer1-plugins-{bad-\*,good-\*,base} gstreamer1-plugin-openh264 gstreamer1-libav --exclude=gstreamer1-plugins-bad-free-devel
 * sudo dnf install lame\* --exclude=lame-devel
 * sudo dnf group upgrade --with-optional Multimedia
 * sudo dnf install x265 x264 wavpack xvidcore faad2 faad2-libs
 * sudo dnf update 
 * sudo dnf upgrade
 


