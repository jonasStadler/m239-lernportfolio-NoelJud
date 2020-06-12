# Tag 4

## Was haben wir gemacht?
Angefangen haben wir mit einer Repetition von einem Docker-Compose-File. Wir haben besprochen was das gezeigte Docker-Compose-File macht und wozu es gebraucht wird. Anschliessend haben wir die Hausaufgabe, ein Docker-Projekt auf GitHub zu suchen, besprochen. Als nächstes haben wir angefangen einen LAMP-Stack aufzubauen. Dazu musste zuerst ein Verzeichnis mit einer vorgegebenen YAML-Datei erstellt werden. Dann musste eine Port-Weiterleitung erstellt werden und eine Kommunikation zwischen Containern ermöglicht werden. In den nächsten Schritten müssen Verzeichnisse im Projekt erstellt werden und diese dann jeweils in einen Container gemounten. Die zuvor erstellten Verzeichnisse müssen noch konfiguriert werden, dazu muss in allen Verzeichnissen ein Konfigurationsfile erstellt werden. Zum Schluss musste noch für jeden Container ein Dockerfile nach Vorlage erstellt werden. Als letzter Schritt muss für die Infrastruktur noch ein Test HTML- und PHP-File erstellt werden.

## Wie haben wir das gemacht?
Gestartet haben wir mit der Repetition des Docker-Compose-Files, dieses haben wir zusammen in der Klasse analysiert. Ebenfalls die Hausaufgabe, ein Docker-Projekt auf GitHub zu finden wurde im Plenum besprochen. Dann haben wir damit begonnen den LAMP-Stack aufzubauen. Bei diesen Übungen haben wir immer jeweils zwei Schritte in Einzelarbeit durchgeführt und dann allfälige Fragen im Plenum besprochen. So konnte vermieden werden dass man den Anschluss verliert.

## Habe ich noch offene Fragen? Was muss ich noch tun?
Ich hatte keine Probleme bei der praktischen Umsetzung, jedoch weiss ich nicht genau was ein LAMP-Stack ist, oder was dessen Funktion ist, dessen Umsetzung mit Docker-Compose funktionierte aber problemlos.

## Dokumentation der Lernziele

### Jeder Lernende kennt die Optionen Ports, Volumes, Images, Builds, Networks und kann sie in eigenen Worten beschreiben
Mit der Option Ports kann bestummen werden auf welchen Ports der Docker-Container gehostet werden soll. Ein Volume ist eine Art Ordner der Ausserhalb des Containers lebt, es ist auf dem Host gemountet und kann mit den Daten des Containers interagieren. Ein Docker Image ist ein File das genutzt wird um den Code eines Docker-Containers aufzuführen. Die Build-Option wird genutzt um einen automatisierten Build zu generieren, die verschiedene Command-Lines auszuführen. Mit der Networks-Option kan die Kommunikation zwischen Containern ermöglicht werden ohne spezifische Ports festlegen zu müssen.
 
### Jeder Lernende kann einfache Docker-Compose-Projekte nach Anleitung zusammen stellen
  

### Jeder Lernende kann bestehende Docker-Compose-Projekte interpretieren und beschreiben     

### Jeder Lernende kann die Docker-Compose-Befehle anwenden um Projekte zu starten/stoppen
