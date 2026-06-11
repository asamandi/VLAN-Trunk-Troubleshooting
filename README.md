## VLAN and Trunk Troubleshooting Lab

### Objective
- This lab demonstrates how to troubleshoot a VLAN connectivity issue in a Cisco network.
- The issue was caused by an incorrect access VLAN assignment on a switchport.

---------------------------------------------------------------
### Topology
- PC1 is connected to SW1.
- PC2 is connected to SW2.
- SW1 and SW2 are connected using a trunk link.
- SW1 is connected to R1 using router-on-a-stick.

---------------------------------------------------------------
### Problem
- PC1 could not ping PC2.

---------------------------------------------------------------
### Symptoms
- Ping from PC1 to PC2 failed.
- PC1 gateway was reachable.
- PC2 gateway was not reachable correctly.

---------------------------------------------------------------
### Troubleshooting Commands Used
- show vlan brief
- show interfaces trunk
- show ip interface brief
- show interface fa0/1
- ping

---------------------------------------------------------------
### Root Cause
- SW2 interface Fa0/1 was assigned to VLAN 10.
- PC2 should have been assigned to VLAN 20.

---------------------------------------------------------------
### Fix
- interface fa0/1
- switchport mode access
- switchport access vlan 20

---------------------------------------------------------------
### Verification
- After correcting the VLAN assignment, PC1 successfully pinged PC2.

---------------------------------------------------------------
### Screenshots
This section documents the VLAN trunk troubleshooting process in two parts:
- Before Fix
- After Fix

### Before Fix / Broken State:

[router-subinterface-10.png](https://github.com/asamandi/VLAN-Trunk-Troubleshooting/blob/main/Screenshots-before-break/router-subinterface-10.png)
- Shows the router subinterface configuration for VLAN 10 before the fix.

[router-subinterface-20.png](https://github.com/asamandi/VLAN-Trunk-Troubleshooting/blob/main/Screenshots-before-break/router-subinterface-20.png)
- Shows the router subinterface configuration for VLAN 20 before the fix.

[show-interfaces-trunk.png](https://github.com/asamandi/VLAN-Trunk-Troubleshooting/blob/main/Screenshots-before-break/show-interfaces-trunk.png)
- Shows the trunk status before the fix.

[show-vlan-brief.png](https://github.com/asamandi/VLAN-Trunk-Troubleshooting/blob/main/Screenshots-before-break/show-vlan-brief.png)
- Shows VLAN membership before the fix.

[successful-pc1-to-pc2-ping.png](https://github.com/asamandi/VLAN-Trunk-Troubleshooting/blob/main/Screenshots-before-break/successful-pc1-to-pc2-ping.png)
- Shows the connectivity test before the break/fix scenario.

### After Fix

[pc1-cannot-ping-pc2.png](https://github.com/asamandi/VLAN-Trunk-Troubleshooting/blob/main/Screenshots-after-fix/pc1-cannot-ping-pc2.png)
- Shows the broken state where PC1 could not ping PC2.

[sw2-wrong-vlan.png](https://github.com/asamandi/VLAN-Trunk-Troubleshooting/blob/main/Screenshots-after-fix/sw2-wrong-vlan.png)
- Shows the incorrect VLAN assignment on SW2.

[trunk-status.png](https://github.com/asamandi/VLAN-Trunk-Troubleshooting/blob/main/Screenshots-after-fix/trunk-status.png)
- Shows trunk verification during troubleshooting.

[sw2-fixed-vlan.png](https://github.com/asamandi/VLAN-Trunk-Troubleshooting/blob/main/Screenshots-after-fix/sw2-fixed-vlan.png)
- Shows the corrected VLAN configuration on SW2.

[show-vlan-brief-after-fix.png](https://github.com/asamandi/VLAN-Trunk-Troubleshooting/blob/main/Screenshots-after-fix/show-vlan-brief-after-fix.png)
- Shows VLAN membership after the fix.

[successful-ping-after-fix.png](https://github.com/asamandi/VLAN-Trunk-Troubleshooting/blob/main/Screenshots-after-fix/successful-ping-after-fix.png)
- Shows successful ping after troubleshooting.

---------------------------------------------------------------
### Skills Demonstrated
- VLAN troubleshooting
- Trunk verification
- Router-on-a-stick verification
- Layer 2 troubleshooting
- End-to-end connectivity testing
