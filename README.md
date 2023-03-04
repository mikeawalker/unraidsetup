# unraidsetup

I'm running my home machine as a set of virtual machines backed by UnRaid.

Why?
1. I want a windows machine as a daily driver and to play a few games on occasionally
1. I want a linux VM for regularl development
1. I want a linux VM that has gpu access for machine learning
1. I want to have a series of docker containers running in the background for basic services

UnRaid is great at virtualization so I'm going with it.

# Boot settings

Unraid serves up a nice web gui and i picked a cpu without integrated graphics. This made things a bit complicated as UnRaid will try to hoard the graphics card instead of passing it to my VMs.

To fix this i had to create a boot mode for unraid that sets it to run headless

Add the following to TODO
```
TODO
```

# Windows Vm
## Installing windows

I followed the tutorials from SpaceInvader One 

1. [Part1](https://www.youtube.com/watch?v=miYUGWq6l24&t=12s)
2. (https://www.youtube.com/watch?v=A2dkrFKPOyw&t=636s)[Part 2]

## GPU Pass through

I'm using a NVIDIA GPU and using GPU pass through can get a little tricky. 

First we need to dump the vbios. From the gpu luckily we can do this with a handy user script

1. Install the `user scripts` app from the app menu
2. Install a user script to dump the vbios - @SpaceInvaderOne has one available (https://github.com/SpaceinvaderOne/Dump_GPU_vBIOS/blob/master/dump_vbios.sh)[DumpVbios]. 
3. Run the script to save the file to your isos folder in unraid.

When setting up the windows VM

1. Select the nvidia gpu for graphics
2. Select the nvidia gpu for sound
3. Select the vbios to apply to the gpu

## Bluetooth

I had some trouble getting bluetooth passthrough working. I resolved based on this method
- (https://www.reddit.com/r/VFIO/comments/wbsqy1/how_to_fix_onboard_intel_bluetooth_error_code_10/)[Source 1]
- ()[]
