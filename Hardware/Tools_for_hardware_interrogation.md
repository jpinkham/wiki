### Processor 

+ Easiest: From procfs:

```cat /proc/cpuinfo```

+ From BIOS, via sysfs:

```dmidecode --type processor```

Example output:
```
taz07-kali ~ # dmidecode --type processor
# dmidecode 3.2
Getting SMBIOS data from sysfs.
SMBIOS 2.6 present.

Handle 0x0004, DMI type 4, 42 bytes
Processor Information
	Socket Designation: CPU 1
	Type: Central Processor
	Family: Core i7
	Manufacturer: Intel            
	ID: A7 06 02 00 FF FB EB BF
	Signature: Type 0, Family 6, Model 42, Stepping 7
	Flags:
		FPU (Floating-point unit on-chip)
	<SNIP rest of flag list>
	Version: Intel(R) Core(TM) i7-2640M CPU @ 2.80GH        
	Voltage: 0.0 V
	External Clock: 100 MHz
	Max Speed: 4000 MHz
	Current Speed: 2800 MHz
	Status: Populated, Enabled
	Upgrade: Other
	L1 Cache Handle: 0x0005
	L2 Cache Handle: 0x0006
	L3 Cache Handle: 0x0007
	Serial Number: To Be Filled By O.E.M.
	Asset Tag: To Be Filled By O.E.M.
	Part Number: To Be Filled By O.E.M.
	Core Count: 2
	Core Enabled: 2
	Thread Count: 4
	Characteristics:
		64-bit capable

```
