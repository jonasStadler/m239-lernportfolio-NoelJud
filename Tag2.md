# Tag2

## Was haben wir gemacht?
Nach dem Organisatorischen Anfangsteil haben wir einige Repetitionsfragen durchgearbeitet. Anschliessend haben wir den Auftrag erhalten zu Recherchieren wie wir verschiedene kleine Docker Aufträge durchführen können. Dann haben wir alle Aufgaben im Skriptkapitel "Docker: Einführung in die SystemLevel-Virtualisierung" durchgearbeitet. Sobald wir damit fertig waren haben wir die Übungen des Kapitels "Docker und PHP" durchgeführt. Zum Schluss haben wir Docker-Compose auf unsere Virtuellen Maschine gemäss einer beigelegten Anleitung installiert.

## Wie haben wir das gemacht?
Die Repetitionsfragen haben wir zusammen in der Klasse besprochen. Die Recherche für die Aufträge und die Durchführung der Aufträge wurden in Einzelarbeit durchgeführt. Das Skriptkapitel "Docker: Einführung in die SystemLevel-Virtualisierung" wurde in Einzelarbeit mithilfe des Skriptes gelöst. Ebenfalls das Kapitel "Docker und PHP" wurde in Einzelarbeit mihilfe der Anleitungen im Skript gelöst. Für die Installation von Docker-Compose wurde in Einzelarbeit eine Online-Anleitung gemacht.

## Habe ich noch offene Fragen? Was muss ich noch tun?
Ich bin mir noch unsicher welche Gründe es gibt Docker, einer Virtuellen Maschine zu bevorzugen und warum wir Docker auf einer Virtuellen Maschine nutzen.

## Dokumentation der Lernziele

### Jeder Lernende kann den Vergleich zwischen Virtuellen Maschinen und Containern in eigenen Worten formulieren
Der Unterschied zwischen Docker und Virtuellen Maschinen ist dass Docker lediglich ein Teil des Betriebssystems reserviert, den sogenanten User Space. Container sind im Prinzip nur Softwareprozesse, die komplett isoliert vom Rest des Systems laufen. Docker zielt expliziet nur auf den Betrieb von Anwendungen ab. Virtuelle Maschinen hingegebn basieren nicht auf einem Containersystem. Sie bestehen ebenfalls teilweise aus dem User Space aber auch aus dem Kernel Space vom Betriebssystem. Jede Virtuelle Maschine verfügt jeweils über ein eigenes Betriebssystem und Anwendungen.

### Jeder Lernende kann Docker-Images anzeigen
Wenn Docker gestartet ist können die bereits heruntergeladenen Docker-Images aufgelistet werden. Wenn dann der Befehl "docker images" eingegeben wird, werden alle heruntergeladenen images aufgelistet.

### Jeder Lernende kann laufende Docker-Container anzeigen
Um alle Docker-Container mit dem Status "running" aufzulisten, kann in der Linux-Konsole der Befehl "docker ps" eingegeben werden. Mit einem "-a" hinter dem Befehl kann man auch die deaktivierten anzeigen.

### Jeder Lernende kann einfache, vorbereitete Docker-Container laufen lassen
Um einen Docker-Container starten zu können muss zuerst "docker ps -a" eingegen werden um die Docker-Container ID zu sehen. Dann kann mit docker start ID der Docker-Container gestartet werden.
