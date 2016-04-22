###2.1.2. Halbkanten Daten

Im Grasshopper primer, haben wir uns angesehen wie ein Polygonnetz in Grasshopper mit der Netzflaechen-Eckpunkte-Datenstruktur beschrieben werden kann. Diese ist eine relativ einfache Datenstruktur und wird fuer viele Polygonnetzapplikationen genutzt, kann aber bei komplexeren Algorithmen recht ineffizient werden. Die Element\* Erweiterung restrukturiert Polygonnetze mit der Halbkanten Datenstruktur, eine kantenfokusierte Datenstruktur, die effiziente Aufrufe von benachbarten Eckpunkten, Netzflaechen und Kanten ermoeglicht, was die Geschwindigkeit und Performance von Algorithmen stark erhoehen kann. Diese Struktur kann [...] Informationen ueber Eckpunkte, Netzflaechen und Kanten erhalten. Diese Methode ermoeglicht die Generierung von neuen Mustern und Geometrien, komplett basiered auf der topologischen Nachbarschaft der Basisgeometrie.

Die Halbkantendatenstruktur ist eine Repraesentation eines Polygonnetzes in dem jede Kante in zwei Halbkanten unterteilt ist, die in entgegengesetzte Richtungen zeigen. Dies erlaubt expliziten und impliziten Zugang zu Daten von einem Polygonnetzelement zu benachbarten Elementen.

![IMAGE](images/2-1-2/2-1-2_001_Half-Edge.png)

####2.1.2.1 Halbkantenkonnektivitaet
Die in blau hervorgehobenen Halbkanten speichern Indizes mit Informationen ueber die jeweiligen Endpunkte, benachbarte Halbkanten und den zugehoerigen Netzflaechen. Die anderen Informationen (in grau dargestellt) sind implizit zugaenglich.
![IMAGE](images/2-1-2/2-1-2_002_Half-Edge.png)
####2.1.2.2 Eckpunktkonnektivitaet
Die in blau hervorgehobenen Eckpunkte speichern einen Index zu den jeweiligen ausgehenden Halbkanten. Die anderen Informationen (in grau dargestellt) sind implizit zugaenglich.
![IMAGE](images/2-1-2/2-1-2_003_Half-Edge.png)


