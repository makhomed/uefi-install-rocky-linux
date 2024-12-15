
# uefi-install-rocky-linux (version 1.0.0)
Install Rocky Linux from local block device in UEFI mode

## Usaage:

Boot server to Rescue Console, connect to server via ssh and run these commands as root:

```# cd```

```# git clone https://github.com/makhomed/uefi-install-rocky-linux```

```# cd uefi-install-rocky-linux/```

```# vim uefi-install-rocky-linux```

Edit variables block on the start of the script and enter apropriate custom values:

```
### variables ########################################################

# only_use_blockdevices = [ '/dev/nvme0n1', '/dev/nvme1n1' ]

# kickstart_url = 'https://example.com/ks.cfg'

# vnc_installation_enabled = True

# rocky_linux_version = 9

######################################################################
```

Save file after editing and run script for execution:

```# ./uefi-install-rocky-linux```

Script `uefi-install-rocky-linux` will print error message if case of errors, or display summary screen in case if no errors in configuration block was detected.

Summary screen will be looks like this:

```
Install Rocky Linux 9.5

UEFI boot from /dev/nvme0n1 /dev/nvme1n1

Using kickstart https://example.com/ks.cfg

VNC password: E3klJrWI

IP addresses: 11.22.33.44 2001:0DB8:4ED2:3217::2

Press <Enter> to reboot
```

After pressing `<Enter>` server will reboot and after reboot automatically start requested Rocky Linux installation, initiated from the local block device, in the UEFI mode.

Installing Rocky Linux fully and semi-automated possible using kickstart files, more details about creating Rocky Linux kickstart files - see in the [Red Hat Enterprise Linux Documentation](https://docs.redhat.com/en/documentation/red_hat_enterprise_linux/), chapter `Installing RHEL`, document `Automatically installing RHEL`.

