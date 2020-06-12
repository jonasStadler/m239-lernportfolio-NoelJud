# Tag 5

## Was haben wir gemacht?
Am Anfang haben wir allfällige Fragen zu Docker oder Docker-Compose beantwortet. Dann haben wir zum Thema SSL und TLS recherchiert und einige Leitfrage dazu beantwortet. Dann haben wir angefangen mit SSL zu arbeiten, dazu musste zuerst ein Key erstellt werden. Nachdem der Key mit der Konsole erstellt wurde, kann das Zertifikat erstellt werden. In der Regel müsste dann eine CA-Anfrage erstellt werden, in unserem Szenario kann das aber ausgelassen werden. Zur Konfiguration muss anschliessend die Datei **/etc/apache2/ports.conf** um einige Zeilen erweitert werden. Zuletzt muss dann die Webseite gecodet werden. Dann haben wir Proxys angeschaut. Wir haben dann besprochen was der Unterschied zwischen Forward und Reverse Proxies. Dann haben wir behandelt wozu Proxies eingesetzt werden und was die Vor- und Nachteile sind. Wir haben dabei die Themen Anonymisierung, Schutz und Verschlüsselung, Load-Balancing, Caching und Kompression bearbeitet. Dann haben wir unds ein Beispiel eins Proxys und eines Load-Balancings angeschaut. Dann haben wir ein Kapitel im Skript gelesen. Zum Schluss haben wir die Übung "Übung: Proxies und SSL" gelöst.

## Wie haben wir das gemacht?
Die Fragenrunde am Anfang der Lektion hat im Plenum stattgefunden. Wir haben selbstständing zu TLS und SSL recherchiert und die Leitfragen dann wieder im Plenum besprochen. Wir haben dann den SSL-Key und das SSL-Zertifikat in selbstständiger Arbeit erstellt. Wir haben dann in der Klasse besprochen was die verschiedenen Proxys sind. Auch die Theorie hinter den verschiedenen Eigenschaften der Proxies war in Zusammenarbeit. Wir haben den darauffolgenden Leseauftrag selbstständig durchgeführt. Zum Schluss wurde in Einzelarbeit an der Hausaufgabe gearbeitet.

## Habe ich noch offene Fragen? Was muss ich noch tun?
Ich bin mir noch Unsicher was die Unterschiede von SSL und TLS sind und welches welchen Vorteil gegenüber dem anderen bringt, oder wann welches zu bevorzugen ist.

## Dokumentation der Lernziele

### Jeder Lernende kann die Funktion "Reverse Proxy" in eigenen Worten erklären
Der Reverse-Proxy kontrolliert den Zugang im Internet. Der Reverse Proxy schützt den Webserver vor verschiedenen Einflüssen, deshalb wird er als zusätzliche Sicherheitskomponente vor einen oder mehrere Webserver geschaltet um Anfragen aus dem Internet entgegen zu nehmen und an den Backend-Server weiterzuleiten. Im Gegensatz zu einem Forward Proxy schützt der Reverse-Proxy nicht den Client vor Einflüssen aus dem Internet, sondern den Webserver vor Zugriffen von einem Client.

### Jeder Lernende kann einen Apache2 Webserver in einen Reverse Proxy überführen
Zuerst müssen die benötigten Apache-Proxy-Module installiert werden. Wir brauchen in unserem Fall das Modul **mod_proxy**. Es gibt viele verschiedene Zusatzodule die Verschiedene funktionen haben.
* **mod_proxy_http** beinhaltet alle Proxy-Funktionen für HTTP und HTTPS-Anfragen. Das Zusatzmodul unterstützt die Protokollversionen HTTP/0.9, HTTP/1.0 und HTTP/1.1.
* **mod_proxy_ftp** wird benötigt, um Proxy-Funktionen für FTP-Anfragen zur Verfügung zu stellen.
* **mod_proxy_connect** hält Proxy-Funktionen für ein SSL-Tunneling bereit.
* **mod_proxy_ajp** implementiert das Apache-JServ-Protocol (AJP). Dieses wird im Rahmen des Load-Balancings genutzt, um Anfragen an Applikationsserver im Hintergrund weiterzuleiten.
* **mod_cache, mod_disk_cache und mod_mem_cache** implementieren Caching-Funktionen, die es ermöglichen, Inhalte auf dem Apache-Server zwischenzuspeichern.
* **mod_proxy_html** ermöglicht ein Rewriting von HTML-Links.
* **mod_headers** ermöglicht die Manipulation von HTTP-Kopfdaten.
* **mod_deflate** implementiert eine Kompressionsfunktion.

Die benötigten Zusatzmodule müssen nach dem Download des Moduls noch aktiviert werden. In unserem Fall müssen dann die Zusatzmodule proxy und proxy_http aktiviert werden. Danach muss der HTTP-Server neugestartet werden.

