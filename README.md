📄 Szenario 3: Einfaches internes Netzwerk (2 VMs, Ping-Test)
🎯 Zielsetzung
In diesem Szenario wird ein internes Netzwerk zwischen zwei virtuellen Maschinen (Windows 10 und Kali Linux) erstellt. Ziel ist es, die Netzwerkkonfiguration ohne DHCP zu simulieren und die Kommunikation durch statische IP-Adressen sicherzustellen.

💡 Warum dieses Szenario?
Da in realen IT-Umgebungen häufig Netzwerke ohne automatische IP-Vergabe (DHCP) existieren, ist es wichtig, die manuelle Konfiguration und den Test der Erreichbarkeit zu üben. Diese Übung dient dazu, Netzwerkkonzepte, Switch-Typen und IP-Konfigurationen besser zu verstehen.

🛠️ Was wurde gelernt?
Erstellen eines internen virtuellen Switches (ohne Verbindung zum physischen Netzwerk)

Zuweisung des Switches zu den virtuellen Maschinen

Statische IP-Konfiguration unter Windows mit netsh

Statische IP-Konfiguration unter Kali Linux mit ip addr

Test der Erreichbarkeit durch ping

Unterscheidung zwischen Extern / Intern / Privat Switch

🌐 IP-Konfiguration
VM	IP-Adresse	Subnetzmaske
Kali Linux	192.168.50.10	255.255.255.0
Windows 10	192.168.50.20	255.255.255.0

📸 Screenshots
![Szenario_3 photo_1](https://github.com/user-attachments/assets/4cd22b67-76ac-400e-9bf3-c918f8746e93)
![Szenario_3 photo_2](https://github.com/user-attachments/assets/3665d2f7-1f58-4afe-98b1-a929457ebdd1)
![Szenario_3 photo_3](https://github.com/user-attachments/assets/e840323f-de1a-4cb4-a2b9-bad0b4fbb0cb)

💻 Genutzte Befehle
Kali Linux

bash
Kopieren
Bearbeiten
sudo ip addr add 192.168.50.10/24 dev eth0
ping 192.168.50.20
Windows 10 (als Administrator)

powershell
Kopieren
Bearbeiten
netsh interface ipv4 set address name="Ethernet" static 192.168.50.20 255.255.255.0
ping 192.168.50.10

✅ Fazit
Beide Maschinen konnten nach manueller Konfiguration erfolgreich miteinander kommunizieren. Dieses Szenario demonstriert, wie wichtig ein korrekt eingerichteter virtueller Switch und passende IP-Adressen sind.

