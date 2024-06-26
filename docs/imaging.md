# Imaging computers

Whenever a TU Windows computer stops being functional, the best course of action is to nuke the OS and start anew.

## Requirements
- A USB flash drive that boots to [Ghost](https://en.wikipedia.org/wiki/Ghost_(disk_utility))
- Network session name and IP address provided to you by full time staff
- About an hour block. This process could take a while

## Steps

### Booting to Ghost
1. Restart the computer and change boot drive
   - It depends on the PC manufacturer but it's usually <kbd> F12 </kbd> or <kbd> DEL </kbd>
   - I recommend plugging it in the back of the PC if possible. Front USB ports aren't always reliable when using those as ports to boot into an external drive.
   
### Imaging the OS
1. Wait for Ghost to finish initializing
   - It looks sketch, but it's fine. You can't do anything worse to the computer.
2. Select **Cast** then **Multicast**
3. Input in the GhostCast Session name that you were provided with
4. Select the computer's hard drive containing the OS.
   - It's usually the biggest size drive on the list
5. Ghost should automatically select the correct partition, so just hit `Next`
6. Wait until the imaging is done
7. Unplug the USB drive
   - This step prevents the computer from booting back into Ghost (slight inconvenience)
   - If it does boot back to the USB stick, just restart the computer and change which drive to boot from

### First boot into Windows

**System Preparations Tools** pop up will appear on the screen

1. Set **System Cleanup Action** to **Out-of-Box Experience**
2. Check **Generalize**

### Adding computer to university domain

1. Look up "About PC" 
2. Rename the computer with `CLS-<COLLECTION_CODE>-01`
3. Set "Domain" to "towson.edu"

You will be prompted to enter in your credentials and the computer will reboot



