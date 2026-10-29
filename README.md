# NETWORKWALKS-B084-2YU-WK1-PM1-CYBERSECURITY-LAB-SETUP
Isolated virtual cybersecurity lab built with VirtualBox and Kali Linux for ethical hacking practice. Networkwalks Internship, Week 1, Project Module 1.
📌 Project Overview

This project is Week 1, Project Module 1 of the Cybersecurity & Ethical Hacking Internship at Networkwalks IT Solutions & Training.

I built a virtual cybersecurity lab with VirtualBox and Kali Linux. It gives me a safe, isolated space to practise security tools for network scanning, reconnaissance and vulnerability assessment, with no risk to any real system.

The lab sits on a private virtual network, so I can later add further machines to act as targets for authorised testing.

🎯 Objectives
Install and configure VirtualBox
Import Kali Linux as a virtual machine
Set up a private NAT Network for the lab
Give the Kali VM a static IP address
Check network connectivity and DNS resolution
Save a clean VM snapshot as a recovery point
Record the whole process, including the problems met and how they were 

🛡️ Purpose of the Lab

The environment supports:

Network reconnaissance
Port scanning
Vulnerability assessment
Packet analysis
Web security testing
Safe experimentation with security tools

🐞 Problems Encountered and Solutions
Problem 1: Internet Access Lost After Setting a Static IP

After I set the IPv4 details by hand, the VM could lose internet access, depending on how Kali and NetworkManager were configured. The fix was to disable the duplicate address detection timeout on the connection:

sudo nmcli connection modify "Wired connection 1" ipv4.dad-timeout 0

Problem 2: VirtualBox VT-x / Virtualization Error

The VM would not start at first because hardware virtualization was switched off in the system firmware (BIOS/UEFI).

To fix it, I:

Restarted the computer
Opened the BIOS/UEFI settings
Turned on Intel VT-x (hardware virtualization)
Saved the changes
Restarted again
Launched the Kali VM

With virtualization enabled, the VM booted normally.

💡 What I Learned

This project taught me how to build and configure a virtual environment for cybersecurity practice. The key takeaways were:

1. NAT vs NAT Network

A plain NAT setup and a NAT Network have different uses. A NAT Network lets several VMs on the same virtual network talk to each other, while still translating addresses so they can reach the outside world. That makes it well suited to a multi-machine security lab.

2. Virtual Machine Networking

I learned how VirtualBox’s virtual network adapters attach VMs to different kinds of networks, and how the chosen configuration affects which machines can communicate.

3. Static IP Configuration

I practised setting and checking IPv4 addresses, subnet masks, gateways and DNS servers in Kali Linux.

4. VM Snapshots

A clean snapshot should be taken before any risky or experimental work. It gives a known-good state to return to for future exercises.

5. Documentation

Keeping a record of commands, configurations, screenshots, problems and solutions is a core part of professional cybersecurity work.
