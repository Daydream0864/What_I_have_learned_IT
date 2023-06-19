# Helpdesk
https://youtu.be/b7VVaIiaeKY
https://youtu.be/Wb7cSHheFT8
- Helpdesk is customer support 
- customers sending "Tickets"(Aufträge, jobs, work task) helpdesk-support will solve the problem
- Ticketsystem where all the Tickets will be send
- Using Remote PC service like TeamViewer or RDP(remote desktop protocol) or via phone call
- Network Administration of [[#Active directory]] or cloud services [[#Microsoft 360]]
#
___
# IP- Adresse
https://youtu.be/B1vqKQIPxr0
https://youtu.be/oZGZRtaGyG8
https://youtu.be/po8ZFG0Xc4Q
https://youtu.be/s_Ntt6eTn94
Privat IP : comes from a home network
Public IP : comes from a router or internet service provider(ISP)
___
192.168.1.0 =192.168.178 is the network portion / 0 is the host portion
255.255.255.0 = 255.255.255 is the network/ 0 = can be anything
binary format is important. used for subnetting. 
____
## 8 BIT octet chart
128 | 64 | 32 | 16 | 8 | 4 | 2 | 1 |
___
## Example
192.168.1.0 =  11000000.10101000.00000001.0000000
255.255.255 = 11111111.11111111.11111111.0000000

*example :*
192 in binary = 128+64 =192
128 | 64 | 32 | 16 | 8 | 4 | 2 | 1 |
  1     1      0    0   0   0  0    0
Subnetmask in binary = all octet summery of all numbers (+)

-  **subnetting**: breaking a large network into small networks for better performance and manageability . computer send a messege to all computers in a network there for subnetting breaking network into smaller sections.

**192.168.178.1 = Router (default gateway)** ^0f699f
#
___
# DNS
https://youtu.be/mpQZVYPuDGU
- DNS: Domain name system or Domain name server
- DNS is a Name like google.com it's a IP adress
- resolves names into numbers
- computer types a domain/IP and send it to a ISP and ask if the server knows the domain. if not it ask 3 layers of others servers  **ROOT-server -> TDL Sever -> AU server.**
#
___
# Switches, Hubs, Router (hardware)
https://youtu.be/zFfattg5gd8
https://youtu.be/1z0ULvg_pW8
- **Hubs** are sending a Broadcast to all computers (sending to all computers) (port Ethernet)
- **Switches** are sending to a specific computer/IP (stores MAC Adresse to specify which PC)      (port Ethernet)
- **Router** looking up IP adress if it's for there network or a different one.  it send the Request to that specific network. gateway for a network.
- Hubs and switches is for building a network. Routers is for connecting Networks
## VLAN
- VLANS is a physical isolation of a switch. 
- switches are able to connect to other switches via a port called "trunk"
-  VLANs can also bring security benefits by allowing greater control over which devices have local access to each other.
- At a high level, network administrators can set up new VLANs by choosing a valid VLAN number and a private IP address range for devices on that VLAN to use. They then configure the switch device with either static or dynamic settings. In static configurations, the administrator assigns a VLAN number to each switch port.
#
___
# Networktopology
https://youtu.be/zbqrNg4C98U


- **Bus network.** In the [bus network](https://www.techtarget.com/searchnetworking/definition/bus-network) topology, every node is connected in series along a single cable. This arrangement is found today primarily in cable broadband distribution networks.
- **Star network.** In the [star network](https://www.techtarget.com/searchnetworking/definition/star-network) topology, a central device connects to all other nodes through a central hub. Switched local area networks based on Ethernet switches and most wired home and office networks have a physical star topology.
- **Ring network.** In the [ring network](https://www.techtarget.com/whatis/definition/ring-network) topology, the nodes are connected in a closed-loop [configuration](https://www.techtarget.com/whatis/definition/configuration). Some rings pass data in one direction only, while others are capable of transmission in both directions. These bidirectional ring networks are more resilient than bus networks since traffic can reach a node by moving in either direction. Metro networks based on Synchronous Optical Network technology are the primary example of ring networks.
- **Mesh network.** The [mesh network](https://internetofthingsagenda.techtarget.com/definition/mesh-network-topology-mesh-network) topology links nodes with connections so that multiple paths between at least some points of the network are available. A network is considered to be _fully meshed_ if all nodes are directly connected to all other nodes and _partially meshed_ if only some nodes have multiple connections to others. Meshing multiple paths increases resiliency but also increases cost. However, more space is needed for dedicated links.
- **Tree network.** The tree network topology consists of one root node, and all other nodes are connected in a hierarchy. The topology itself is connected in a star configuration. Many larger Ethernet switch networks, including data center networks, are configured as trees.
- **Hybrid network.** The hybrid network topology is any combination of two or more topologies. Hybrid topologies typically provide exceptional flexibility, as they can accommodate a number of setups. For example, different departments in the same organization may opt for personalized network topologies that are more adaptable to their network needs.
#
___
# Server
https://youtu.be/UjCDWCeHCzY
- Server is a computer that for a specific service like Webserver, Database server, Email server, file server
- server are more robust 
- CPU processors are have the capability for multy processors means stack CPU cores (Intel XEON)
  - Higher core count 
  -  larger Cache
  - more RAM to added
- RAM high RAM GB ECC RAM (error-Connecting Code)
- HDD hot swappable. HDD change with out turning off
- OS like Linux servers, windows servers
- Horizontal scaling = duplicate servers (making new servers)
- vertical scaling = upgrade hardware (purchase more ram ore CPU etc...)
## Ports
https://youtu.be/aQoFR6m1yOM
https://www.ionos.de/digitalguide/server/knowhow/tcp-und-udp-ports/
https://youtu.be/RDotMcs0Erg
-  port is not a physical connection
- it's a  logical connection that's used by programs and services to exchange Information
- it specifically determines which program o services on a computer or server that is going to be used like: Webpage, FTP Service, Email
- A port number is a way to identify a specific process to which an internet or other network message is to be forwarded when it arrives at a [server](https://www.techtarget.com/whatis/definition/server). All network-connected devices come equipped with standardized ports that have an assigned number. These numbers are reserved for certain [protocols](https://www.techtarget.com/searchnetworking/definition/protocol) and their associated function. Hypertext Transfer Protocol ([HTTP](https://www.techtarget.com/whatis/definition/HTTP-Hypertext-Transfer-Protocol)) messages, for example, always go to [port 80](https://www.techtarget.com/searchnetworking/definition/port-80) -- one of the most commonly used ports.
- An [IP address](https://www.techtarget.com/whatis/definition/IP-address-Internet-Protocol-Address) identifies a machine in an IP network and is used to determine the destination of a data [packet](https://www.techtarget.com/searchnetworking/definition/packet). Port numbers identify a particular application or service on a system
### What is port number 8080 used for?
Port number 8080 is usually used for [web servers](https://www.techtarget.com/whatis/definition/Web-server). When a port number is added to the end of the domain name, it drives traffic to the web server. However, users can not reserve port 8080 for secondary web servers.
### What is port number 3360 used for?
[TCP/IP](https://www.techtarget.com/searchnetworking/definition/TCP-IP) networks use port 3360. The connection-oriented protocol TCP demands handshaking to set up end-to-end communications. Upon establishing the connection, user data is transferred bidirectionally over the connection.
## Example of a Server(File sharing)
[[17-06-2023#Overview]]

#
___
# Windows server / Active directory/ Microsoft software
https://www.youtube.com/watch?v=85-bp7XxWDQ&t=1491s
https://youtu.be/6x4-vNmzuqU
https://youtu.be/Q4I2lKHboDw
https://youtu.be/0DLRRv6Evjo
https://youtu.be/cBe5nnnJbSQ

[Windows Server is designed to be used in a networked environment and provides features such as Active Directory, which allows administrators to manage users and computers in a network](https://www.makeuseof.com/tag/windows-server-different-windows/) [1](https://www.makeuseof.com/tag/windows-server-different-windows/). [It also provides features such as Group Policy, which allows administrators to manage settings for users and computers in a network](https://www.makeuseof.com/tag/windows-server-different-windows/)
- [[04-06-2023]]
- https://learn.microsoft.com/en-us/certifications/
## Active directory
Active Directory (AD) is a Microsoft proprietary directory service that runs on Windows Server. It enables administrators to manage permissions and access to network resources by storing data as objects1. It is included in most Windows Server operating systems as a set of processes and services2. AD DS (Active Directory Domain Services) provides the methods for storing directory data and making this data available to network users and administrators. Managing Domains/PC for permissions for Users. Managing of networks of Users. It is a distributed, hierarchical database that stores information about users, computers, groups, devices, and other objects 1. Active Directory allows network administrators to create and manage domains, users, and objects within a network 2. It provides a common interface for locating, securing, and organizing these resources
## Microsoft 360
- MS Sharepoint: website builder and organization of  teams
-  Microsoft 365 Cloud / Power Plattform
#
___
# Virtual Machines and containers
https://youtu.be/wX75Z-4MEoM
https://youtu.be/eyNBf1sqdBQ
https://www.youtube.com/watch?v=apC1bOLbzbY
## Virtual machines
a **virtual machine (VM)** is a software-based simulation of a physical computer system. It can run programs and operating systems, store data, connect to networks, and do other computing functions. A VM uses software on a physical computer to replicate or emulate the functionality of a different computer or operating system. [A VM has its own CPU, memory, network interface, and storage](https://www.avast.com/c-virtual-machine)
**Virtual machines recreate an entire Operating system**
- VMWare and proxmox are the used software (**Hypervisor1**)
  - **type 1** (or native or bare-metal) hypervisors run directly on the host’s hardware to control the hardware and manage guest operating systems.
- VirtualBox and QEMU/KVM **(Hypervisor2**)
  - **Type 2** (or hosted) hypervisors run on top of an existing operating system and are used to create VMs on top of that operating system.
### Virtuel machines disadvantages
1. Consume a lot of diskspace
2. consume a lot of RAM
3. consume CPU power
4. Slow to startup
5. license for OS
## Containers
https://youtu.be/eyNBf1sqdBQ
https://www.youtube.com/watch?v=eGz9DS-aIeY&t=1152s
**containers recreate an Application**
A container is an Applikation that's been packaged with :
 - Files
 - Configuration
 - Dependencies
necessary for it to run. for example a website or a program just for one applications.
#
---
# SQL
https://youtu.be/xiUTqnI6xk8
- SQL (Structured Query Language) is a standard language for accessing and manipulating databases. It lets you execute queries against a database, retrieve data from a database, insert records in a database, update records in a database, delete records from a database, create new databases, create new tables in a database, create stored procedures in a database, create views in a database and set permissions on tables, procedures and views.
- SQL creates a table with columns and rows like an excel spreadsheet
- SQL Data Management System (RDBMS = Relational (related to each other)): PostgreSQL, Microsoft SQLserver, MYSQL
## Example
-  create a Table with creating columns (id -> INT(number)) (name-> VARCHAR(characters 50 max long) can't be NULL or Empty)
```sql
CREATE TABLE customers (
  id INT PRIMARY KEY,
  name VARCHAR(50) NOT NULL,
  email VARCHAR(50) UNIQUE,
  phone VARCHAR(15)
);
```
#
___

