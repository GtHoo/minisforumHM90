# minisforumHM90
Having problems with installing a linux distro and keeping it alive without frezzing.
What I so far have found out to be "working"

For entering bios spam `del` key after pressing the power button.
-----------------
## Proxmox
* Go into bios and disable `IOMMU`, enable `SVM`, disable MBIST (memory MBIST). Also sett the power  manuelly, example on where and how I found some photos online: https://imgur.com/gallery/hm90-bios-settings-power-q6lIFdC
* Install proxmox.
* Add "AMD_IOMMU=force_enable iommu=pt"  inside grub `/etc/default/grub`  in the end of line GRUB_CMDLINE_LINUX_DEFAULT inside the `"`
* Save and recompile grub with `update-grub`
* Reboot into bios
* Set "IOMMU=Auto" ('Enabled' seems to cause some problems)
* Reboot

