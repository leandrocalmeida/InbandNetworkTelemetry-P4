# Lab INT-P4
This is my first lab to use In-band Network Telemetry with P4. To use this lab, you will need following requirements:

- Virtualbox
- Vagrant
- Ansible

# Purpose of the lab

Use In-band Network Telemetry to collect metadata from BMv2 switches. 

# Topology
![INT-P4 Topology](https://user-images.githubusercontent.com/10882149/107682204-cadb9780-6c7e-11eb-9492-eafb4ed509d7.png)

# Commands
- ``` vagrant up ``` will create four virtual machines and start the topology.
- ``` vagrant ssh host-1 ``` will make a ssh connection in a virtual machine host-1. This virtual machine has IP address 192.168.50.11
- ``` vagrant ssh host-2 ``` will make a ssh connection in a virtual machine host-2. This virtual machine has IP address 192.168.50.12
