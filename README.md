# VLAN and Trunk Troubleshooting Lab


## Objective

This lab demonstrates how to troubleshoot a VLAN connectivity issue in a Cisco network.

The issue was caused by an incorrect access VLAN assignment on a switchport.


## Topology

PC1 is connected to SW1.

PC2 is connected to SW2.

SW1 and SW2 are connected using a trunk link.

SW1 is connected to R1 using router-on-a-stick.


## Problem

PC1 could not ping PC2.


## Symptoms

Ping from PC1 to PC2 failed.

PC1 gateway was reachable.

PC2 gateway was not reachable correctly.


## Troubleshooting Commands Used

show vlan brief

show interfaces trunk

show ip interface brief

show interface fa0/1

ping


## Root Cause

SW2 interface Fa0/1 was assigned to VLAN 10.

PC2 should have been assigned to VLAN 20.


## Fix

interface fa0/1

switchport mode access

switchport access vlan 20


## Verification

After correcting the VLAN assignment, PC1 successfully pinged PC2.


## Skills Demonstrated

VLAN troubleshooting

Trunk verification

Router-on-a-stick verification

Layer 2 troubleshooting

End-to-end connectivity testing
