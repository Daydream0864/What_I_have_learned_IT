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

(**Zu jedem Thema sind zunächst die Ressourcen wie Videos oder Websites aufgeführt. Danach eine Zusammenfassung der Themen**)

# Helpdesk
- Helpdesk ist Kunden Support 
- Kunden senden "Tickets" (Arbeitsaufgaben, Ziele) und der Helpdesk-Support wird die Probleme lösen.
- Ticketsysteme ist der Ort wo alle Tickets gesendet werden
- Verwendung von Remote-PC-Diensten wie TeamViewer oder RDP (Remote-Desktop-Protokoll) oder per Telefonanruf zur Lösung der Probleme
- Netzwerkadministration von [[#Active Directory]] oder Cloud-Diensten von [[#Microsoft 360]]
- Hinzufügen neuer Benutzer zum Active Directory oder Erstellen von Gruppenrichtlinien für Sicherheitsbelangen 
- Freundliches Verhalten und Problemlösung für die Bedürfnisse der Kunden
- Fahrt zum Standort, wenn nötig, um das Problem zu lösen oder Präsenz zu zeigen

# IP - Configuration
## IP - Adresse
- 192.168.1.34 = 192.168.1 ist der Netzwerkanteil / 34 ist der Hostanteil
- Eine IP-Adresse identifiziert eindeutig ein Gerät in einem Netzwerk
  Private IP : kommt von einem Heimnetzwerk wie *192.168.1.34*
  Öffentliche IP: kommt von einem Router oder Internet Service Provider (ISP) wie *29.231.183.222*
- Der Grund dafür, dass jede Zahl nur bis zu 255 reichen kann, ist, dass jede der Zahlen in Wirklichkeit eine achtstellige Binärzahl ist (manchmal auch als Oktett bezeichnet). In einem Oktett wäre die Zahl Null 00000000, während die Zahl 255 11111111 wäre, also die maximale Zahl, die das Oktett erreichen kann. Die IP-Adresse, die wir bereits erwähnt haben (192.168.1.34), würde im Binärformat folgendermaßen aussehen: 11000000.10101000.00000001.0010001
- Das Binärformat ist wichtig. Es wird für die Subnetzbildung verwendet. 
## Subnetzmaske
- 255.255.255.0 = 255.255.255 ist das Netzwerk / 0 = kann alles sein
- In den meisten einfachen Netzwerken werden Sie Subnetzmasken wie 255.255.255.0 sehen, bei denen alle vier Zahlen entweder 255 oder 0 sind. Die Position der Änderungen von 255 bis 0 zeigt die Unterteilung zwischen der Netzwerk- und Host-ID an. Die 255er "maskieren" die Netzwerk-ID aus der Gleichung heraus.
- Die Subnetzmaske bestimmt, welcher Teil der IP-Adresse die Netzwerkkennung und welcher Teil die Hostkennung ist.
## Die Standard-Gateway-Adresse
- 192.168.178.1 = ist das Standard-Gateway 1 ist immer der Router
- Neben der IP-Adresse selbst und der zugehörigen Subnetzmaske wird auch eine Standard-Gateway-Adresse zusammen mit den IP-Adressierungsinformationen aufgeführt. Je nach Plattform, die Sie verwenden, kann diese Adresse anders heißen. Sie wird manchmal als "Router" bezeichnet.
## Subnetting
- Mit Subnetting können Sie mehrere logische Netzwerke erstellen. 
- Beim IP-Subnetting wird ein großes IP-Netzwerk in kleinere IP-Netzwerke aufgeteilt. Beim Subnetting werden aus einem einzigen großen IP-Netz mehrere kleine, verwaltbare Netze gebildet.
- Wenn wir mehr als 16000000 Hosts in ein einziges Netzwerk setzen, wird dieses Netzwerk aufgrund von Broadcast und Kollisionen nicht funktionieren, um die verfügbaren Adressen optimal zu nutzen. Wenn wir weniger Hosts einsetzen, werden die verbleibenden Adressen verschwendet. Das Subnetting bietet eine bessere Möglichkeit, mit dieser Situation umzugehen. Mit Subnetting können wir aus einem einzigen großen Netzwerk kleinere Netzwerke erstellen, die nicht nur die Anforderungen unserer Hosts erfüllen, sondern auch verschiedene andere Netzwerkvorteile bieten.
### Beispiel
192.168.1.0 = 11000000.10101000.00000001.0000000
255.255.255 = 11111111.11111111.11111111.0000000
192 im Binärformat = 128+64 =192

128 | 64 | 32 | 16 | 8 | 4 | 2 | 1 |
--| -- | -- | -- | -- | -- | -- | -- |
1 | 1 | 0 | 0 | 0 | 0 | 0 | 0 |

Subnetzmaske im Binärformat = alle Oktetsummen aller Zahlen (+) (255)

# DNS
- DNS: Domänennamensystem oder Domänennamenserver
- DNS ist ein Name wie google.com, eigentlich eine IP-Adresse
- löst Namen in Zahlen auf `Google.com = 8.8.8.8`
- Es wird oft als das Telefonbuch des Internets bezeichnet. Menschen greifen online über Domänennamen auf Informationen zu

# Switches, Hubs, Router (Hardware)
- **Hubs** are sending a Broadcast to all computers (sending to all computers) (port Ethernet)
- **Switches** are sending to a specific computer/IP (stores MAC Adresse to specify which PC)      (port Ethernet)
- **Router** looking up IP Adresse if it's for there network or a different one.  it send the Request to that specific network. gateway for a network.
- Hubs and switches is for building a network. Routers is for connecting Networks
## VLAN
- VLANS is a physical isolation of a switch. 
- switches are able to connect to other switches via a port called "trunk"
-  VLANs can also bring security benefits by allowing greater control over which devices have local access to each other.
- At a high level, network administrators can set up new VLANs by choosing a valid VLAN number and a private IP address range for devices on that VLAN to use. They then configure the switch device with either static or dynamic settings. In static configurations, the administrator assigns a VLAN number to each switch port.

# Netzwerktopologie
- Peer-to-Peer-Netz. ist der Oberbegriff für diese Netze. Alle Clients sind miteinander verbunden. 
- **Busnetz.** In der Topologie des [Busnetzes](https://www.techtarget.com/searchnetworking/definition/bus-network) ist jeder Knoten über ein einziges Kabel in Reihe geschaltet. Diese Anordnung findet man heute vor allem in Kabel-Breitbandverteilernetzen.
- **Sternnetz.** In der Topologie des [Sternnetzes](https://www.techtarget.com/searchnetworking/definition/star-network) ist ein zentrales Gerät über einen zentralen Hub mit allen anderen Knoten verbunden. Vermittelte lokale Netzwerke auf der Grundlage von Ethernet-Switches und die meisten verkabelten Heim- und Büronetzwerke haben eine physische Sterntopologie.
- **Ringnetz.** In der Topologie des [Ringnetzes](https://www.techtarget.com/whatis/definition/ring-network) sind die Knoten in einer geschlossenen [Konfiguration](https://www.techtarget.com/whatis/definition/configuration) verbunden. Einige Ringe leiten Daten nur in eine Richtung weiter, während andere in beide Richtungen übertragen können. Diese bidirektionalen Ringnetze sind widerstandsfähiger als Busnetze, da der Verkehr einen Knoten in beiden Richtungen erreichen kann. Metro-Netze, die auf der Technologie der synchronen optischen Netze basieren, sind das wichtigste Beispiel für Ringnetze.
- **Maschennetz.** Die Topologie des [Maschennetzes](https://internetofthingsagenda.techtarget.com/definition/mesh-network-topology-mesh-network) verbindet Knoten mit Verbindungen, so dass zumindest zwischen einigen Punkten des Netzes mehrere Pfade verfügbar sind. Ein Netz gilt als _voll vermaschend_, wenn alle Knoten direkt mit allen anderen Knoten verbunden sind, und _teilweise vermaschend_, wenn nur einige Knoten mehrere Verbindungen zu anderen haben. Die Vermaschung mehrerer Pfade erhöht die Ausfallsicherheit, aber auch die Kosten. Es wird jedoch mehr Platz für dedizierte Verbindungen benötigt.
- **Baumnetz.** Die Topologie des Baumnetzes besteht aus einem Wurzelknoten, und alle anderen Knoten sind in einer Hierarchie verbunden. Die Topologie selbst ist sternförmig verbunden. Viele größere Ethernet-Switch-Netzwerke, einschließlich der Netzwerke von Rechenzentren, sind als Bäume konfiguriert.
- **Hybridnetz** Die hybride Netztopologie ist eine beliebige Kombination aus zwei oder mehr Topologien. Hybride Topologien bieten in der Regel außergewöhnliche Flexibilität, da sie eine Reihe von Konfigurationen zulassen. So können sich beispielsweise verschiedene Abteilungen desselben Unternehmens für personalisierte Netzwerktopologien entscheiden, die sich besser an ihre Netzanforderungen anpassen lassen.

# Server
- Server ist ein Computer, der für einen bestimmten Dienst wie Webserver, Datenbankserver, E-Mail-Server, Dateiserver
- Server sind robuster als Heim-PCs
- CPU-Prozessoren haben die Fähigkeit zur Mehrfachverarbeitung, d.h. Stapel von CPU-Kernen (Intel XEON)
  - Höhere Kernanzahl 
  - größerer Cache
  - mehr RAM zugefügt
- RAM hoher Arbeitsspeicher GB ECC RAM (Error-Connecting Code)
- HDD hot swappable. Festplattenwechsel ohne Ausschalten des Hostsystems
- Verwendete Betriebssysteme wie Linux-Server, Windows-Server, MacOS
- Horizontale Skalierung = Duplizieren von Servern (Erstellen neuer Server)
- Vertikale Skalierung = Aufrüstung der Hardware (Kauf von mehr Ram oder CPU usw.)
## Arten von Servern
### 1. Web-Server
Ein Open-Source-Webserver wird für den Zugriff auf das World Wide Web über Public-Domain-Software verwendet. Diese Server verbinden gespeicherte Informationen von einer Internet-Website mit Ihrem eigenen Computer.
### 2. Proxy-Server
Proxyserver fungieren als Brücke zwischen einem Host-Server und einem Client-Server. Ein Proxy sendet Daten von einer Website an die IP-Adresse Ihres Computers, nachdem sie den Proxy-Server passiert haben.
### 3. Virtuelle Maschine (VM)
Wie der Name schon sagt, speichern und verbinden virtuelle Maschinen Daten ausschließlich in einem virtuellen Raum. Um eine virtuelle Maschine zu erstellen, verwenden IT-Teams einen Hypervisor, auch bekannt als Virtual Machine Monitor (VMM).
### 4. FTP-Server (File Transfer Protocol)
FTP-Server werden verwendet, um Dateien von einem Computer auf einen anderen zu verschieben. Hochgeladene Dateien werden von Ihrem Computer auf den Server übertragen, während heruntergeladene Dateien vom Server auf Ihr Gerät extrahiert werden. Das Dateiübertragungsprotokoll bezieht sich auch auf die Methode, einen Server zu verwenden, um einen Computer mit einem anderen zu verbinden, um Daten sicher auszutauschen.
### 5. Anwendungsserver
Diese Server verbinden Clients über virtuelle Serververbindungen mit Softwareanwendungen. Auf diese Weise können Benutzer das Herunterladen von Daten auf ihre eigene Hardware umgehen, um auf Anwendungen zuzugreifen.
### 6. Dateiserver
Ein Dateiserver speichert Datendateien für mehrere Benutzer. Sie ermöglichen einen schnelleren Datenabruf und das Speichern oder Schreiben von Dateien auf einem Computer.
### 7. Datenbank-Server
Database servers function as large storage spaces that organizations use and access to run multiple programs to meet their needs.
### 8. Mail server
A mail server stores and delivers mail for clients through email service platforms.
### 9. Collaboration server
When work needs to be shared across multiple users, a collaboration server makes it easy to connect. These servers allow you to share and store files, applications and other large amounts of data.
### 10. Monitoring and management server
Monitoring and management servers function in several capacities. First, they record and track digital transactions and receive user requests. Others simply monitor and don't actively participate in user operations. Überwachungsserver reagieren darauf, dass Netzwerkadministratoren den Zustand des Netzwerks überwachen, um nach Bedrohungen oder Fehlern im System zu suchen.
## Ports numbers
https://youtu.be/aQoFR6m1yOM<br/>https://www.ionos.de/digitalguide/server/knowhow/tcp-und-udp-ports/<br/>https://youtu.be/RDotMcs0Erg
- Port ist keine physische Verbindung
- es ist eine logische Verbindung, die von Programmen und Diensten zum Austausch von Informationen verwendet wird
- er bestimmt speziell, welches Programm oder welcher Dienst auf einem Computer oder Server verwendet wird, wie z.B.: Webseite, FTP-Dienst, E-Mail
- Eine Portnummer ist eine Möglichkeit, einen bestimmten Prozess zu identifizieren, an den eine Internet- oder andere Netzwerknachricht weitergeleitet werden soll, wenn sie bei einem [Server] (https://www.techtarget.com/whatis/definition/server) ankommt. Alle an das Netzwerk angeschlossenen Geräte sind mit standardisierten Ports ausgestattet, denen eine Nummer zugewiesen ist. Diese Nummern sind für bestimmte [Protokolle](https://www.techtarget.com/searchnetworking/definition/protocol) und ihre zugehörige Funktion reserviert. Hypertext Transfer Protocol ([HTTP](https://www.techtarget.com/whatis/definition/HTTP-Hypertext-Transfer-Protocol))-Nachrichten zum Beispiel gehen immer an [Port 80](https://www.techtarget.com/searchnetworking/definition/port-80) -- einer der am häufigsten verwendeten Ports.
- Denken Sie daran, dass eine IP-Adresse als logische Kennung für einen Computer in einem Netzwerk verwendet wird und dass ein logischer Port eine Kennung ist, die einer Anwendung zugewiesen wird. Einfacher ausgedrückt könnte man ein Netzwerk-Subnetz als eine Straße in einer Stadt (das Unternehmensnetzwerk) betrachten, eine IP-Adresse in diesem Subnetz, die einem Host zugewiesen ist, als ein Haus in dieser Straße und logische Ports als Fenster/Türen, durch die man auf das Haus zugreifen kann.
### Wofür wird die Portnummer 8080 verwendet?
Die Portnummer 8080 wird normalerweise für [Webserver] (https://www.techtarget.com/whatis/definition/Web-server) verwendet. Wenn eine Portnummer an das Ende des Domänennamens angehängt wird, leitet sie den Verkehr zum Webserver. Allerdings können Benutzer den Port 8080 nicht für sekundäre Webserver reservieren.
### Wofür wird Portnummer 3360 verwendet?
[TCP/IP](https://www.techtarget.com/searchnetworking/definition/TCP-IP) Netzwerke verwenden Port 3360. Das verbindungsorientierte Protokoll TCP erfordert ein Handshaking, um eine durchgängige Kommunikation aufzubauen. Nach dem Aufbau der Verbindung werden die Nutzdaten bidirektional über die Verbindung übertragen.
## Beispiel für einen Server (Dateifreigabe)
Erstellung eines File-Sharing-Servers mit Linux-Server in einem Netzwerk (Proxmox) unter Verwendung von Samba.
und einem FTP-Server auf einem Windows Server OS. LINUX-Server :
  - **Linux** und Windows sind in der Lage, ihn zu benutzen (Benutzer braucht ggf. Berechtigungen)

# Windows server/Active directory
- Windows Server ist für den Einsatz in einer Netzwerkumgebung konzipiert und bietet Funktionen wie Active Directory, mit denen Administratoren Benutzer und Computer in einem Netzwerk verwalten können. Außerdem bietet er Funktionen wie die Gruppenrichtlinie, mit der Administratoren Einstellungen für Benutzer und Computer in einem Netzwerk verwalten können. 
## Active directory
https://www.makeuseof.com/tag/windows-domain/
Active Directory (AD) ist ein proprietärer Verzeichnisdienst von Microsoft, der auf Windows Server läuft. Er ermöglicht es Administratoren, Berechtigungen und den Zugriff auf Netzwerkressourcen zu verwalten, indem Daten als Objekte gespeichert werden. Er ist in den meisten Windows Server-Betriebssystemen als eine Reihe von Prozessen und Diensten enthalten. AD DS (Active Directory Domain Services) stellt die Methoden zum Speichern von Verzeichnisdaten und zur Bereitstellung dieser Daten für Netzwerkbenutzer und Administratoren bereit. Verwaltung von Domänen/PC für die Berechtigungen der Benutzer. Verwaltung von Benutzernetzwerken. Es ist eine verteilte, hierarchische Datenbank, die Informationen über Benutzer, Computer, Gruppen, Geräte und andere Objekte speichert. Active Directory ermöglicht es Netzwerkadministratoren, Domänen, Benutzer und Objekte innerhalb eines Netzwerks zu erstellen und zu verwalten. Es bietet eine gemeinsame Schnittstelle zum Auffinden, Sichern und Organisieren dieser Ressourcen
 - Erstellen und Verwalten von Benutzern
 - Benutzerrichtlinien einschränken 
### Beispiel eines Windows-Servers 
 - Ich habe Windows Server auf Proxmox installiert
 - Ich habe Benutzer und Gruppen erstellt
 - Ich habe einen FTP-Dienst eingerichtet, über den die Benutzer Dateien austauschen können.
 - Ich habe einen Ordner im Netzwerk freigegeben (Shared Folder Methode)
#### Windows Server FTP
https://youtu.be/dGEiwyBkS3w
- Ich habe einen FTP-Dienst auf einem **Windows-Server** eingerichtet, mit dem ich Dateien im Netzwerk austauschen kann.
- Ich konnte auch herausfinden, wie man Ordner mit der Methode "Freigegebener Ordner" freigibt. und ich habe 2 Benutzern erlaubt, Dateien in einem Domänennetzwerk auszutauschen.
## Domäne
https://youtu.be/ut_oLhMhJsY
<u>Mindestens ein Server, **Domänencontroller** genannt, ist für die anderen Geräte zuständig. Dadurch können die Netzwerkadministratoren (in der Regel IT-Mitarbeiter) die Computer in der Domäne über Benutzer, Einstellungen und mehr steuern. Eine Windows-Domäne ist im Wesentlichen ein Netzwerk von kontrollierten Computern, das in einem geschäftlichen Umfeld verwendet wird.</u>
## Microsoft 360
- MS SharePoint: Website-Erstellung und Organisation von Teams
- Microsoft Teams für die Verwaltung von Teams und Terminen 
- Microsoft 365 Cloud / Power Plattform

# Cloud Technologie
Einfach ausgedrückt ist Cloud Computing die Bereitstellung von Computerdiensten - einschließlich Servern, Speicher, Datenbanken, Netzwerken, Software, Analysen und Intelligenz - über das Internet ("die Cloud"), um schnellere Innovationen, flexible Ressourcen und Skaleneffekte zu ermöglichen. In der Regel zahlen Sie nur für die in Anspruch genommenen Cloud-Dienste, was Ihnen hilft, Ihre Betriebskosten zu senken, Ihre Infrastruktur effizienter zu betreiben und die Skalierbarkeit zu erhöhen, wenn sich Ihre Geschäftsanforderungen ändern.
## Die wichtigsten Vorteile
 - Kosteneinsparungen:
 - Skalierbarkeit
 - Flexibilisierung
 - Wiederherstellung im Katastrophenfall
 - Vorteile für die Umwelt
## Cloud Computing-Dienste
1. Infrastruktur als Dienstleistung (IaaS): **IaaS**-Anbieter bieten ihren Kunden die Möglichkeit, IT-Infrastruktur nach Bedarf zu mieten. IaaS umfasst alle grundlegenden Bausteine des Cloud Computing, z. B. Speicher, Netzwerke und Server. Beliebte IaaS-Anbieter sind Amazon Web Services (AWS), Microsoft Azure und Google Cloud Platform (GCP).
2. Plattform-as-a-Service (PaaS): **PaaS**-Anbieter bieten ihren Kunden die Möglichkeit, Anwendungen auf einer Cloud-basierten Plattform zu entwickeln, auszuführen und zu verwalten. PaaS umfasst alles, was zum Erstellen und Ausführen einer Anwendung benötigt wird, z. B. einen Webserver, eine Datenbank und Entwicklungstools. Beliebte PaaS-Anbieter sind Heroku, AWS Elastic Beanstalk und Google App Engine.
3. Software-as-a-Service (SaaS): **SaaS**-Anbieter bieten Kunden die Möglichkeit, eine cloudbasierte Softwareanwendung zu nutzen. SaaS-Anwendungen werden in der Regel über einen Webbrowser bereitgestellt, und die Kunden müssen die Software nicht installieren oder verwalten. Zu den beliebten SaaS-Anwendungen gehören Google Docs, Microsoft Office 365 und Salesforce.
## Kernelemente des Cloud Computing
- Die wichtigsten Elemente des Cloud Computing sind:
   - Elastizität: Die Fähigkeit, die Leistung je nach Bedarf zu erhöhen oder zu verringern, um der Nachfrage gerecht zu werden.
   - Abrechnung nach Aufwand: Sie zahlen nur für die Ressourcen, die Sie nutzen, wenn Sie sie nutzen.
   - Selbstbedienung: Sie können Ihre eigenen Ressourcen bereitstellen und verwalten, ohne ein langwieriges Genehmigungsverfahren durchlaufen zu müssen.
   - Gemeinsam genutzte Ressourcen: Die Möglichkeit, Ressourcen mit anderen Nutzern zu teilen, um die Effizienz zu steigern und Kosten zu senken.
   - Mehrmandantenfähigkeit: Die Möglichkeit, mehrere Nutzer auf derselben Plattform zu haben, ohne dass jeder Nutzer über eigene Ressourcen verfügt.

# Virtualisierung

## Virtuelle Maschinen
Eine **virtuelle Maschine (VM)** ist eine softwarebasierte Simulation eines physischen Computersystems. Sie kann Programme und Betriebssysteme ausführen, Daten speichern, Verbindungen zu Netzwerken herstellen und andere Computerfunktionen ausführen. Eine VM verwendet Software auf einem physischen Computer, um die Funktionalität eines anderen Computers oder Betriebssystems zu replizieren oder zu emulieren. [Eine VM hat ihre eigene CPU, Arbeitsspeicher, Netzwerkschnittstelle und Speicher](https://www.avast.com/c-virtual-machine)
**Virtuelle Maschinen bilden ein komplettes Betriebssystem nach**
- VMWare und proxmox sind die verwendete Software (**Hypervisor1**)
  - **Typ 1** (oder native oder Bare-Metal) Hypervisoren laufen direkt auf der Hardware des Hosts, um die Hardware zu kontrollieren und Gastbetriebssysteme zu verwalten.
- VirtualBox und QEMU/KVM **(Hypervisor2**)
  - **Typ 2** (oder gehostete Hypervisors) laufen auf einem bestehenden Betriebssystem und werden zur Erstellung von VMs auf diesem Betriebssystem verwendet.
### Virtuelle Maschinen haben folgende Nachteile
1. Verbrauchen viel Speicherplatz
2. verbrauchen viel RAM
3. verbrauchen CPU-Leistung
### Vorteile virtueller Maschinen
1. Kostenersparnis
2. Software-Kompatibilität
3. Isolierung
## Container
- Im Kontext der Datenverarbeitung ist ein **Container** eine Standard-Softwareeinheit, die den Code und alle seine Abhängigkeiten zusammenfasst, damit die Anwendung schnell und zuverlässig von einer Computerumgebung zur anderen läuft.
- Container sind eine Abstraktion auf der Anwendungsebene, die Code und Abhängigkeiten zusammenfasst. Mehrere Container können auf demselben Rechner laufen und den Betriebssystemkern mit anderen Containern teilen, die jeweils als isolierte Prozesse im Benutzerraum laufen.
Ein Container ist eine Anwendung, die mit einem Paket aus :
 - Dateien
 - Konfiguration
 - Abhängigkeiten
zum Beispiel eine Website oder ein Programm nur für eine Anwendung.
#### Vorteile von Containern
1. Portabilität
2. Isolierung
3. Wirkungsgrad

# SQL
SQL (Structured Query Language) ist eine Standardsprache für den Zugriff auf und die Bearbeitung von Datenbanken. Sie ermöglicht die Ausführung von Abfragen an eine Datenbank, das Abrufen von Daten aus einer Datenbank, das Einfügen von Datensätzen in eine Datenbank, das Aktualisieren von Datensätzen in einer Datenbank, das Löschen von Datensätzen aus einer Datenbank, das Anlegen neuer Datenbanken, das Anlegen neuer Tabellen in einer Datenbank, das Anlegen gespeicherter Prozeduren in einer Datenbank, das Anlegen von Ansichten in einer Datenbank und das Festlegen von Berechtigungen für Tabellen, Prozeduren und Ansichten.
- SQL erstellt eine Tabelle mit Spalten und Zeilen wie eine Excel-Tabelle
- SQL-Datenverwaltungssystem (RDBMS = Relational (aufeinander bezogen)): PostgreSQL, Microsoft SQLserver, MYSQL
## Beispiel
- Erstellen einer Tabelle mit Spalten (id -> INT(Zahl)) (name-> VARCHAR(Zeichen 50 max lang) kann nicht NULL oder leer sein)
```sql
CREATE TABLE customers (
  id INT PRIMARY KEY,
  name VARCHAR(50) NOT NULL,
  email VARCHAR(50) UNIQUE,
  phone VARCHAR(15)
);
```

# Firewall
Eine Firewall ist ein Netzwerksicherheitsgerät, das den eingehenden und ausgehenden Netzwerkverkehr überwacht und Datenpakete auf der Grundlage einer Reihe von Sicherheitsregeln zulässt oder blockiert. Sie soll den unbefugten Zugang zu oder von einem privaten Netzwerk verhindern. Firewalls können sowohl in Hardware als auch in Software oder in einer Kombination aus beidem implementiert sein. Eine Firewall ist ein [Netzwerksicherheits]-Gerät (https://www.forcepoint.com/cyber-edu/network-security), das den ein- und ausgehenden Netzwerkverkehr überwacht und Daten [Pakete] (https://www.forcepoint.com/cyber-edu/packet-loss) auf der Grundlage einer Reihe von Sicherheitsregeln zulässt oder blockiert. Ihr Zweck ist es, eine Barriere zwischen Ihrem internen Netzwerk und dem eingehenden Verkehr von externen Quellen (wie dem Internet) zu errichten, um bösartigen Verkehr wie Viren und Hacker zu blockieren.

# Monitoring
- Bei der IT-Überwachung handelt es sich um einen Prozess, der Metriken über den Betrieb einer IT-Umgebung sammelt.....
- Das Überwachungssystem prüft die Verfügbarkeit, Auslastung, Funktionalität und Reaktionszeit der Dienste. Überschreitet eine Messung einen bestimmten Wert, wird der Fehlerzustand sofort gemeldet. Alle Messdaten werden archiviert und ermöglichen so die Erstellung von Prognosen.