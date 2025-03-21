# VLAN-Configuration-Guide-
A concise and efficient guide to configuring VLANs on a Cisco switch. Covers VLAN creation, port assignments, and verification to streamline network segmentation. Perfect for IT professionals and networking enthusiasts! ⚡💻
# VLAN Configuration on Cisco Switch

## Description
This document outlines the steps to configure VLANs on a Cisco switch. VLANs (Virtual Local Area Networks) are used to segment network traffic, improve security, and enhance network efficiency. This guide provides a step-by-step configuration, including VLAN creation, port assignment, and verification commands.

## Overview
This document provides the configuration steps for setting up VLANs on a Cisco switch. The VLANs are assigned specific ports to segment the network logically.

## Configuration Steps
1. Enter privileged EXEC mode:
   ```
   Switch>enable
   ```
2. Enter global configuration mode:
   ```
   Switch#configure terminal
   ```
3. Set the hostname:
   ```
   Switch(config)#hostname SW!
   ```
4. Create VLANs:
   ```
   SW!(config)#vlan 10
   SW!(config-vlan)#name AA
   SW!(config-vlan)#exit

   SW!(config)#vlan 20
   SW!(config-vlan)#name BB
   SW!(config-vlan)#exit

   SW!(config)#vlan 30
   SW!(config-vlan)#name CC
   SW!(config-vlan)#exit
   ```
5. Assign VLANs to ports:
   ```
   SW!(config)#interface range fa0/1-2
   SW!(config-if-range)#switchport mode access 
   SW!(config-if-range)#switchport access vlan 10
   SW!(config-if-range)#exit

   SW!(config)#interface range fa0/3-4
   SW!(config-if-range)#switchport mode access 
   SW!(config-if-range)#switchport access vlan 20
   SW!(config-if-range)#exit

   SW!(config)#interface range fa0/5-6
   SW!(config-if-range)#switchport mode access 
   SW!(config-if-range)#switchport access vlan 30
   SW!(config-if-range)#exit
   ```
6. Save the configuration:
   ```
   SW!#write memory
   ```
7. Verify the VLANs:
   ```
   SW!#show vlan brief
   ```

## VLAN Summary
| VLAN | Name | Assigned Ports |
|------|------|---------------|
| 10   | AA   | Fa0/1, Fa0/2  |
| 20   | BB   | Fa0/3, Fa0/4  |
| 30   | CC   | Fa0/5, Fa0/6  |


