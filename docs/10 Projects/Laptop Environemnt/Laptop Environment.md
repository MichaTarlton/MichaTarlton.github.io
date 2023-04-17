---
aliases:
type: project
project: laptop
status: open
priority: p4
creationtag: 2022-11-14 13:22
infotags: [laptop,endeavour]
---

```dataview
table rows.file.link AS "Related",
file.ctime as "Created",
infotags as "Tags"
FROM ""
WHERE contains(project,"laptop")
GROUP BY type
SORT file.ctime asc 
```
# Log
## [[14.11.22]]
- Made some changes to GPU settings
- Hopefully set it up where hybrid is fully “on-demand”
- Used:
	- [A guide to power management options · Askannz/optimus-manager Wiki · GitHub](https://github.com/Askannz/optimus-manager/wiki/A-guide--to-power-management-options)
	- [optimus-manager/optimus-manager.conf at master · Askannz/optimus-manager · GitHub](https://github.com/Askannz/optimus-manager/blob/master/optimus-manager.conf)
	- [Optimus-manager problems with bbswitch & acpi-call : linuxquestions](https://www.reddit.com/r/linuxquestions/comments/solwv7/optimusmanager_problems_with_bbswitch_acpicall/)
Made changes to `/etc/optimus-manager/optimus-manager.conf`

```
[amd]  
DRI=3  
driver=modesetting  
tearfree=  
  
[intel]  
DRI=3  
accel=  
driver=modesetting  
modeset=yes  
tearfree=  
  
[nvidia]  
DPI=96  
PAT=yes  
allow_external_gpus=no  
dynamic_power_management=fine  
ignore_abi=no  
modeset=yes  
options=overclocking, triple_buffer  
  
[optimus]  
auto_logout=yes  
pci_power_control=yes  # changed from 'no'
pci_remove=no  
pci_reset=no  
startup_auto_battery_mode=integrated  
startup_auto_extpower_mode=hybrid  
startup_mode=hybrid  
switching=none # changed from 'nouveau'
```


`switching=none` 
- changed from 'nouveau'
`pci_power_control=yes`
- changed from 'no'

Also tried bbswitch but that’s bumblebee and I don’t have it (or want to use it)

Ideally, the GPU is now completely off until called. and it appears to be working.

3 hours of battery and holding