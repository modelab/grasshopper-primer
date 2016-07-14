### 2.1.3. Komponenten

![IMAGE](images/2-1-3/2-1-3_001_Components-Tabs.png)

#### 2.1.3.1 Analyse

![IMAGE](images/2-1-3/2-1-3_002_Analyse-Components.png)
>1. Mesh Closest Point 
2. Mesh Evaluate
3. Mesh Sample Plus

**Element\* Mesh Closest Point**

Abweichend von Grasshopper's **Mesh Closest Point** Komponente, berechnet diese Komponente auch den Normalenvektor und die Farbe der ausgegebenen Punkte und überkommt die Notwendigkeit der **Mesh Eval** Komponente, was den Graphen auf der Leinwand vereinfacht.

**Element\* Mesh Evaluate**

Die grasshoppereigene **Mesh Eval** Komponente benötigt einen Polygonnetzparameter als Eingabe, der von der **Mesh Closest Point** Komponente ausgegeben wird, aber recht schwierig händisch zu erstellen ist. Element's "Closest Point" Komponente ermöglicht die direkte Eingabe des Index einer Netzfläche und ihrer baryzentrischen Koordinaten.

Merke - baryzentrische Koordinaten sind auf eine Art und Weise definiert, dass sie immer zu eins aufaddieren. Wenn die Eingabewerte U, V und W nicht auf eins aufaddieren, wird diese Komponente das Verhältnis der drei Werte beibehalten, während sie normalisiert werden. Zum Beispiel, wenn Du die Eingabewerte 2, 2 und 4 eingibst, wird der Polygonnetzparameter mit {0.25;0.25;0.5} berechnet.

**Element\* Mesh Sample Plus**

Diese Komponente wird benutzt, um schnell Farbinformation aus einem Polygonnetz zu extrahieren. Sie gibt Alpha, Rot, Grün, Blau, Farbton, Sättigung, und Leuchtkraftwerte der eingegebenen Punkte aus. Wenn ein gegebener Punkt nicht auf dem Polygonnetz liegt, wird diese Komponente den naheliegensten Punkt auf dem Polygonnetz berechnen. Diese Komponente nutzt parallele Datenverarbeitung, um die Geschwindigkeit zu erhöhen.


#### 2.1.3.2 Daten

![IMAGE](images/2-1-3/2-1-3_003_Data-Components.png)
>1. Datenvisualisierer
2. Benachbarte Kanten
3. Benachbarte Netzflächen
4. Benachbarte Eckpunkte


**Element\* Data Visualizer**

Diese Komponente wird verwendet, um Halbkantendaten der Netzflächen eines Eingabepolygonnetzes zu visualieren.

**Element\* Edge Neighbors**

Diese Komponente bietet die Möglichkeit Daten zur Nachbarschaft von Kanten eines Eingabepolygonnetzes strukturiert auszugeben. Die Ausgabedaten werden als Baum mit einem Ast für jede Kante in dem Polygonnetz ausgegeben. Sie gibt die Meshkanten, deren Endpunkte und die Mittelpunkte der Netzflächen angrenzend an jeder Kante ("dual graph"), die benachbarten Kanten als Linienobjekte (in Reihe entgegen dem Uhrzeigersinn) und benachbarte Netzflächenmittelpunkte (Mittelpunkte der Netzflächen angrenzend zu den Kantenstart- und endpunkten) aus.

![IMAGE](images/2-1-3/2-1-3_004_Edge-Neighbors.png)
> **Edge Neighbors** - Kanten, Eckpunkte an den Enden, angrenzende Netzflächenmittelpunkte, benachbarte Kanten und benachbarte Netzflächenmittelpunkte

**Element\* Face Neighbors**

Diese Komponente ist ähnlich zu den anderen in diesem Abschnitt, aber die Daten im Baum sind entsprechend der Netzflächen geordnet, mit einem Ast pro Netzfläche. Die Ausgabeparameter sind die Netzflächenmittelpunkte, die Eckpunkte jeder Netzfläche (angeordnet entgegen dem Uhrzeigersinn), benachbarte Kanten (angeordnet entgegen dem Uhrzeigersinn) und die Mittelpunkte der benachbarten Flächen (angeordnet entgegen dem Uhrzeigersinn).

