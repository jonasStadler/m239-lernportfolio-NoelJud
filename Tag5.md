# Tag 5

## Was haben wir gemacht?
Am Anfang haben wir allfällige Fragen zu Docker oder Docker-Compose beantwortet. Dann haben wir zum Thema SSL und TLS recherchiert und einige Leitfrage dazu beantwortet. Dann haben wir angefangen mit SSL zu arbeiten, dazu musste zuerst ein Key erstellt werden. Nachdem der Key mit der Konsole erstellt wurde, kann das Zertifikat erstellt werden. In der Regel müsste dann eine CA-Anfrage erstellt werden, in unserem Szenario kann das aber ausgelassen werden. Zur Konfiguration muss anschliessend die Datei **/etc/apache2/ports.conf** um einige Zeilen erweitert werden. Zuletzt muss dann die Webseite gecodet werden. Dann haben wir Proxys angeschaut. Wir haben dann besprochen was der Unterschied zwischen Forward und Reverse Proxies. Dann haben wir behandelt wozu Proxies eingesetzt werden und was die Vor- und Nachteile sind. Wir haben dabei die Themen Anonymisierung, Schutz und Verschlüsselung, Load-Balancing, Caching und Kompression bearbeitet. Dann haben wir unds ein Beispiel eins Proxys und eines Load-Balancings angeschaut. Dann haben wir ein Kapitel im Skript gelesen. Zum Schluss haben wir die Übung "Übung: Proxies und SSL" gelöst.

## Wie haben wir das gemacht?
Die Fragenrunde am Anfang der Lektion hat im Plenum stattgefunden. Wir haben selbstständing zu TLS und SSL recherchiert und die Leitfragen dann wieder im Plenum besprochen. Wir haben dann den SSL-Key und das SSL-Zertifikat in selbstständiger Arbeit erstellt. Wir haben dann in der Klasse besprochen was die verschiedenen Proxys sind. Auch die Theorie hinter den verschiedenen Eigenschaften der Proxies war in Zusammenarbeit. Wir haben den darauffolgenden Leseauftrag selbstständig durchgeführt. Zum Schluss wurde in Einzelarbeit an der Hausaufgabe gearbeitet.

## Habe ich noch offene Fragen? Was muss ich noch tun?
Ich bin mir noch Unsicher was die Unterschiede von SSL und TLS sind und welches welchen Vorteil gegenüber dem anderen bringt, oder wann welches zu bevorzugen ist.

## Dokumentation der Lernziele

### Jeder Lernende kann die Funktion "Reverse Proxy" in eigenen Worten erklären
Der Reverse-Proxy kontrolliert den Zugang im Internet. Der Reverse Proxy schützt den Webserver vor verschiedenen Einflüssen, deshalb wird er als zusätzliche Sicherheitskomponente vor einen oder mehrere Webserver geschaltet um Anfragen aus dem Internet entgegen zu nehmen und an den Backend-Server weiterzuleiten.

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

### Jeder Lernende kann mittels OpenSSL eigene, selbstsignierte Zertifikate generieren

### Jeder Lernende kann die Funktion "Reverse Proxy" in eigenen Worten erklären

### Jeder Lernende kann einen Apache2 Webserver in einen Reverse Proxy überführen

### Jeder Lernende kann einen Apache2 Webserver in einen Loadbalancer überführen

### Jeder Lernende kann Reverse Proxies für eigene Services einsetzen und entsprechend konfigurieren

### Jeder Lernende kann einen Reverse-Proxy mittels Apache installieren und konfigurieren

### Jeder Lernende kann einen Webserver (und damit auch einen Reverse Proxy) mittels SSL schützen

### Jeder Lernende kann einen Webserver als Load-Balancer ensetzen
