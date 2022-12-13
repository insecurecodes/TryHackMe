# Day 11

{% embed url="https://github.com/volatilityfoundation/volatility" %}

<figure><img src="../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

## What is the Windows version number that the memory image captured?

```bash
cmnatic@aoc2022-day-11:~/volatility3$ python3 vol.py -f workstation.vmem windows.info
Volatility 3 Framework 2.4.1
Progress:  100.00   PDB scanning finished
Variable  Value

Kernel Base 0xf803218a8000
DTB 0x1ad000
Symbols file:///home/ubuntu/volatility3/volatility3/symbols/windows/ntkrnlmp.pdb/E0093F3AEF15D58168B753C9488A4043-1.json.xz
Is64Bit True
IsPAE False
layer_name  0 WindowsIntel32e
memory_layer  1 FileLayer
KdVersionBlock  0xf80321cd23c8
Major/Minor 15.18362
MachineType 34404
KeNumberProcessors  4
SystemTime  2022-11-23 10:15:56
NtSystemRoot  C:\Windows
NtProductType NtProductWinNt
NtMajorVersion  10
NtMinorVersion  0
PE MajorOperatingSystemVersion  10
PE MinorOperatingSystemVersion  0
PE Machine  34404
PE TimeDateStamp  Mon Apr 14 21:36:50 2104
```

\-> Major version = 10

{% hint style="info" %}
10
{% endhint %}

## What is the name of the binary/gift that secret Santa left?

```bash
cmnatic@aoc2022-day-11:~/volatility3$ python3 vol.py -f workstation.vmem windows.psscan
Volatility 3 Framework 2.4.1
Progress:  100.00   PDB scanning finished
PID PPID  ImageFileName Offset(V) Threads Handles SessionId Wow64 CreateTime  ExitTime  File output

2040  5888  mysterygift.ex  0xc0090b52e4c0  3 - 1 False 2022-11-23 10:15:19.000000  N/A Disabled

```

{% hint style="info" %}
```
mysterygift.exe
```
{% endhint %}

## What is the Process ID (PID) of this binary?

Answer was given in the previous command

{% hint style="info" %}
```
2040
```
{% endhint %}

## Dump the contents of this binary. How many files are dumped?

```bash
python3 vol.py -f workstation.vmem windows.dumpfiles --pid 2040
```

<figure><img src="../../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
16
{% endhint %}
