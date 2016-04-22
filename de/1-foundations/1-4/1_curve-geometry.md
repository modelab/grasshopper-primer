### 1.4.1. KURVENGEOMETRIEN

#####NURBS (non-uniform rational B-splines) sind mathematische Repraesentationen, die akurat jede Form, von einer 2D Linie, einem Kreis, Boden oder einer Kiste, bis hin zur komplexesten, organischen 3D Freiformflaeche darstellen koennen. Sie koennen in jedem Prozess von Illustration und Animation bis zur Herstellung verwendet werden, da NURBS Modelle flexibel und akurat sind.

Da Kurven geometrische Objekte sind, besitzen sie eine Anzahl von Eigenschaften und Charakteristika, die genutzt werden koennen um sie zu beschreiben oder zu analysieren. Zum Beispiel hat jede Kurve eine Startkoordinate und eine Endkoordinate. Wenn die Distanz zwischen den beiden Koordinaten null ergibt, ist die Kurve geschlossen. Ebenso hat jede Kurve eine Anzahl an Kontrollpunkten. Wenn all diese Punkte in der selben Ebene angeordnet sind, ist die gesamte Kurve planar. Einige Eigenschaften beziehen sich auf die Kurve als Ganzes, waehrend andere sich nur auf bestimmte Punkte auf der Kurve beziehen. Beispielsweise ist die Ebenheit eine globale Eigenschaft, waehrend Tangentenvekroren eine lokale Eigenschaft sind. Einige Eigenschaften sind auch nur auf bestimmte Kurventypen anzuwenden. So weit habrn wir einigen von Grasshopper's primtiven Kurvenkomponenten besprochen: Linien, Kreise, Ellipsen und Boegen.

![IMAGE](images/1-4-1/1-4-1_001-curve-types.png)
>1. Linie
2. Polylinie
3. Kreis
4. Ellipse
5. Bogen
6. NURBS Kurve
7. Polykurve

![IMAGE](images/1-4-1/1-4-1_002-bezier-curve.png)
>1. Endpunkt
2. Bearbeitungspunkt
3. Kontrollpunkt

####1.4.1.1. NURBS KURVEN
**Degree:** Der Grad ist eine positive ganze Zahl. Diese Zahl ist ueblicherweise 1, 2, 3 oder 5, kann aber jede positive ganze Zahl annehmen. Der Grad einer Kurve legt die Reichweite des Einflusses der Kontrollpunkte auf die Kurve fest; wobei je hoeher der Grad, desto groesser der Einflussbereich. NURBS Linien und Polylinien haben den Grad 2, und die meisten Freiformkurven haben den Grad 3 oder 5.

**Control Points:** Die Kontrollpunkte sind eine Liste von mindestens Grad+1 Punkten. Einer der eingachsten Wege die Form einer NURBS Kurve zu veraendern ist es die Kontrollpunkte zu bewegen.

**Weight:** Kontrollpunkte haben eine mit ihnen assoziierte Nummer, Gewicht genannt. Geweichte sind ueblicherweise positive Zahlen. Wenn alle Kontrollpunkte einer Kurve das gleiche Gewicht (normalerweise 1) haben, ist die Kurve nicht-rational, sonst ist die Kurve rational. Die meisten NURBS Kurven sind nichr-rational. Wenige NURBS Kurven, wie Kreise und Ellipsen sind immer rational.

**Knots:** Knoten sind eine Liste von (degree+N-1) Zahlen, wobei N die Anzahl der Kontrollpunkte darstellt.

**Edit Points:** Punkte auf einer Kurve werden nach ihrem Knotendurchschnitt ausgewertet. Bearbeitungspunkte sind wie Kontrollpunkte, ausser dass sie sich immer auf der Kurve befinden und die Veraenderung der Lage eines Bearbeitungspunkte generell die Form der gesamten Kurve veraendert (das Bewegen eines Kontrollpunktes kann die Form der Kurve nur lokal beeinflussen). Bearbeitungspunkte sind nuetzlich, wenn es darum geht einen Punkt im Inneren einer Kurve genau durch eine bestimmte Position zu legen.

NURBS Kurvenknoten sind das Resultat von sich aendernden Graden:

![IMAGE](images/1-4-1/1-4-1_003-degree-one.png)
>A D<sup>1</sup> NURBS  Kurven verhalten sich wie Polylinien. Eine D<sup>1</sup> Kurve hat einen Knoten fuer jeden Bearbeitungspunkt.

