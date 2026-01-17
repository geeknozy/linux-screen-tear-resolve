## Graphics package for amd
```
sudo pacman -Syu mesa vulkan-radeon libva-mesa-driver xf86-video-amdgpu
```

## Graphics package for intel
```
sudo pacman -S mesa vulkan-intel intel-media-driver
```

## To resolve screen tearing in Linux
config to resolve screen tearing issue on Linux for intel based integrated GPU machines
Note: inorder for this config to work respective intel / amd xf86 driver must be installed exclusively
intel: xf86-video-intel
amd- xf86-video-amdgpu

### Step 1: make a folder with name xorg.conf.d in /etc/X11/ path using below command <br>
##### Note: Ignore if already the config folder is present and move to step 2<br>
```
sudo mkdir /etc/X11/xorg.conf.d
```
### Intel
### Step 2: make a config file using below path <br>
```
sudo nano /etc/X11/xorg.conf.d/20-intel.conf
```

### Step 3: paste the below lines in the config file and save and exit <br>
```
Section "Device"
   Identifier  "Intel Graphics"
   Driver      "intel"
   Option      "TearFree"    "true"
EndSection
```


### AMD
### Step 2: make a config file using below path <br>
```
sudo nano /etc/X11/xorg.conf.d/20-amdgpu.conf
```

### Step 3: paste the below lines in the config file and save and exit <br>
```
Section "Device"
        Identifier      "AMD Graphics"
        Driver          "amdgpu"
        Option          "TearFree" "true"
EndSection
```
### Step 4: Restart the computer and there should not be any screentearing.
