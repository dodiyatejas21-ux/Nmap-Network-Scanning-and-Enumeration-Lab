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

 <img width="1030" height="582" alt="image" src="https://github.com/user-attachments/assets/c454bf55-7e3c-459c-8765-508434d6a40a" />
 
## Step 5: OS Detection
In this step, Nmap is used to identify the operating system of the target machine.

### Command
nmap -O 192.168.126.131

### Purpose
To detect the operating system running on the Metasploitable 2 target machine.

### Target IP
192.168.126.131

### Example Result
| Target IP | Detected Operating System |
|-----------|---------------------------|
| 192.168.126.131 | Linux 2.6.X |

### Result

The Nmap scan attempts to identify the operating system and provides information about the target's OS.

Note: OS detection may not always be accurate and can depend on the target configuration and network conditions.

<img width="769" height="632" alt="Screenshot 2026-08-19 162413" src="https://github.com/user-attachments/assets/fad232fd-84c1-4167-8a12-2605d0c10552" />

## Step 6: Vulnerability Scanning Using NSE
In this step, Nmap Scripting Engine (NSE) is used to perform basic vulnerability checks on the target machine.

### Command
nmap --script vuln 192.168.126.131

### Purpose
To identify potential vulnerabilities and security issues associated with the services running on the Metasploitable 2 target.

### Target IP
192.168.126.131

### Result
The NSE vulnerability scan checks the available services and reports potential security weaknesses found on the target system.

### Note
This scan is performed only on the authorized Metasploitable 2 lab environment.

<img width="1273" height="765" alt="Screenshot 2026-08-20 062037" src="https://github.com/user-attachments/assets/58660cde-874c-428c-89e8-f0a4414a32c0" />
<img width="1022" height="772" alt="Screenshot 2026-08-20 062613" src="https://github.com/user-attachments/assets/e255fe3f-5f50-4777-b14f-ff62ebcb3656" />
<img width="963" height="789" alt="Screenshot 2026-08-20 062801" src="https://github.com/user-attachments/assets/d2b25747-b2a0-4061-8e78-40f68e5dd559" />
<img width="1084" height="783" alt="Screenshot 2026-08-20 063013" src="https://github.com/user-attachments/assets/575d1d48-eb10-41b3-913e-68e6b851942a" />
<img width="1073" height="780" alt="Screenshot 2026-08-20 063104" src="https://github.com/user-attachments/assets/c4bdef21-703c-49d5-a399-551842a5c5b4" />
<img width="978" height="777" alt="Screenshot 2026-08-20 063142" src="https://github.com/user-attachments/assets/dd9af917-4149-451f-8433-465e18192173" />
<img width="958" height="784" alt="Screenshot 2026-08-20 063247" src="https://github.com/user-attachments/assets/0871fe67-2653-4638-b3c4-18c4f1cfbaf0" />
<img width="946" height="219" alt="Screenshot 2026-08-20 063316" src="https://github.com/user-attachments/assets/923816b1-4581-44ea-aeaa-2361153ebd18" />

## Step 7: Aggressive Scan
In this step, Nmap is used to perform an aggressive scan to gather detailed information about the target system.

### Command
nmap -A 192.168.126.131

### Purpose
To collect detailed information about the target, including open ports, services, service versions, operating system, and network information.

### Target IP
192.168.126.131

### Result
The aggressive scan provides detailed information about the Metasploitable 2 system and its running services.

### Information Gathered
- Open ports
- Running services
- Service versions
- Operating system details
- Network information
- Additional script-based information

### Note
This scan is performed only on the authorized Metasploitable 2 lab environment

<img width="1249" height="760" alt="Screenshot 2026-08-20 065940" src="https://github.com/user-attachments/assets/6a62dbec-bbd8-4fb0-9630-9516c89a1981" />
<img width="1402" height="783" alt="Screenshot 2026-08-20 070028" src="https://github.com/user-attachments/assets/5a382c55-4be6-49e7-bfd9-af0469194958" />
<img width="1077" height="516" alt="Screenshot 2026-08-20 070124" src="https://github.com/user-attachments/assets/edfa6c3c-6ba3-4fe1-8432-a97efdc01d8c" />




