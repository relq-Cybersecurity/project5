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

# what is AD

Active Directory (AD) is a directory service used to manage users, computers, and other resources in a network. It organizes these elements using Organizational Units (OUs), Users, and Groups to apply policies, control access, and enhance security.

### Before proceeding
.Must have an administrativ privilege on server

![im1](https://github.com/Sonakhach/project5/blob/main/Screenshot%20from%202025-02-17%2011-39-16.png)

.Setup server with a static IP address

![im1](https://github.com/Sonakhach/project5/blob/main/Screenshot%20from%202025-02-17%2011-36-54.png)

.Change the Windows Server name according to your company's naming standart

![im1](https://github.com/Sonakhach/project5/blob/main/Screenshot%20from%202025-02-17%2011-43-31.png)



.Install the Active Domain Services role

![im1](https://github.com/Sonakhach/project5/blob/main/Screenshot%20from%202025-02-17%2011-46-05.png)

![im1](https://github.com/Sonakhach/project5/blob/main/Screenshot%20from%202025-02-17%2013-48-22.png)

.Promote the server to a Domain Controller

![im1](https://github.com/Sonakhach/project5/blob/main/Screenshot%20from%202025-02-17%2011-32-29.png)
![im1](https://github.com/Sonakhach/project5/blob/main/Screenshot%20from%202025-02-01%2016-48-30.png)

# what is Organizational Units (OUs)

An Organizational Unit (OU) is a container within Active Directory that helps organize users, groups, and computers. OUs allow administrators to manage and apply Group Policies to specific subsets of objects in AD.

**How to create OU, User and Groups on Active Directory**
![im1](https://github.com/Sonakhach/project5/blob/main/Screenshot%20from%202025-02-17%2013-54-42.png)

![im1](https://github.com/Sonakhach/project5/blob/main/Screenshot%20from%202025-02-17%2014-03-30.png)
![im1](https://github.com/Sonakhach/project5/blob/main/Screenshot%20from%202025-02-17%2014-06-31.png)
![im1](https://github.com/Sonakhach/project5/blob/main/Screenshot%20from%202025-02-17%2014-07-01.png)

# Users in Active Directory

A User in AD represents an individual account that can log in and access resources based on assigned permissions.

**Types of Users:**

  **. Domain Users: Regular user accounts created in AD (e.g., employees)**

  **. Administrator Users: Accounts with elevated privileges (e.g., Administrator)**

  **. Service Accounts: Used by applications/services instead of humans**

**Example:**

  **jdoe@mydomain.local (Regular user)**

  **admin@mydomain.local (Administrator user)**


# Groups in Active Directory

A Group is a collection of users that can be managed as a single unit. Instead of assigning permissions to individual users, they are assigned to groups for easier management.

**Types of Groups:**

  **. Security Groups: Used to assign permissions and access control**
  
  **. Distribution Groups: Used for email distribution (not for security)**
  
**Create Group and add users on it**

![im1](https://github.com/Sonakhach/project5/blob/main/Screenshot%20from%202025-02-17%2014-10-14.png)
![im1](https://github.com/Sonakhach/project5/blob/main/Screenshot%20from%202025-02-17%2014-23-38.png)
