systemd
===

basic usage
---
Usage|command
-|-
Show system status|systemctl status
List running units|systemctl
List failed units|systemctl --failed
Status of a unit|systemctl status ```unit```
Check whether a unit is enabled|systemctl is-enabled ```unit```
Start a unit immediately|systemctl start ```unit```
Stop a unit immediately|systemctl stop ```unit```
Restart a unit|systemctl restart ```unit```
Enable a unit to start automatically at boot|systemctl enable ```unit```
Enable a unit to start automatically at boot and start it immediately|systemctl enable --now ```unit```
Disable a unit to no longer start at boot|systemctl disable ```unit```
Shut down and reboot the system|systemctl reboot
Shut down and power-off the system|systemctl poweroff
Suspend the system|systemctl suspend
Put the system into hibernation|systemctl hibernate
Put the system into hybrid-sleep state|systemctl hybrid-sleep

unit files
---

file path
- ```/usr/lib/systemd/system/```: units provided by installed packages
- ```/etc/systemd/system/```: units installed by the system administrator

syntax is basically same as .desktop
