###1.3.1. Punkte, Ebenen & Vektoren

#####Alles beginnt mit Punkten. Ein Punkt ist nicht mehr als ein oder mehrere Werte, die Koordinaten genannt werden. Die Anzahl der Koordinatenwerte korrespondieren mit der Anzahl der Dimensionen des Raums in welchem sie dargestellt werden. Punkte, Ebenen und Vektoren sind die Basis der Erstellung und Transformation von Geometrie in Grasshopper.

![Points, Vectors, and Planes](images/1-3-1/1-3-1_001-intro.png)

####1.3.1.1 PUNKTE
Punkte im dreidimensionalen Raum haben drei Koordinaten, normalerweise bezeichnet als [x,y,z]. Punkte in einem zweidimensionalen Raum haben nur zwei Koordinaten, die entweder [x,y] oder [u,v] genannt werden, abhaengig davon, von welcher Art zweidimensionalem Raum wir sprechen.
2D Parameterraum ist an eine begrenzte Flaeche gebunden. Er ist immer noch kontionuierlich und kann hypothetisch gesprochen immer noch unendlich viele Punkte auf der Flaeche darstellen, aber die maximale Distanz zwischen beliebigen Punkten dieser Menege ist begrenzt. 2D Parameterkoordinaten sind nur gueltig, wenn sie eine bestimmte Spanne nicht uebersteigen. In der Beispielzeichnung, wurde diese Spanne zwischen 0.0 und 1.0 fuer die Richtungen [u] und [v] definiert, aber sue koennte jede beliebige begrenzte Domaene annehmen. Ein Punkt mit den Koordinaten [1.5, 0.6] wuerde irgendwo ausserhalb der Flaeche liegen und ist deshalb ungueltig.

Since the surface which defines this particular parameter space resides in regular 3D world space, we can always translate a parametric coordinate into a 3D world coordinate. The point [0.2, 0.5] on the surface for example is the same as point [1.8, 2.0, 4.1] in world coordinates. Once we transform or deform the surface, the 3D coordinates which correspond with [0.2, 0.5] will change.

![Points](images/1-3-1/1-3-1_002-points.png)

Wenn es schwer ist, dieses Konzept zu verstehen, kannst Du Dir eventuell damit behelfen, Dir Deine eigene Position im Raum vorzustellen. Wir neigen dazy unsere lokalen Koordinatensysteme zu benutzen um zu beschreiben, wo wir uns befinden; "Ich sitze im dritten Sitz in der siebten Reihe des Kinos", "Ich bin auf dem Ruecksitz". Wenn das Auto in dem Du Dich befindest auf der Strasse unterwegs ist, veraendern sich Deine globalen Koordinaten staendig, auch wenn Du Dich immer noch auf der selben Ruecksitz-"Koordinate" befindest.

####1.3.1.2. VEKTOREN
Ein Vektor ist eine geometrische Groesse, die Richtung und Staerke beschreibt. Vektoren sind abstrakt; das heisst, dass sie eine Groesse beschreiben und nicht ein geometrisches Element.

Vektoren sind von Punkten nicht zu unterscheiden. Das bedeutet, dass die beiden Listen von je drei Zahlen sich so wenig unterscheiden, dass man nicht mit Sicherheit sagen kann, ob sie Punkte oder Vektoren darstellt. Es gibt jedoch einen praktischen Unterschiedd; Punkte sind absolut, Vektoren sind relativ. Wenn wir eine Liste von drei Dezimalzahlen als einen Punkt behandeln, stellt sie eine bestimmte Koordinate dar im Raum dar. Wenn wir sie als Vektor behandeln, stellt sie eine bestimmt Richtung dar. Ein Vektor ist ein Pfeil in einem Raum, der immer vom Weltursprung (0.0, 0.0, 0.0) beginnt und an einer bestimmten Koordinate endet.

![Vectors](images/1-3-1/1-3-1_003-vectors.png)

####1.3.1.3. EBENEN
Ebenen sind "flach"und dehnen sich unendlich in zwei Dimensionen aus, waehrend sie ein lokales Koordinatensystem definieren. Ebenen sind keine expliziten Objekte in Rhino, da sie lediglich dazu verwendet werden um Koordinatensysteme im 3D Weltraum zu bestimmen. Faktisch ist es am Besten sich die Ebenen als Vektoren vorzustellen, da sie lediglich mathematische Konstrukte sind.

![Planes](images/1-3-1/1-3-1_004-planes.png)
