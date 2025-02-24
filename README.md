
# uefi-install-rocky-linux (version 1.1.0)
Install Rocky Linux from local block device in UEFI mode

## Usaage:

Boot server to Rescue Console, connect to server via ssh and run these commands as root:

```# cd```

```# pacman --noconfirm --refresh --sync git```

```# git clone https://github.com/makhomed/uefi-install-rocky-linux```

```# cd uefi-install-rocky-linux/```

```# vim uefi-install-rocky-linux```

Edit variables block on the start of the script and enter apropriate custom values:

```
### variables ########################################################

### basic settings ###

# only_use_blockdevices = [ '/dev/disk/by-id/ata-INTEL_SSDSC2KB960G8_PHYF874700EG960CGN', '/dev/disk/by-id/ata-INTEL_SSDSC2KB960G8_PHYF87470114960CGN' ]

# kickstart_url = 'https://example.com/server-name-kickstart.cfg'

# vnc_installation_enabled = True

# rocky_linux_version = 9

### advanced settings ###

# eth0_mac_address = '3c:ec:ef:29:73:44'
# eth1_mac_address = '3c:ec:ef:29:73:45'

# eth0_ipv4_address = '197.149.57.183'
# eth0_ipv4_gateway = '197.149.57.1'
# eth0_ipv4_netcidr = 24
# bootdev= 'eth0'

# nameservers_info = f'nameserver=1.1.1.1 nameserver=1.0.0.1 nameserver=8.8.8.8'
# rename_interface = f'ifname=eth0:{eth0_mac_address} ifname=eth1:{eth1_mac_address}'
# interface_config = f'{nameservers_info} {rename_interface} ip={eth0_ipv4_address}::{eth0_ipv4_gateway}:{eth0_ipv4_netcidr}::{bootdev}:none bootdev={bootdev}'

# linux_cmdline_extra = f'{interface_config}'

######################################################################
```

Save file after editing and run script for execution:

```# ./uefi-install-rocky-linux```

Script `uefi-install-rocky-linux` will print error message if case of errors, or display summary screen in case if no errors in configuration block was detected.

Summary screen will be looks like this:

```
Install Rocky Linux 9.5

UEFI boot from /dev/disk/by-id/ata-INTEL_SSDSC2KB960G8_PHYF874700EG960CGN /dev/disk/by-id/ata-INTEL_SSDSC2KB960G8_PHYF87470114960CGN

Using kickstart https://example.com/server-name-kickstart.cfg

VNC password: E3klJrWI

IP addresses: 197.149.57.183 2001:0DB8:4ED2:3217::2

Press <Enter> to reboot
```

After pressing `<Enter>` server will reboot and after reboot automatically start requested Rocky Linux installation, initiated from the local block device, in the UEFI mode.

Installing Rocky Linux fully and semi-automated possible using kickstart files, more details about creating Rocky Linux kickstart files - see in the [Red Hat Enterprise Linux Documentation](https://docs.redhat.com/en/documentation/red_hat_enterprise_linux/), chapter `Installing RHEL`, document `Automatically installing RHEL`.