![IMAGE](images/2-1-3/2-1-3_005_Face-Neighbors.png)
> **Face Neighbors** - Netzflächenmittelpunkte, Netzflächeneckpunkte, benachbarte Kanten und benachbarte Netzflächenmittelpunkte

**Element\* Vertex Neighbors**

Diese Komponente gibt die Polygonnetzeckpunkte, benachbarte Eckpunkte (angeordnet entgegen dem Uhrzeigersinn), benachbarte Kanten (angeordnet entgegen dem Uhrzeigersinn) und benachbarte Netzflächenmittelpunkte (angeordnet entgegen dem Uhrzeigersinn) in einem strukturierten Datenbaum entsprechend den Eckpunkten des Polygonnetzes aus.

![IMAGE](images/2-1-3/2-1-3_006_Vertex-Neighbors.png)
> **Vertex Neighbors** - Eckpunkte, benachbarte Eckpunkte, benachbarte Kanten, benachbarte Netzflächenmittelpunkte

#### 2.1.3.3 Primitive Polygonnetzkörper

Element\* stellt vier zusätzliche primitve Polygonnetzkörper zur Verfügung: den Dodekaeder, Tetraeder, Oktaeder und Ikosaeder. Diese Komponente nimmt eine einzelne Zahl als Eingabeparameter für den Radius und produziert ein Polygonnetz mit dem Koordinatenursprung als Zentrum, das aus einer Netzfläche pro Seite besteht. Mit dem zusätzlichen Einsatz des Würfels, der bereits in Grasshopper zur Verfügung steht, macht das fünf platonische Körper. 

![IMAGE](images/2-1-3/2-1-3_007_Primitives.png)
>1. Dodekaeder
2. Tetraeder
3. Oktaeder
4. Ikosaeder

#### 2.1.3.4 Glättung

**Element\* Smooth** stellt einen optimierten Glättungsalgorithmus zur Verfügung, der effizienter arbeitet als Grasshopper's **Smooth Mesh**, wenn er für größere Datensätze eingesetzt wird. Er nutzt den Laplaceschen Glättungsalgorithmus für halbkantenstrukturierte Polygonnetze. Er verändert nicht die Topologie oder die Anzahl der Eckpunkte eines verschweißten Polygonnetzes, wird aber identische Eckpunkte zusammenführen, die aus einem unverschweißten Polygonnetz resultieren. Wir können die Glättungsstärke, Grenzbedingungen, Grenztoleranzen, sowie die Anzahl der Iterationen angeben.

![IMAGE](images/2-1-3/2-1-3_008_Smooth.png)

#### 2.1.3.5 Unterteilung

**Element\* Catmull Clark Subdivision** 

Dies ist eine rekursive Unterteilung basierend auf dem Catmull Clark Algorithmus. Wir können die Anzahl der Iterationen, sowie die Art des Umgangs mit offenen Kanten bestimmen.

**Element\* Constant Quad**

Diese Unterteilungskomponente wird ein Polygonnetz mit ausschließlich viereckigen Netzflächen erzeugen, indem sie eine weitere Netzfläche für jede Kante des Polygonnetzes hinzufügt.

![IMAGE](images/2-1-3/2-1-3_009_Subdivide.png)
>1. Constant Quad Unterteilung
2. Catmull Clark Unterteilung

#### 2.1.3.6 Transformation

![IMAGE](images/2-1-3/2-1-3_010_Transform-Components.png)
>1. Mesh Windown
2. Mesh Frame
3. Mesh Thicken
4. Mesh Offset
5. Mesh Poke Face

Diese Komponenten stellen eine Anzahl von unterschiedlichen Transformationen zur Verfügung, die unten beschrieben werden. Jede Komponente hat die zusätzliche Möglichkeit Distanzdaten pro Eckpunkt anzunehmen, um eine Variation der Transformationsstärke über das Polygonnetz zu erreichen.

