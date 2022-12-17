amdctl
===
This is an unofficial manual for amdctl,which is a software for undervolting amd cpu under Linux.

~~This software have no official manual avaliable as far as i know. :(~~

It is possible to damage your chip,therefore you need to make sure you do understand what you are doing and I will take no responsiblity even if you followed this document.

installation
---
```
paru -S amdctl-git          #under ArchLinux
```
for other linux distribution,clone the official git repository then build and install it from source.


basic arguments
---

Usage:

amdctl [options]
option|use
-|-
-g |Get CPU and north bridge (if available) information.
-c |CPU core to work on.
-p |CPU P-state to work on.
-v |Set CPU voltage id (vid).
-d |Set the CPU divisor id (did).
-f |Set the CPU frequency id (fid).
-a |Activate (1) or deactivate (0) P-state.
-e |Show current P-State only. (Not available on 17h / 19h)
-t |Preview changes without applying them to the CPU / north bridge.
-u |Try to find voltage id by voltage (millivolts).
-m |On Linux kernel >= 5.9, enables userspace MSR writing.
-s |Hide all output / errors.
-i |Show debug info.
-h |Shows this information.
-x |Explains field name descriptions.

note:
Generally,every command need to run with root permission and ```-m``` optoin(if you are not using the antique kernel)

In the content below,I will assume that you are using the command as ___root___

getting info
---
```
amdctl -mg
```

UnderVolting
---
__WARNING:MAKE SURE U DO UNDERSTAND CONTENT BELOW__

Use command below to undervolt cpu
```
amdctl -p [p-state-number] -v [CpuVid] -f [CpuFid]
```

- p-state number : the [p-state](https://www.intel.com/content/www/us/en/develop/documentation/vtune-help/top/reference/energy-analysis-metrics-reference/p-state.html) you are changing

- CpuVid : The argument related to your cpu voltage.__The higher CpuVid means lower voltage.__ Therefore never set it to 0 as 0 means the maximum voltage.

- CpuFid : The argument related to your cpu frequency.The higher CpuFid means higher cpu frequency

Tip: it is recommended to use -t preview the result to verify whether the changes are correct before applying them
