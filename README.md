
# uefi-install-rocky-linux (version 1.2.0)

Install Rocky Linux from local block device in UEFI mode

## Usage:

Boot server to Rescue Console, connect to server via ssh and run these commands as root:

```# cd```

```# pacman --noconfirm --refresh --sync git```

```# git clone https://github.com/makhomed/uefi-install-rocky-linux```

```# cd uefi-install-rocky-linux/```

```# mv uefi-install-rocky-linux.toml.example uefi-install-rocky-linux.toml```

```# vim uefi-install-rocky-linux.toml```

Edit settings in the uefi-install-rocky-linux.toml configuration file and run script for execution:

```# ./uefi-install-rocky-linux```

Script `uefi-install-rocky-linux` will print error message if case of errors, or display summary screen in case if no errors in configuration block was detected.

Summary screen will be looks like this:

```
Install Rocky Linux 9.5

UEFI boot from /dev/disk/by-id/ata-INTEL_SSDSC2KB960G8_PHYF82857386960CGN /dev/disk/by-id/ata-INTEL_SSDSC2KB960G8_PHYF82857217960CGN

Using kickstart [https://example.com/server-name-kickstart.cfg](https://example.com/linux-server-name-kickstart.cfg)

VNC password: E3klJrWI

IP addresses: 11.22.33.44 2001:0DB8:4ED2:3217::55

Press <Enter> to reboot
```

After pressing `<Enter>` server will reboot and after reboot automatically start requested Rocky Linux installation, initiated from the local block device, in the UEFI mode.

Installing Rocky Linux fully and semi-automated possible using kickstart files, more details about creating Rocky Linux kickstart files - see in the [Red Hat Enterprise Linux Documentation](https://docs.redhat.com/en/documentation/red_hat_enterprise_linux/), chapter `Installing RHEL`, document `Automatically installing RHEL`.

