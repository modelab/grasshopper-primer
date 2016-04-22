### 1.2.5. DIE GRASSHOPPERDEFINITION
{% if gitbook.generator == "pdf" or "mobi" or "epub" %}
>Beispieldateien zu diesem Abschnitt: [http://grasshopperprimer.com/appendix/A-2/1_gh-files.html](http://grasshopperprimer.com/appendix/A-2/1_gh-files.html)
{% else %}
>Beispieldateien zu diesem Abschnitt: [Download](../../appendix/A-2/gh-files/1.2.5_the grasshopper definition.gh)
{% endif %}

#####Grasshopperdefinitionen haben einen Programmfluss, der darstellt, an welcher Stelle das Programm die Ausfuehrung beginnt, was in der Mitte passiert und wie man sehen kann, dass die Ausfuehrung abgeschlossen ist.

####1.2.5.1. PROGRAMMFLUSS
Visuelle Grasshopperprogramme werden von links nach rechts ausgefuehrt. Das Lesen des Graphen in Abhaengigkeit von den verkabelten Verbindungen von stromaufwaerts nach stromabwaerts ermoeglicht das Verstaendnis des Programmflusses.

![IMAGE](images/1-2-5/1-2-5_001-program-flow.png)
>Richtung des Datenflusses von links nach rechts.

####1.2.5.2. DER LOGISCHE PFAD
Alle Objekte und Kabel, welche Objekte verbinden stellen den logischen Graphen unseres Programmes dar. Dieser Graph offenbart den Datenfluss, die Abhaengigkeiten eines jeden Eingabeparameters von dem mit ihm verbundenen Ausgabeparameter. Zu jeder Zeit, an der sich unser Graph veraendert, sozusagen "verunreinigt" wird, wird jede Komponente flussabwaerts und jede Verbindung in dieser Richtung aktualisiert.

![IMAGE](images/1-2-5/1-2-5_002-logical-graph.png)
>1. Reparametrisiere die Domaene einer Kurve auf die Werte von 0.0 bis 1.0.
2. Referenziere eine Kurve von Rhino.
3. Teile eine Kurve in 13 gleiche Teile.
4. Sende die Parameterwerte eines jeden Teilpunktes der Kurventeilung durch den Graphmapper.
5. Multipliziere jeden Wert mit 27. 
6. Zeichne einen Kreis and jedem Teilpunkt entlang der Kurve normal zum Tangentialvektor an jedem Punkt, mit dem Radius definiert durch den Parameterwert (t), der durch den Graphmapper und die Multiplikation mit 27 modifiziert wurde.
7. Lofte eine Flaeche zwischen den Kreisen.

![IMAGE](images/1-2-5/1-2-5_003-lofted-variable-circles.png)
>1. Variabler Kreisradius.
2. Loft zwischen Kreisen.
