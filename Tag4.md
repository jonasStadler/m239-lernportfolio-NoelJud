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
 
### Jeder Lernende kann einfache Docker-Compose-Projekte nach Anleitung zusammenstellen
Um ein Docker-Compose-Projekt zu erstellen muss zuerst ein Ordner für das Projekt erstellt werden. In dem Ordner muss dann ein YAML-File erstellt werden in dem dann die benötigten Dienste festgelegt werden. Dann muss eine Portweiterleitung definiert werden und eine Kommunikation zwischen den Containern ermöglicht werden. Anschliessend muss ein bestimmtes Verzeichnissystem im Projekt angelegt werden. Die zuvor angelegten Verzeichnisse müssen dann in lokale Ordner gemountet werden. Die Container apache und mysql müssen dann mit vorgegebenen Dateien konfiguriert werden. Als nächster Schritt muss für jeden Container ein Dockerfile erstellt werden. Zuletzt muss dann die Umgebung realisiert werden.

### Jeder Lernende kann bestehende Docker-Compose-Projekte interpretieren und beschreiben     
```yaml
# Zuerst wird die Version gekennzeichnet
version: '3'

#Die Services "api" und "db" werden definiert
services:
 api:
  build: .
  # Der Pfad des Images für diesen Service wird festgelegt
  image: tunix/docker-compose-demo
  # Der Port des Services wird auf 8080 festgelegt
  ports:
   - "8080"
   # Es wird auf den DB-Service verwiesen
  links:
   - db:demodb
  command: ["/source/wait-for-it.sh","demodb:3306","--","java","-jar",
# Der DB-Service wird definiert
db:
 # Verweis auf das Image des Service
 image: mysql
 # Die Datenbankstruktur wir definiert
 environment:
  - MYSQL_ALLOW_EMPTY_PASSWORD=true
  - MYSQL_DATABASE=demo
  - MYSQL_USER=user
  - MYSQL_PASSWORD=test
```

### Jeder Lernende kann die Docker-Compose-Befehle anwenden um Projekte zu starten/stoppen
Um alle Docker-Container eines Docker-Compose-Projektes zu starten muss der Befehl "sudo docker-compose up -d". Wenn man alle Docker-Container wieder stoppen will muss man den Befehl "sudo docker-compose stop" eingeben.
