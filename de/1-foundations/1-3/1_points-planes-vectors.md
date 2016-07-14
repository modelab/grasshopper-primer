###1.3.1. Punkte, Ebenen & Vektoren

#####Alles beginnt mit Punkten. Ein Punkt ist nicht mehr als ein oder mehrere Werte, die Koordinaten genannt werden. Die Anzahl der Koordinatenwerte korrespondieren mit der Anzahl der Dimensionen des Raums in welchem sie dargestellt werden. Punkte, Ebenen und Vektoren sind die Basis der Erstellung und Transformation von Geometrie in Grasshopper.

![Points, Vectors, and Planes](images/1-3-1/1-3-1_001-intro.png)

####1.3.1.1 PUNKTE
Punkte im dreidimensionalen Raum haben drei Koordinaten, normalerweise bezeichnet als [x,y,z]. Punkte in einem zweidimensionalen Raum haben nur zwei Koordinaten, die entweder [x,y] oder [u,v] genannt werden, abhängig davon, von welcher Art zweidimensionalem Raum wir sprechen.
2D Parameterraum ist an eine begrenzte Fläche gebunden. Er ist immer noch kontinuierlich und kann hypothetisch gesprochen immer noch unendlich viele Punkte auf der Fläche darstellen, aber die maximale Distanz zwischen beliebigen Punkten dieser Menge ist begrenzt. 2D Parameterkoordinaten sind nur gültig, wenn sie eine bestimmte Spanne nicht übersteigen. In der Beispielzeichnung wurde diese Spanne zwischen 0.0 und 1.0 für die Richtungen [u] und [v] definiert, aber sie könnte jede beliebige begrenzte Domäne annehmen. Ein Punkt mit den Koordinaten [1.5, 0.6] würde irgendwo außerhalb der Fläche liegen und ist deshalb ungültig.

Da die Fläche, welche diese bestimmten Parameter definiert, sich im regulären 3D Raum befindet, können wir immer die parametrischen Werte in 3D Weltkoordinaten übersetzen. Der Punkt [0.2, 0.5] auf der Fläche zum Beispiel ist derselbe Punkt wie [1.8, 2.0, 4.1] in Weltkoordinaten. Sobald wir die Fläche verändern, werden sich die 3D Koordinaten des entsprechenden Punktes and den Parameterkoordinaten [0.2, 0.5] ebenfalls verändern.

![Points](images/1-3-1/1-3-1_002-points.png)

Wenn es schwer ist, dieses Konzept zu verstehen, kannst Du Dir eventuell damit behelfen, Dir Deine eigene Position im Raum vorzustellen. Wir neigen dazu unsere lokalen Koordinatensysteme zu benutzen, um zu beschreiben, wo wir uns befinden; "Ich sitze im dritten Sitz in der siebten Reihe des Kinos", "Ich bin auf dem Rücksitz". Wenn das Auto, in dem Du Dich befindest, auf der Straße unterwegs ist, verändern sich Deine globalen Koordinaten ständig, auch wenn Du Dich immer noch auf der selben Rücksitz-"Koordinate" befindest.

####1.3.1.2. VEKTOREN
Ein Vektor ist eine geometrische Größe, die Richtung und Stärke beschreibt. Vektoren sind abstrakt; das heißt, dass sie eine Größe beschreiben und nicht ein geometrisches Element.

Vektoren sind von Punkten nicht zu unterscheiden. Das bedeutet, dass die beiden Listen von je drei Zahlen sich so wenig unterscheiden, dass man nicht mit Sicherheit sagen kann, ob sie Punkte oder Vektoren darstellen. Es gibt jedoch einen praktischen Unterschied; Punkte sind absolut, Vektoren sind relativ. Wenn wir eine Liste von drei Dezimalzahlen als einen Punkt behandeln, stellt sie eine bestimmte Koordinate im Raum dar. Wenn wir sie als Vektor behandeln, stellt sie eine bestimmt Richtung dar. Ein Vektor ist ein Pfeil in einem Raum, der immer vom Weltursprung (0.0, 0.0, 0.0) beginnt und an einer bestimmten Koordinate endet.

![Vectors](images/1-3-1/1-3-1_003-vectors.png)

####1.3.1.3. EBENEN
Ebenen sind "flach" und dehnen sich unendlich in zwei Dimensionen aus, während sie ein lokales Koordinatensystem definieren. Ebenen sind keine expliziten Objekte in Rhino, da sie lediglich dazu verwendet werden, um Koordinatensysteme im 3D Weltraum zu bestimmen. Faktisch ist es am besten sich die Ebenen als Vektoren vorzustellen, da sie lediglich mathematische Konstrukte sind.

![Planes](images/1-3-1/1-3-1_004-planes.png)