### Jeder Lernende kann Reverse Proxies für eigene Services einsetzen und entsprechend konfigurieren
Nach der Installation muss der Reverse-Proxy konfiguriert werden. Dazu sollte die Datei **/etc/apache2/sites-enabled/000-default.conf** deaktiviert werden und eine eigene Virtual-Host-Datei erstellt werden. In dieser müssen dann die vorgeschriebenen Konfigurationen festgelegt werden.

### Jeder Lernende kann die Verwendung von SSL im Umfeld von Internet Servern in eigenen Worten erklären
SSL ist ein Protokoll zur Sicherung der Datenübertragung im Internet. Nach der Version 3.0 wurde es in TLS umbenannt. TLS wird meistens mit HTTPS genutzt um Wevserver zu schützen. TLS kann aber auch für andere Protokolle wie zum Beispiel POP3 oder SMTP genutzt werden. TLS ist auch die Funktion die Internetseiten im Browser als sicher oder unsicher erkennt.

### Jeder Lernende kann mittels OpenSSL eigene, selbstsignierte Zertifikate generieren
Um ein Zertifikat generieren zu können muss zuerst ein Privater Schlüssel vorhanden sein. Dieser kann mit folgendem Befehl generiert werden:
```bash
openssl genra -out /etc/ssl/private/apache.key 2048
```
Nachdem der Private Key erstellt wurde kann das SSL-Zertifikat generiert werden. Dazu wird folgender Befehl genutzt:
```bash
openssl req -new -x590 -key /etc/ssl/private/apache.key -days 365 -sha256 -out /etc/ssl/certs/apache.crt
```

### Jeder Lernende kann die Funktion "Reverse Proxy" in eigenen Worten erklären
Proxy-Server sind Kommunikationsschnittstellen in einem Netzwerk, die Anfragen entgegen nehmen und zum Zielrechner weiterleiten. Im Gegensatz zu einem Forward Proxy schützt der Reverse-Proxy nicht den Client vor Einflüssen aus dem Internet, sondern den Webserver vor Zugriffen von einem Client.

### Jeder Lernende kann einen Apache2 Webserver in einen Loadbalancer überführen
Um den Loadbalancer nutzen zu können muss zuerst das Modul heruntergeladen werden. Das kann mit folgendem Befehl gemacht werden:
```bash
a2enmod proxy_balancer lbmethod_byrequests slotmen_shm
```
Ebenfalls wird mit dem Befehl das Modul **lbmethod_byrequest** installiert. Anschliessend kann mit der Konfiguration begonnen werden. Die Konfiguration kann anhand eines Beispiels im Sktipt corgenommen werden.

### Jeder Lernende kann einen Reverse-Proxy mittels Apache insallieren und konfigurieren
Zuerst müssen die benötigten Apache-Proxy-Module installiert werden. Wir brauchen in unserem Fall das Modul **mod_proxy**. Es gibt viele verschiedene Zusatzodule die Verschiedene funktionen haben. Die benötigten Zusatzmodule müssen nach dem Download des Moduls noch aktiviert werden. In unserem Fall müssen dann die Zusatzmodule proxy und proxy_http aktiviert werden. Danach muss der HTTP-Server neugestartet werden.

### Jeder Lernende kann einen Webserver (und damit auch einen Reverse Proxy) mittels SSL schützen
Zuerst muss OpenSSL mit folgendem Befehl installiert werden:
```bash
sudo apt-get install openssl
```
Danach muss folgendermassen ein Private Key erstellt werden:
```bash
openssl genra -out /etc/ssl/private/apache.key 2048
```

Anschliessend muss mit folgendem Befehl ein Zertifikat erstellt werden:
```bash
openssl req -new -x590 -key /etc/ssl/private/apache.key -days 365 -sha256 -out /etc/ssl/certs/apache.crt
```

Zuletzt muss konfiguriert werden dass der Apache auf den Port 443 hört.

### Jeder Lernende kann einen Webserver als Load-Balancer einsetzten
Um den Loadbalancer nutzen zu können muss zuerst das Modul heruntergeladen werden. 
Ebenfalls wird mit dem Befehl das Modul **lbmethod_byrequest** installiert. Anschliessend kann mit der Konfiguration begonnen werden. Die Konfiguration kann anhand eines Beispiels im Sktipt corgenommen werden. Folgendermassen sieht eine Konfiguration aus:
```bash
<Proxy balancer://mycluster>

  # Server 1
  BalancerMember http://0.0.0:8080/
  
  # Server 2
  BalancerMember http://0.0.0.0:8081/
  
 </Proxy>
 
 <VirtualHost *:*>
 
  ProxyPass / balancer://mycluster
 </VirtualHost>
```
