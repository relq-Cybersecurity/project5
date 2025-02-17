# Active Directory Security Assessment Report
## 1. Introduction

This document outlines the process of setting up a Windows Server environment with Active Directory (AD), securing its configurations, and conducting penetration testing using industry-standard tools. The purpose is to enhance system administration and security assessment skills.

**Goals:**

Build a fully functioning AD environment

Implement security best practices

Conduct penetration testing to identify vulnerabilities

**Tools Used:**

Windows Server

VirtualBox

Kali Linux

CrackMapExec, Mimikatz, BloodHound, Nmap, Enum4linux-ng, Impacket

## 2. Windows Server & Active Directory Setup

**Installation & Configuration**

Installed Windows Server and assigned a static IP

Configured hostname and updated system

Installed Active Directory Domain Services (AD DS)

Promoted server to domain controller (mydomain.local)

**Domain & Organizational Setup**

Configured DNS and created AD forest

Established key Organizational Units (OUs) (e.g., IT, Finance)

Created user accounts (Admin, StandardUser) and security groups

**Security Configuration**

Applied Group Policy settings for access control

Configured password policies and administrative restrictions

## 3. Penetration Testing Process

**Information Gathering**

Used Nmap for network scanning: nmap -A domain_ip

Enum4linux-ng for AD enumeration

**Exploitation**

CrackMapExec to test SMB shares

Mimikatz for credential dumping

Kerberoasting using Impacket (GetUserSPNs.py)

**Lateral Movement & Persistence**

Pass-the-Hash with Mimikatz

WinRM exploitation

Persistence via backdoor accounts & Group Policy manipulation

## 4. Findings & Analysis

Identified misconfigurations and security risks

Documented vulnerabilities and exploited weaknesses


### Before proceeding
.Must have an administrativ privilege on server
.Setup server with a static IP address
.Change the Windows Server name according to your company's naming standart
![im1](https://github.com/Sonakhach/project5/blob/main/Screenshot%20from%202025-02-17%2011-36-54.png)
![im1](https://github.com/Sonakhach/project5/blob/main/Screenshot%20from%202025-02-17%2011-39-16.png)
![im1](https://github.com/Sonakhach/project5/blob/main/Screenshot%20from%202025-02-17%2011-46-05.png)
![im1](onakhach/project5/blob/main/Screenshot%20from%202025-02-17%2011-43-31.png)
![im1](https://github.com/Sonakhach/project5/blob/main/Screenshot%20from%202025-02-17%2011-32-29.png)
