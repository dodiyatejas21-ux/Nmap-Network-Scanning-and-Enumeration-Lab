# Nmap-Network-Scanning-and-Enumeration-Lab

## Introduction

Nmap (Network Mapper) is a powerful open-source tool used for network discovery and security auditing. It helps identify active hosts, open ports, running services, service versions, and operating systems on a target system. In this project, different Nmap scanning and enumeration techniques are performed in an authorized lab environment to understand how network information can be discovered and analyzed.

## Objectives

- To understand the basics of Nmap and network scanning.
- To identify active hosts on a network.
- To scan and identify open and closed ports.
- To detect running services and their versions.
- To identify the operating system of a target system.
- To perform basic network enumeration using Nmap.
- To analyze and document the scan results.

## Requirements

- **Kali Linux** – Used for network scanning.
- **Nmap** – Used to scan hosts, ports, and services.
- **Terminal** – Used to run Nmap commands.
- **Target Machine (Metasploitable 2)** – Used as the authorized scanning target.
- **VMware** – Used to create the lab environment.
- **Networking Basics** – Required to understand IPs, ports, and services.

## Step 1: Lab Setup & Target Identification
In this step, Kali Linux and Metasploitable 2 are started in the virtual lab environment. The IP address of the Metasploitable 2 machine is identified before performing Nmap scanning.
### Command
ifconfig
or
ip addr
### Target IP Address
192.168.126.131
### Purpose
To identify the IP address of the Metasploitable 2 target machine for further Nmap scanning.
### Target
Metasploitable 2 – Authorized Lab Target

<img width="912" height="495" alt="image" src="https://github.com/user-attachments/assets/fb98173b-bdce-4fef-9f35-b5fabc436ae5" />

## Step 2: Host Discovery
In this step, Nmap is used to check whether the target machine is active and reachable on the network.
### Command
nmap -sn 192.168.126.131
### Purpose
To discover whether the Metasploitable 2 machine is active on the network.
### Target IP
192.168.126.131
### Expected Result
If the target is active, Nmap will show:

Host is up.

This confirms that the target machine is reachable and ready for further scanning.

<img width="553" height="131" alt="image" src="https://github.com/user-attachments/assets/c953bcd4-ff7e-47d6-8549-39d5d25dc8d6" />

## Step 3: Port Scanning
In this step, Nmap is used to scan the target machine and identify open TCP ports.

### Command
nmap -p- 192.168.126.131

### Purpose
To identify open ports and the services running on the Metasploitable 2 target.

### Target IP
192.168.126.131

### Expected Result
Nmap will display the open ports, port numbers, protocols, and associated services.

### Example Result

| Port | State | Service |
|------|-------|---------|
| 21/tcp | open | ftp |
| 22/tcp | open | ssh |
| 23/tcp | open | telnet |
| 25/tcp | open | smtp |
| 80/tcp | open | http |
| 139/tcp | open | netbios-ssn |
| 445/tcp | open | microsoft-ds |
| 3306/tcp | open | mysql |

Note: This is an example table. Actual results may vary depending on the Nmap scan.

<img width="629" height="645" alt="image" src="https://github.com/user-attachments/assets/b8045932-23bc-488a-be2b-4f078e866933" />

## Step 4: Service and Version Detection
In this step, Nmap is used to identify the services running on the open ports and detect their version information.

### Command
nmap -sV 192.168.126.131

### Purpose
To identify the running services and their versions on the Metasploitable 2 target.

### Target IP
192.168.126.131

### Example Result

| Port | State | Service | Version |
|------|-------|---------|---------|
| 21/tcp | open | ftp | vsftpd |
| 22/tcp | open | ssh | OpenSSH |
| 23/tcp | open | telnet | Linux telnetd |
| 80/tcp | open | http | Apache |
| 3306/tcp | open | mysql | MySQL |

Note: The actual service and version information may vary depending on the target configuration.

 
 
