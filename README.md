# What I have learned so far in IT
- [Helpdesk](#helpdesk)
- [IP-Adresse](#ip-adresse)
- [DNS](#dns)
- [Switches,Hubs,Router](#switcheshubsrouter)
- [Networktopology](#networktopology)
- [Server](#server)
- [Windows server](#windows-server)
- [Virtual Machines and containers](#virtual-machines-and-containers)
- [SQL](#sql)
- [firewall](#firewall)
- [Cloud Technologie](#cloud-technologie)

(**THIS IS A COPY AND PASTE FROM MY OBSIDIAN FILE, STRUCTURE WILL CHANGE AND MORE CONTENT ADDED**)<br/>
(**Every Topic has first the resources like Videos or websites listed. After that a summery of Topics**)

# Helpdesk
https://youtu.be/b7VVaIiaeKY
https://youtu.be/Wb7cSHheFT8
- Helpdesk is customer support 
- customers sending "Tickets" (work tasks, objectives) and helpdesk-support will solve the problems
- Ticketsystems are where all the Tickets will be send
- Using Remote PC service like TeamViewer or RDP(remote desktop protocol) or via phone call to solve the Issues
- Network Administration of [[#Active directory]] or cloud services [[#Microsoft 360]]
- Adding new Users to the Active directory or creating group policies for safety concerns 
- Friendly behavior and problem solving for the costumers needs
- driving to the location if necessary to solve the problem or to take presence
___
# IP - Configuration
https://youtu.be/B1vqKQIPxr0<br/>https://youtu.be/oZGZRtaGyG8<br/>https://youtu.be/po8ZFG0Xc4Q<br/>https://youtu.be/s_Ntt6eTn94<br/>https://youtu.be/pCcJFdYNamc<br/>[How Do IP Addresses Work? (howtogeek.com)](https://www.howtogeek.com/341307/how-do-ip-addresses-work/)
## IP - Adresse
- 192.168.1.34 = 192.168.1 is the network portion / 34 is the host portion
- An IP address uniquely identifies a device on a network
  Privat IP : comes from a home network like *192.168.1.34*
  Public IP : comes from a router or internet service provider(ISP) like *29.231.183.222*
- The reason each number can only reach up to 255 is that each of the numbers is really an eight digit binary number (sometimes called an octet). In an octet, the number zero would be 00000000, while the number 255 would be 11111111, the maximum number the octet can reach. That IP address we mentioned before (192.168.1.34) in binary would look like this: 11000000.10101000.00000001.0010001
- binary format is important. used for subnetting. 
## Subnet Mask
- 255.255.255.0 = 255.255.255 is the network / 0 = can be anything
- On most simple networks you’ll see subnet masks like 255.255.255.0, where all four numbers are either 255 or 0. The position of the changes from 255 to 0 indicate the division between the network and host ID. The 255s “mask out” the network ID from the equation.
- the subnet mask determine which part of the IP address is the network ID and which part the host ID
## The Default Gateway Address
-  192.168.178.1 =  is the Default Gateway 1 is always the router
- In addition to the IP address itself and the associated subnet mask, you’ll also see a default gateway address listed along with IP addressing information. Depending on the platform you’re using, this address might be called something different. It’s sometimes called the “router,”
## Subnetting
- Subnetting allows you to create multiple logical networks. 
- IP Subnetting is a process of dividing a large IP network in smaller IP networks. In Subnetting we create multiple small manageable networks from a single large IP network.
- To best utilize available addresses if we put more than 16000000 hosts in a single network, due to broadcast and collision, that network will never work. If we put less hosts then remaining addresses will be wasted. Subnetting provides a better way to deal with this situation. Subnetting allows us to create smaller networks from a single large network which not only fulfill our hosts’ requirement but also offer several other networking benefits.
### Example
192.168.1.0 =  11000000.10101000.00000001.0000000
255.255.255 = 11111111.11111111.11111111.0000000
192 in binary = 128+64 =192
128 | 64 | 32 | 16 | 8 | 4 | 2 | 1 |
  1     1      0    0   0   0  0    0
Subnetmask in binary = all octet summery of all numbers (+) (255)
___
# DNS
https://youtu.be/mpQZVYPuDGU
- DNS: Domain name system or Domain name server
- DNS is a Name like google.com it's actually an IP address
- resolves names into numbers `Google.com = 8.8.8.8`
-  It is often referred to as the phonebook of the Internet. Humans access information online through domain names
___
# Switches, Hubs, Router (Hardware)
https://youtu.be/zFfattg5gd8<br/>https://youtu.be/1z0ULvg_pW8
- **Hubs** are sending a Broadcast to all computers (sending to all computers) (port Ethernet)
- **Switches** are sending to a specific computer/IP (stores MAC Adresse to specify which PC)      (port Ethernet)
- **Router** looking up IP Adresse if it's for there network or a different one.  it send the Request to that specific network. gateway for a network.
- Hubs and switches is for building a network. Routers is for connecting Networks
## VLAN
- VLANS is a physical isolation of a switch. 
- switches are able to connect to other switches via a port called "trunk"
-  VLANs can also bring security benefits by allowing greater control over which devices have local access to each other.
- At a high level, network administrators can set up new VLANs by choosing a valid VLAN number and a private IP address range for devices on that VLAN to use. They then configure the switch device with either static or dynamic settings. In static configurations, the administrator assigns a VLAN number to each switch port.
___
# Networktopology
https://youtu.be/zbqrNg4C98U<br/>[NetSim™ Online (boson.com)](https://netsim.boson.com/labs/200-301/vlsm-practice-iii-m)
- **Peer to Peer network.** is the umbrella term for these networks. all clients are connected to each other. 
- **Bus network.** In the [bus network](https://www.techtarget.com/searchnetworking/definition/bus-network) topology, every node is connected in series along a single cable. This arrangement is found today primarily in cable broadband distribution networks.
- **Star network.** In the [star network](https://www.techtarget.com/searchnetworking/definition/star-network) topology, a central device connects to all other nodes through a central hub. Switched local area networks based on Ethernet switches and most wired home and office networks have a physical star topology.
- **Ring network.** In the [ring network](https://www.techtarget.com/whatis/definition/ring-network) topology, the nodes are connected in a closed-loop [configuration](https://www.techtarget.com/whatis/definition/configuration). Some rings pass data in one direction only, while others are capable of transmission in both directions. These bidirectional ring networks are more resilient than bus networks since traffic can reach a node by moving in either direction. Metro networks based on Synchronous Optical Network technology are the primary example of ring networks.
- **Mesh network.** The [mesh network](https://internetofthingsagenda.techtarget.com/definition/mesh-network-topology-mesh-network) topology links nodes with connections so that multiple paths between at least some points of the network are available. A network is considered to be _fully meshed_ if all nodes are directly connected to all other nodes and _partially meshed_ if only some nodes have multiple connections to others. Meshing multiple paths increases resiliency but also increases cost. However, more space is needed for dedicated links.
- **Tree network.** The tree network topology consists of one root node, and all other nodes are connected in a hierarchy. The topology itself is connected in a star configuration. Many larger Ethernet switch networks, including data center networks, are configured as trees.
- **Hybrid network.** The hybrid network topology is any combination of two or more topologies. Hybrid topologies typically provide exceptional flexibility, as they can accommodate a number of setups. For example, different departments in the same organization may opt for personalized network topologies that are more adaptable to their network needs.
___
# Server
https://youtu.be/UjCDWCeHCzY<br/>
- Server is a computer that for a specific service like Webserver, Database server, Email server, file server
- server are more robust than home PC
- CPU processors have the capability for multi processing, means stacks CPU cores (Intel XEON)
  - Higher core count 
  -  larger Cache
  - more RAM to added
- RAM high RAM GB ECC RAM (error-Connecting Code)
- HDD hot swappable. HDD change with out turning off the host system
- Operating System used like Linux servers, windows servers, MacOS
- Horizontal scaling = duplicate servers (making new servers)
- Vertical scaling = upgrade hardware (purchase more ram ore CPU etc...)
## Types of server
### 1. Web server
An open-source web server is used for accessing the world wide web through public domain software. These servers connect stored information from an internet website to your own computer.
### 2. Proxy server
Proxy servers act as a bridge between a host server and a client server. A proxy sends data from a website to your computer IP address after it passes through the proxy's server.
### 3. Virtual machine (VM)
As their name suggests, virtual machines store and connect data strictly through virtual space. To create a virtual machine, IT teams use a hypervisor, also known as a virtual machine monitor (VMM)
### 4. File transfer protocol (FTP) server
FTP servers are used to relocate files from one computer to another. Uploaded files move from your computer to the server while downloaded files are extracted from the server onto your device. File transfer protocol also refers to the method of using a server to connect one computer to another in order to share data safely.
### 5. Application server
These servers connect clients to software applications through virtual server connections. This allows users to bypass downloading data to their own hardware in order to access applications.
### 6. File server
A file server stores data files for multiple users. They allow for faster data retrieval and saving or writing files to a computer.
### 7. Database server
Database servers function as large storage spaces that organizations use and access to run multiple programs to meet their needs.
### 8. Mail server
A mail server stores and delivers mail for clients through email service platforms.
### 9. Collaboration server
When work needs to be shared across multiple users, a collaboration server makes it easy to connect. These servers allow you to share and store files, applications and other large amounts of data.
### 10. Monitoring and management server
Monitoring and management servers function in several capacities. First, they record and track digital transactions and receive user requests. Others simply monitor and don't actively participate in user operations. Monitoring servers are responsive to who network administrators survey network health to check for threats or bugs in the system.
## Ports numbers
https://youtu.be/aQoFR6m1yOM<br/>https://www.ionos.de/digitalguide/server/knowhow/tcp-und-udp-ports/<br/>https://youtu.be/RDotMcs0Erg<br/>
- port is not a physical connection
- it's a  logical connection that's used by programs and services to exchange Information
- it specifically determines which program o services on a computer or server that is going to be used like: Webpage, FTP Service, Email
- A port number is a way to identify a specific process to which an internet or other network message is to be forwarded when it arrives at a [server](https://www.techtarget.com/whatis/definition/server). All network-connected devices come equipped with standardized ports that have an assigned number. These numbers are reserved for certain [protocols](https://www.techtarget.com/searchnetworking/definition/protocol) and their associated function. Hypertext Transfer Protocol ([HTTP](https://www.techtarget.com/whatis/definition/HTTP-Hypertext-Transfer-Protocol)) messages, for example, always go to [port 80](https://www.techtarget.com/searchnetworking/definition/port-80) -- one of the most commonly used ports.
- Keep in mind that an IP address is used as a logical identifier for a computer on a network, and a logical port is an identifier assigned to an application. In simpler terms, we could consider a network subnet a street in a town (the corporate network), an IP address in that subnet assigned to a host as a house on that street, and logical ports as windows/doors that can be used to access the house.
### What is port number 8080 used for?
Port number 8080 is usually used for [web servers](https://www.techtarget.com/whatis/definition/Web-server). When a port number is added to the end of the domain name, it drives traffic to the web server. However, users can not reserve port 8080 for secondary web servers.
### What is port number 3360 used for?
[TCP/IP](https://www.techtarget.com/searchnetworking/definition/TCP-IP) networks use port 3360. The connection-oriented protocol TCP demands handshaking to set up end-to-end communications. Upon establishing the connection, user data is transferred bidirectionally over the connection.
## Example of a Server(File sharing)
created a file sharing server with Linux server on a network (Proxmox) using samba.
and a FTP server on a windows server OS. LINUX server :
  - **Linux** and windows are capable of using it.(User needs permissions if necessary)
___
# Windows server/Active directory
https://www.youtube.com/watch?v=85-bp7XxWDQ&t=1491s<br/>https://youtu.be/6x4-vNmzuqU<br/>https://youtu.be/Q4I2lKHboDw<br/>https://youtu.be/0DLRRv6Evjo<br/>https://youtu.be/cBe5nnnJbSQ<br/>https://learn.microsoft.com/en-us/certifications/
- Windows Server is designed to be used in a networked environment and provides features such as Active Directory, which allows administrators to manage users and computers in a network. It also provides features such as Group Policy, which allows administrators to manage settings for users and computers in a network. 

## Active directory
https://www.makeuseof.com/tag/windows-domain/<br/>
Active Directory (AD) is a Microsoft proprietary directory service that runs on Windows Server. It enables administrators to manage permissions and access to network resources by storing data as objects. It is included in most Windows Server operating systems as a set of processes and services. AD DS (Active Directory Domain Services) provides the methods for storing directory data and making this data available to network users and administrators. Managing Domains/PC for permissions for Users. Managing of networks of Users. It is a distributed, hierarchical database that stores information about users, computers, groups, devices, and other objects. Active Directory allows network administrators to create and manage domains, users, and objects within a network. It provides a common interface for locating, securing, and organizing these resources
 - creating and managing Users
 - restricting users policies 
### Example of Windows server 
 - I installed windows Server on Proxmox
 - I created Users and groups
 - I made an FTP service where users can exchange files
 - I shared folder in the network (Shared folder method)
#### Windows server FTP
https://youtu.be/dGEiwyBkS3w
- created a FTP service on a **Windows server** where I can share files in a network
- I also was able to figure out how to use share folders using: share folder method. and I granted 2 Users to share files between them in a Domain network.
## Domain
https://youtu.be/ut_oLhMhJsY<br/>
<u>At least one server, called a **Domain controller**, is in charge of the other devices. This lets the network administrators (usually IT staff) control the computers on the domain through users, settings, and more. A Windows domain is essentially a network of controlled computers used in a business setting.</u>
## Microsoft 360
- MS SharePoint: website builder and organization of  teams
- Microsoft teams for managing teams and Appointments 
- Microsoft 365 Cloud / Power Plattform
___
# Cloud Technologie
- Simply put, cloud computing is the delivery of computing services—including servers, storage, databases, networking, software, analytics, and intelligence—over the internet (“the cloud”) to offer faster innovation, flexible resources, and economies of scale. You typically pay only for cloud services you use, helping you lower your operating costs, run your infrastructure more efficiently, and scale as your business needs change
## Top benefits
 - Cost savings:
 - Scalability
 - Flexibility
 - Disaster recovery
 - Environmental benefits
## Cloud Computing Services
1. Infrastructure as a Service (IaaS): **IaaS** providers offer customers the ability to rent IT infrastructure on an as-needed basis. IaaS includes all the basic building blocks of cloud computing, such as storage, networking, and servers. Popular IaaS providers include Amazon Web Services (AWS), Microsoft Azure, and Google Cloud Platform (GCP).
2. Platform as a Service (PaaS): **PaaS** providers offer customers the ability to develop, run, and manage applications on a cloud-based platform. PaaS includes everything that is needed to build and run an application, such as a web server, database, and development tools. Popular PaaS providers include Heroku, AWS Elastic Beanstalk, and Google App Engine.
3. Software as a Service (SaaS): **SaaS** providers offer customers the ability to use a cloud-based software application. SaaS applications are usually delivered through a web browser, and customers do not need to install or manage the software. Popular SaaS applications include Google Docs, Microsoft Office 365, and Salesforce.
## Core Elements of Cloud Computing
- The key elements of cloud computing are:
   - Elasticity: The ability to scale up or down as needed, in order to meet demand.
   - Pay-as-you-go pricing: You only pay for the resources you use, when you use them.
   - Self-service: The ability to provision and manage your own resources, without needing to go through a lengthy approval process.
   - Shared resources: The ability to share resources with other users, in order to increase efficiency and reduce costs.
   - Multi-tenancy: The ability to have multiple users on the same platform, without each user having their own dedicated resources.
___
# Virtual Machines and containers
https://youtu.be/wX75Z-4MEoM<br/>https://youtu.be/eyNBf1sqdBQ<br/>https://www.youtube.com/watch?v=apC1bOLbzbY<br/>
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
### Virtuel machines advantages
1. Cost savings
2. Software compatibility
3. Isolation
## Containers
https://youtu.be/eyNBf1sqdBQ<br/>
https://www.youtube.com/watch?v=eGz9DS-aIeY&t=1152s
- In the context of computing, a **container** is a standard unit of software that packages up code and all its dependencies so the application runs quickly and reliably from one computing environment to another.
- Containers are an abstraction at the app layer that packages code and dependencies together. Multiple containers can run on the same machine and share the OS kernel with other containers, each running as isolated processes in user space
A container is an Applikation that's been packaged with :
 - Files
 - Configuration
 - Dependencies
necessary for it to run. for example a website or a program just for one applications.
#### Advantages of Containers
1. Portability
2. Isolation
3. Efficiency
___
# SQL
https://youtu.be/xiUTqnI6xk8<br/>
https://youtu.be/W2Z7fbCLSTw<br/>
https://github.com/donnemartin/system-design-primer#system-design-topics-start-here<br/>
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
___
# Firewall
A firewall is a network security device that monitors incoming and outgoing network traffic and permits or blocks data packets based on a set of security rules. It is designed to prevent unauthorized access to or from a private network. Firewalls can be implemented in both hardware and software, or a combination of both .A firewall is a [network security](https://www.forcepoint.com/cyber-edu/network-security) device that monitors incoming and outgoing network traffic and permits or blocks data [packets](https://www.forcepoint.com/cyber-edu/packet-loss) based on a set of security rules. Its purpose is to establish a barrier between your internal network and incoming traffic from external sources (such as the internet) in order to block malicious traffic like viruses and hackers.
___
# Monitoring
- IT monitoring is a process that gathers metrics on the operations of an IT environment....
- The monitoring system checks the availability, utilization, functionality and response time of the services. If a measurement exceeds a certain value, the error status is reported immediately. All measurement data are archived and thus enable forecasts to be drawn up.


