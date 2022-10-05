# screen-tear-resolve
config to resolve screen tearing issue on Linux for intel based integrated GPU machines

## Step 1: make a folder with name xorg.conf.d in /etc/X11/ path using below command <br>
```sudo mkdir /etc/X11/xorg.conf.d```

## Step 2: make a config file using below path <br>
```sudo nano /etc/X11/xorg.conf.d/20-intel.conf```

## Step 3: paste the below lines in the config file and save and exit <br>

```Section  "Device"
   Identifier  "Intel Graphics"
   Driver   "intel"
   Option   "TearFree"    "true"
EndSection```
