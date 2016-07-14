### 2.1.2. Halbkanten Daten

Im Grasshopper Primer haben wir uns angesehen, wie ein Polygonnetz in Grasshopper mit der Netzflächen-Eckpunkte-Datenstruktur beschrieben werden kann. Diese ist eine relativ einfache Datenstruktur und wird für viele Polygonnetzapplikationen genutzt, kann aber bei komplexeren Algorithmen recht ineffizient werden. Die Element\* Erweiterung restrukturiert Polygonnetze mit der Halbkanten Datenstruktur, eine kantenfokusierte Datenstruktur, die effiziente Aufrufe von benachbarten Eckpunkten, Netzflächen und Kanten ermöglicht, was die Geschwindigkeit und Performance von Algorithmen stark erhöhen kann. Diese Struktur kann [...] Informationen über Eckpunkte, Netzflächen und Kanten erhalten. Diese Methode ermöglicht die Generierung von neuen Mustern und Geometrien, komplett basiered auf der topologischen Nachbarschaft der Basisgeometrie.

Die Halbkantendatenstruktur ist eine Repräsentation eines Polygonnetzes, in dem jede Kante in zwei Halbkanten unterteilt ist, die in entgegengesetzte Richtungen zeigen. Dies erlaubt expliziten und impliziten Zugang zu Daten von einem Polygonnetzelement zu benachbarten Elementen.

![IMAGE](images/2-1-2/2-1-2_001_Half-Edge.png)

#### 2.1.2.1 Halbkantenkonnektivität
Die in blau hervorgehobenen Halbkanten speichern Indizes mit Informationen über die jeweiligen Endpunkte, benachbarte Halbkanten und den zugehörigen Netzflächen. Die anderen Informationen (in grau dargestellt) sind implizit zugänglich.
![IMAGE](images/2-1-2/2-1-2_002_Half-Edge.png)
#### 2.1.2.2 Eckpunktkonnektivität
Die in blau hervorgehobenen Eckpunkte speichern einen Index zu den jeweiligen ausgehenden Halbkanten. Die anderen Informationen (in grau dargestellt) sind implizit zugänglich.
![IMAGE](images/2-1-2/2-1-2_003_Half-Edge.png)


