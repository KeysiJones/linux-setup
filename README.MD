# Linux commands for fresh installed distros

## How to fix Resolution issue on POP OS/UBUNTU 20 and fixes shutdown issue

1. Type the following command: 

```bash
sudo gedit /etc/default/grub
```

2. To fix shutdown freezing issue, please add below line to /etc/default/grub file:

``` bash
GRUB_CMDLINE_LINUX_DEFAULT="quiet splash acpi=force"
```

3. To fix the resolution issue, add below line to the same file:

```bash
GRUB_GFXMODE=1024x768
```
You can change resolution to suit better your needs, in my case i was using a 1024x768 monitor.


### After changing /etc/default/grub file you should update grub with the following command:

```bash
sudo update-grub
```

### And then restart your computer.

<br/>

## How to fix Ethernet not working issue on POP OS/UBUNTU 20

 In a terminal, type the following commands: 

```bash
sudo echo "options forcedeth msi=0 msix=0" | sudo tee /etc/modprobe.d/forcedeth_options.conf
```

And then type:

```bash 
sudo update-initramfs -u
```

Restart your computer and ethernet should be working normally.

## Observations:

- Forcedeth is a generic ethernet driver that needs to be loaded to make ethernet worl properly.

- I am using a ASROCK MOTHERBOARD with a MCP61 (rev 2) Ethernet onboard device with a AMD FX-6300 six core processor 3.5ghz.