![IMAGE](images/1-4-1/1-4-1_004-degree-two.png)
>D<sup>2</sup> NURBS Kurven sind typischerweise nur selten angewandt um Boegen und Kreise anzunaehern. Die Splinekurve schneidet das Kontrollpolygon auf der Haelfte eines jeden Segmentents.

![IMAGE](images/1-4-1/1-4-1_005-degree-three.png)
>D<sup>3</sup> ist die haeufigste NURBS Kurve und ist der Standard in Rhino. Du bist wahrscheinlich mit der visuellen Progression eines Splines vertraut, auch wenn die Knoten in seltsamen Orten zu liegen scheinen.

####1.4.1.2. GRASSHOPPER SPLINE KOMPONENTEN
{% if gitbook.generator == "pdf" or "mobi" or "epub" %}
>Beispieldateien zu diesem Abschnitt: [http://grasshopperprimer.com/appendix/A-2/1_gh-files.html](http://grasshopperprimer.com/appendix/A-2/1_gh-files.html)
{% else %}
>Beispieldateien zu diesem Abschnitt: [Download](../../appendix/A-2/gh-files/1.4.1.2_grasshopper spline components.gh)
{% endif %}

Grasshopper hat eine Menge Werkzeuge um Rhino's fortgeschrittene Kurventypen wie NURBS Kurven und Polylinien auszudruecken. Diese Werkzeuge koennen unter dem "Curve/Splines" Reiter gefunden werden.

**Nurbs Curve** (Curve/Spline/Nurbs curve): Die NURBS Komponente konstruiert NURBS Kurven von Kontrollpunkten. Der V Eingabeparameter definiert diese Punkte, welche implizit durch die Auswahl von Punkten in der Rhinoszene oder durch die Eingabe volatiler Daten von anderen Komponente beschrieben werden koennnen. Der D Eingabeparameter der NURBS Komponents legt den Grad der Kurve fest.

![IMAGE](images/1-4-1/1-4-1_006-nurbs-curve.png)

**Interpolate Curve** (Curve/Spline/Interpolate): Interpolierung von Kurven verhaelt sich etwas unterschiedlich zu NURBS Kurven. Der V Eingabeparameter der Komponente ist aehnlich zu dem der NURBS Komponente, das heisst er fordert eine bestimmte Menge von Punkten um eine Kurve zu bestimmen. Jedoch wird die resultierende Kurve bei der interpolierten Kurve genau durch diese Punkte hindurchfuehren, egal welchen Grad die Kurve aufweist. Wie bei der NURBS Kurve beschreibt der D Eingabeparameter der Komponente den Grad der erzeugten Kurve. In diesem Fall werden jedochnur ungerade Werte fuer den Grad angenommen. Der P Eingabeparameter bestimmt wieder, ob die Kurve periodisch ist. Du wirst beginnen ein Muster in den Ausgabeparametern fuer viele der Kurvenkomponenten zu erkennen, wie z.B. dass C, L und D Ausgabeparameter generell die resultierende Kurve bestimmen, deren Laenge und die Domaene der Kurve.

![IMAGE](images/1-4-1/1-4-1_007-interpolate-curve.png)

**Kinky Curve** (Curve/Spline/Kinky Curve): Die "Kinky curve" Komponente erlaubt es den spezifischen Winkelschwellenwert A festzulegen, der bestimmt, wann die Kurve von einer abgehackten Kurve zu einer glatten, interpolierten Kurve uebergeht. Es soll hier angemerkt werden, dass der A Eingabeparameter im Bogenmass angegeben werden muss.

![IMAGE](images/1-4-1/1-4-1_008-kinky-curve.png)

**Polyline** (Curve/Spline/Polyline): Eine Polylinien ist eine Sammlung von Liniensegmenten, die zwei oder mehrere Punkte verbinden, deren resultierende Linie immer durch ihre Kontrollpunkte verlaeuft; aehnlich wie bei der interpolierten Kurve. Wie die oben genannten Kurventypen, gibt der V Eingabeparameter der Polylinien Komponente eine Menge an Punkten vor, welche die Grenzen eines jeden Liniensegmentes bestimmen, aus dem die Polylinie besteht. Der C Eingabeparameter der Komponente definiert ob oder ob nicht die Polylinie geschlossen oder offen ist. Wenn der erste Punkt nicht die selbe Lage har wie der letzte Punkt, wird ein Liniensegment eingefuegt um die Kurve zu schliessen. ie Ausgabe der Polylinienkomponente ist unterschiedlich von den anderen, da der einzige uebergebene Parameter die Kurve selbst ist.

![IMAGE](images/1-4-1/1-4-1_009-polyline.png)
