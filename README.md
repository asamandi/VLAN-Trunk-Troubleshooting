VLAN / Trunk Troubleshooting
---

Goal
-------------------------------------------------
Prove that you can troubleshoot:

PC connectivity issues

VLAN problems

trunk problems

default gateway problems

switch configuration mistakes

Topology
-------------------------------------------------

PC1 -------- SW1 -------- R1
             |
             |
            SW2 -------- PC2

1 Router

2 Switches

2 PCs

IP Plan
-------------------------------------------------

| Device | Interface |        IP Address |      Gateway |
| ------ | --------- | ----------------- | ------------ |
| PC1    |       NIC | 192.168.10.10 /24 | 192.168.10.1 |
| PC2    |       NIC | 192.168.20.10 /24 | 192.168.20.1 |
| R1     |   G0/0.10 |  192.168.10.1 /24 |          N/A |
| R1     |   G0/0.20 |  192.168.20.1 /24 |          N/A |
