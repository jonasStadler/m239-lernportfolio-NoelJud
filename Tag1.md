# Tag 1

## Was haben wir gemacht?
Zuerst haben wir uns ein Ablaufplan einer Web-Applikation angeschaut und uns überlegt was gemacht werden muss dass eine solche Umsetzung funktionieren kann. Danach haben wir ein Video geschaut, in dem erklärt wurde was Docker ist und wofür es genutzt wird. Es wurde erklärt was für Dienste und Software auf einem Docker-Container betrieben werden kann. Es wurde erklärt was die Unterschiede zu einer Virtuellen Umgebung sind. Das nächste Thema des Videos war es wie die Sicherheit von Docker-Images gewährleistet wird. Zudem wurde erklärt wie Docker-Images selbstständig aktualisiert werden können. Als nächstes haben wir Docker auf einer unserer Ubuntu VMs installiert. Danach haben wir einige Sachen mit Docker gemacht wie zum Beispiel ein Docker-Image herunterladen, ein Docker-Container ausführen oder auch alle aktive Docker-Container auflisten. Zum Schluss haben wir dann einige Kapitel im Skript gelesen und einige Fragen dazu beantwortet.

## Wie haben wir das gemacht?
Wir haben den Ablaufplan der Web-Applikation in der Klasse besprochen und auch miteinander überlegt und beantwortet ob eine solche Umsetzung funktionieren kann. Wir haben dann in Einzelarbeit das Video geschaut und allfällige Fragen notiert. Die notierten Fragen haben wir dann im Plenum besprochen. Um Docker auf der VM zu installieren haben wir in Einzelarbeit eine Online-Anleitung durchgearbeitet. Auch die einfachen Funktionen von Docker die wir getestet haben, waren in Einzelarbeit, mit der Anleitung zu lösen. Die Kapitel im Skript haben wir in Einzelarbeit gelesen und unsere Antworten dann in der Klasse besprochen.

## Habe ich noch offene Fragen? Was muss ich noch tun?
Bei den Fragen die am Schluss der Lektion besprochen wurden stand "Was ist der Docker-HUB?". Diese Frage ist mir auch nach dem Besprechen noch nicht 100% klar. Zu diesem Thema muss ich nochmal selbstständig recherchieren. Zudem hatte ich teilweise etwas probleme mit den Aufträgen in der Anleitung ich konnte dort nicht alles direkt korrekt ausführen wie es in der Anleitung dargestellt war. Nach mehrmaligem Versuchen war es dann allerdings erfolgreich.

## Dokumentaion der Lernziele

### Jeder Lernende kann den Vergleich zwischen Virtuellen Maschinen und Containern in eigenen Worten formulieren
Der Unterschied ist das Docker eine Container basierte Technologie ist. Docker brauch lediglich den User Space des Betriebssystems. Virtuelle Maschinen hingegen basieren nicht auf einem Containersystem. Virtuelle Maschinen basieren auf dem User Space mit Kernel Space auf einem Betriebssystem. Jede Virtuelle Maschine teilt sich seine Hardwareressourcen mit seinem Host. 

### Jeder Lernende kann Docker-Images anzeigen
Um alle Docker-Images anzuzeigen muss zuerst ein Terminal gestartet werden und darauf dann Docker ausführen. Dann kann der Befehl "docker ps -a" eingegeben werden. Mit diesem Befehl werden alle Docker-Images, egal ob aktiv oder inaktiv angezeigt. Mit dem Befehl "docker ps -1" kann das zuletzt erstellte Docker-Image angezeigt werden.

### Jeder Lernende kann laufende Docker-Container anzeigen
Wenn man nur die aktiven Docker-Container anzeigen möchte, kann das mit dem Befehl "docker ps" gemacht werden.

### Jeder Lernende kann einfache, vorbereitete Docker-Container laufen lassen
Wenn man einen Docker-Container starten will muss man dazu die ID des Docker-Containers kennen. Dazu listet man am besten alle Docker-Container mit "docker ps -a" auf. Dort steht dann ganz links jeweils die ID des aufgelisteten Containers. Der Docker-Container kann dann mit dem Befehlt "docker start ID" gestartet werden also zum Beispiel "docker start d9b100f2f636".
