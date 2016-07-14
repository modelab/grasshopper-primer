### 1.2.5. DIE GRASSHOPPERDEFINITION
{% if gitbook.generator == "pdf" or "mobi" or "epub" %}
>Beispieldateien zu diesem Abschnitt: [http://grasshopperprimer.com/appendix/A-2/1_gh-files.html](http://grasshopperprimer.com/appendix/A-2/1_gh-files.html)
{% else %}
>Beispieldateien zu diesem Abschnitt: [Download](../../appendix/A-2/gh-files/1.2.5_the grasshopper definition.gh)
{% endif %}

##### Grasshopper Definitionen haben einen Programmfluss, der darstellt, an welcher Stelle das Programm die Ausführung beginnt, was in der Mitte passiert und wie man sehen kann, dass die Ausführung abgeschlossen ist.

#### 1.2.5.1. PROGRAMMFLUSS
Visuelle Grasshopperprogramme werden von links nach rechts ausgeführt. Das Lesen des Graphen in Abhängigkeit von den verkabelten Verbindungen von stromaufwärts nach stromabwärts ermöglicht das Verständnis des Programmflusses.

![IMAGE](images/1-2-5/1-2-5_001-program-flow.png)
>Richtung des Datenflusses von links nach rechts.

#### 1.2.5.2. DER LOGISCHE PFAD
Alle Objekte und Kabel, welche Objekte verbinden, stellen den logischen Graphen unseres Programmes dar. Dieser Graph offenbart den Datenfluss, die Abhängigkeiten eines jeden Eingabeparameters von dem mit ihm verbundenen Ausgabeparameter. Zu jeder Zeit, an der sich unser Graph verändert, sozusagen "verunreinigt" wird, wird jede Komponente flussabwärts und jede Verbindung in dieser Richtung aktualisiert.

![IMAGE](images/1-2-5/1-2-5_002-logical-graph.png)
>1. Reparametrisiere die Domäne einer Kurve auf die Werte von 0.0 bis 1.0.
2. Referenziere eine Kurve von Rhino.
3. Teile eine Kurve in 13 gleiche Teile.
4. Sende die Parameterwerte eines jeden Teilpunktes der Kurventeilung durch den Graphmapper.
5. Multipliziere jeden Wert mit 27. 
6. Zeichne einen Kreis an jedem Teilpunkt entlang der Kurve normal zum Tangentialvektor an jedem Punkt, mit dem Radius definiert durch den Parameterwert (t), der durch den Graphmapper und die Multiplikation mit 27 modifiziert wurde.
7. Lofte eine Fläche zwischen den Kreisen.

![IMAGE](images/1-2-5/1-2-5_003-lofted-variable-circles.png)
>1. Variabler Kreisradius.
2. Loft zwischen Kreisen.
