### 1.6.5 Wechselwirkungen zwischen Polygonnetzen

##### Dieser Abschnitt betrachtet Wege, wie Polygonnetzobjekte miteinander in Wechselwirkung treten können, wie beispielsweise die Auswertung des nahegelegensten Punktes oder die Kombination mehrerer Polygonnetze miteinander.

#### 1.6.5.1 Polygonnetze und Punkte


**Inclusion**

![IMAGE](images/1-6-5/inclusion.png)

Diese Komponente testet ob ein bestimmter Punkt innerhalb eines Polygonnetzkörpers liegt oder nicht. Dies funktioniert nur mit geschlossenen Polygonnetzen.

**Mesh Closest Point**


![IMAGE](images/1-6-5/mesh-closest-point.png)

Diese Komponente berechnet die Position auf dem Polygonnetz, welche einem angegebenen Punkt am nächsten liegt. Diese Komponente gibt drei verschiedene Daten aus: die Koordinaten des berechneten Punktes auf dem Polygonnetz, die Indizes der Netzfläche, die den Punkt enthält und die Polygonnetzparameter. Diese Parameter sind sehr wichtig in Verbindung mit der **Mesh Eval** Komponente, die unterhalb behandelt wird.

![IMAGE](images/1-6-5/01_mesh-closest-point.png)
>1. Wir wollen, basiered auf einem gegebenen Punkt im Raum, den nahegelegensten Punkt auf einem Polygonnetz finden
2. Die Netzfläche, welche den nahegelegensten Punkt enthält, wird bestimmt
3. Die Parameter des nahegelegensten Punktes auf der Fläche werden berechnet

Nutzer, die sich detaillierter mit der Parametrisierung beschäftigen wollen, können sich die Struktur der Polygonnetzparameter genauer ansehen. Du kannst sehen, wenn Du ein Paneel an den entsprechenden Ausgabeparameter der **Mesh Closest Point** Komponente anschliesst. Der Polygonnetzparameter hat die folgende Struktur: N[A,B,C,D]. Die erste Zahl, N, ist der Index der Netzfläche, welche den berechneten Punkt enthält. 

Die folgenden vier Zahlen definieren die *baryzentrischen* Koordinaten des Punktes innerhalb der Netzfläche. Die Koordinaten des referenzierten Punktes können gefunden werden, indem jeder Eckpunkt des Polygonnetzes mit diesen Zahlen multipliziert wird und die Ergebnisse addiert (Natürlich wird das schon für uns erledigt und wir können den Punktausgabeparameter nutzen). Merke Dir, dass baryzentrische Koordinaten" nur für dreieckige Netzflächen eindeutig sind, was bedeutet, dass für eine viereckige Netzfläche ein bestimmter Punkt mehrere Parametrisierungen aufweisen kann. Grasshopper vermeidet dieses Problem, indem es viereckige Netzflächen intern trianguliert, wenn es die Netzparameter berechnet, was dazu führt, dass von den vier Zahlen des Netzparameters immer mindestens einer 0 ist.

![IMAGE](images/1-6-5/02_barycentric.png)
>Baryzentrische Koordinaten

**Mesh Eval**

![IMAGE](images/1-6-5/mesh-eval.png)

Die **Mesh Eval** Komponente nutzt einen Netzparameter als Eingabeparameter und gibt den referenzierten Punkt, seine Normale und Farbe aus. Die Farbe und Normale werden als Interpolation der Eckpunktfarben und -normalen berechnet, indem dieselben baryzentrischen Koordinaten wie im Netzparameter benutzt werden.

#### 1.6.5.2 Kombination von Polygonnetzgeometrien 

**Mesh Join**

![IMAGE](images/1-6-5/mesh-join.png)

Abweichend von der Verbindung von NURBS Kurven und Oberflächen, die Berührungspunkte benötigen, können beliebige Polygonnetze miteinander verbunden werden - auch wenn die Polygonnetze sich nicht berühren. Es ist keine Voraussetzung, dass die Netzflächen miteinander verbunden sind (obwohl in den meisten Anwendungen ein solches Polygonnetz nicht erstrebenswert ist !!!)

Diese Komponente verschweißt nicht die Eckpunkte und oft ist es sinnvoll sie mit der **Weld** Komponente zu kombinieren.

**Mesh Boolean**

Polygonnetze in Grasshopper haben eine Anzahl von boolschen Operationen, ähnlich der boolschen Operationen für NURBS Körper. Boolsche Operationen sind abhängig von der Eingabereihenfolge, was bedeutet, dass, wenn wir die Reihenfolge der Eingabepolygonnetze zwischen A und B umkehren, verschiedene Ergebnisse erzielt werden.

![IMAGE](images/1-6-5/03_boolean.png)
>1. Mesh Difference
2. Mesh Intersection
3. Mesh Split
4. Mesh Union


#### 1.6.5.3 Verschneidung und Verschattung 

**Intersect**

Verschneidungen können zwischen Polygonnetzen und anderen Objekten berechnet werden: Strahlen, Ebenen, Kurven und andere Polygonnetze

![IMAGE](images/1-6-5/04_mesh-intersection.png)
>1. Mesh | Ray
2. Mesh | Plane
3. Mesh | Curve
4. Mesh | Mesh

**Occlusion**

![IMAGE](images/1-6-5/occlusion.png)

Wie wir schon besprochen haben, ist eine der vielen Anwendungen von Polygonnetzgeometrien die Visualisierung und die Erstellung von Renderings basiered auf Flächennormalen. Wenn wir rendern ist es auch wichtig zu wissen, ob ein Objekt im Schatten hinter einem anderen Objekt liegt. Die **Occlusion** Komponente in Grasshopper erlaubt es uns, einen Satz von Punkten als Stichprobe, das verschattende Polygonnetz und einen *Sichtstrahl* (einen Vektor, der die Lichtrichtung definiert) einzugeben.

Solch ein Prozess kann verwendet werden, um Schatten in Renderings zu erzeugen oder um zu bestimmen ob Objekte von einem bestimmten Kamerawinkel aus verdeckt werden.

![IMAGE](images/1-6-5/05_mesh-occlusion.png)
>1. Sichtstrahl, um auf Verschattung zu testen
2. Verschattendes Polygonnetz
3. 'Getroffene' Stichprobenpunkte
4. 'Verschattete' Stichprobenpunkte