**Element\* Mesh Window**

Stellt ein neues Polygonnetz innerhalb der Netzflächen mit einem Versatzwert her. Diese Komponente akzeptiert entweder ein Polygonnetz oder eine Liste von geschlossenen Polylinien als Eingabe.

**Element\* Mesh Frame**

Die Ausgabe ist ein Rahmen um die Netzflächen. Jede resultierende Netzfläche wird ein neues Loch im Zentrum haben. Diese Komponente akzeptiert entweder ein Polygonnetz oder eine Liste von geschlossenen Polylinien als Eingabe.

**Element\* Mesh Thicken**

Diese Komponente wird einem Eingabepolygonnetz Materialstärke entsprechend der Eckpunktnormalen der zur Verfügung gestellten Eingabewerte zuweisen.

**Element\* Mesh Offset**

Diese Komponente erstellt einen Versatz zum ursprünglichen Polygonnetz entsprechend der Eckpunktnormalen.

**Element\* Mesh Poke Face**

Zuerst werden die Netzflächen mit einer "Frame" Operation geteilt und dann die Innenfläche nochmals mittig unterteilt. Für diesen Teil der Netzfläche kann ein Wert angegeben werden, der die innenliegenden Netzflächen entlang der Flächennormalen verschiebt. Zum Beispiel wird ein vierseitiges Polygon ("Quad") in vier dreiseitige Polygone, mit einem gemeinsamen Eckpunkt in deren Mitte, unterteilt. Der Höheneingabeparameter erlaubt es, den Eckpunkt entsprechend zu transformieren.

![IMAGE](images/2-1-3/2-1-3_011_Transform.png)
>1. Mesh Window
2. Mesh Frame
3. Ikosaeder nach der aufeinanderfolgenden Anwendung der "Mesh Frame", "Mesh Thicken" und Polygonnetzteilung Komponenten.

#### 2.1.3.7 Dienstprogramme

![IMAGE](images/2-1-3/2-1-3_012_Utility-Component.png)
>1. Mesh Combine & Clean
2. Mesh Edges
3. Mesh Status

**Element\* Mesh Combine and Clean** 

Diese Komponente verbindet verschiedene Polygonnetze mit den zusätzlichen Optionen, das Polygonnetz basierend auf einem Winkel zu verschweißen oder identische Eckpunkte zu verbinden. Diese Komponente stellt ebenso mögliche topologische Probleme fest und gibt diese als Anmerkungen und Warnungen mit detaillierten Beschreibungen aus. Im Fall, dass die Zusammenführung von identischen Eckpunkten eine schlechte Topologie erzeugt, wird die Komponente die unveränderten Eingabepolygonnetze ausgeben, anstatt sie zusammenzuführen. Der Nutzer kann auch angeben, das Polygonnetz zusammenzuführen ohne die Eckpunkte zu verändern.

**Element\* Mesh Edges** 

Diese Komponente gibt die offenen Kanten, Kanten, Netzflächenpolylinien und für unverschweißte Polygonnetze die unverschweißten Polygonnetzkanten aus.

**Element\* Mesh Status** 

Diese Komponente gibt Polygonnetzinformationen basierend auf der Topologie aus. Es gibt zwei verschiedene Modi, in denen wir die Informationen ansehen können. Die erste ist die Ausgabe von Daten zur Geometrie, wie Polygonnetzvalidität, Anzahl der Eckpunkte, Anzahl der Netzflächen und Anzahl der Normalen. Die andere ist die Ausgabe des Polygonnetzstatus, welcher den Zustand des Polygonnetzes beschreibt, ob es nicht-mannigfaltige Kanten, degenerierte Netzflächen, die Anzahl der offenen Kanten oder die Anzahl unverbundener Netzflächen ist. Diese Komponente operiert nicht auf einem Polygonnetz, es gibt lediglich Informationen für den Nutzer aus. Es gibt auch eine Option für die Kombination identischer Eckpunkte, wodurch der Nutzer den Effekt dieser Option auf die entsprechenden Daten beobachten kann.