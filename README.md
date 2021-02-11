# Lab INT-P4
This is my first lab to use InBand Network Telemetry with P4. To use this lab, you will need following requirements:

- Virtualbox
- Vagrant
- Ansible

# Purpose of the lab

Use InBand Network Telemetry to collect metadata from BMv2 switches. 

# Topology
![INT-P4 Topology](https://user-images.githubusercontent.com/10882149/107682204-cadb9780-6c7e-11eb-9492-eafb4ed509d7.png)

# Commands
- ``` vagrant up ``` will create four virtual machines and start the topology.
- ``` vagrant ssh host-1 ``` will make a ssh connection in a virtual machine host-1. This virtual machine has IP address 192.168.50.11
- ``` vagrant ssh host-2 ``` will make a ssh connection in a virtual machine host-2. This virtual machine has IP address 192.168.50.12

# Host-2
In host-2 you need run the python script (receive.py) for start server application.
- ``` cd /vagrant/code ```
- ``` sudo ./receive.py ```

# Host-1
In host-1 you need run the python script (send.py) for start client application.
- ``` cd /vagrant/code ```
- ``` sudo ./send.py 192.168.50.12 ```

# InBand Network Telemetry metadata
In host-2 terminal you can see metadata that were collected from switches. The metadata are:
- switchID_t: switch identifier
- ingress_port: for new packets, the number of the ingress port on which the packet arrived to the device.
- egress_port: the output port this packet is destined to.
- egress_spec: Can be assigned a value in ingress code to control which output port a packet will go to. 
- ingress_global_timestamp: a timestamp, in microseconds, set when the packet shows up on ingress. 
- egress_global_timestamp: a timestamp, in microseconds, set when the packet starts egress processing. 
- enq_timestamp: a timestamp, in microseconds, set when the packet is first enqueued.
- enq_qdepth: the depth of the queue when the packet was first enqueued, in units of number of packets (not the total size of packets).
- deq_timedelta: the time, in microseconds, that the packet spent in the queue.
- deq_qdepth: the depth of queue when the packet was dequeued, in units of number of packets (not the total size of packets).
