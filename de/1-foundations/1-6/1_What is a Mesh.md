### 1.6.1 Was ist ein Polygonnetz?

##### Ein Polygonnetz ist eine Sammlung von Vierecken und Dreiecken, die eine Fläche oder einen Körper darstellen. Dieser Anschnitt beschreibt die Struktur von Polygonnetzobjekten, welche aus Eckpunkten, Kanten und Netzflächen, sowie zusätzlichen Polygonnetzeigenschaften, wie Farben und Normalen, bestehen.

![IMAGE](images/1-6-1/01_mesh-structure.png)
>1. Polygonnetzeckpunkte (Eckpunkte)
2. Polygonnetzkanten (Kanten)
3. Polygonnetzflächen (Netzflächen)

#### 1.6.1.1 Grundsätzliche Anatomie von Polygonnetzen

Grasshopper definiert Polygonnetze mit einer Netzflächen-Eckpunkte Datenstruktur. Auf der einfachsten Ebene ist diese Struktur eine Ansammlung von Punkten, die in Polygonen gruppiert sind. Die Punkte des Polygonnetzes nennen wir *Eckpunkte (Vertices)*, während die Polygone *Netzflächen (faces)* genannt werden. Um ein Polygonnetz zu erstellen, benötigen wir eine Liste von Eckpunkten und ein System, um diese in "Netzflächen" zu gruppieren.

![IMAGE](images/1-6-1/02_basic-anatomy.png)
>1. Eine Liste von Eckpunkten ("Vertices")
2. Netzflächen ("Faces") als Gruppierung von Eckpunkten

**Vertices**

Die Eckpunkte eines Polygonnetzes sind einfach eine Liste von Punkten. Erinnere Dich daran, dass eine Liste in Grasshopper eine Sammlung von Objekten darstellt. Jedes Objekt in der Liste hat einen *index*, der die Position von Objekten in einer Liste beschreibt. Der Index von Eckpunkten ist sehr wichtig wenn ein Polygonnetz konstruiert wird oder wenn Informationen über die Struktur des Polygonnetzes benötigt werden.

![IMAGE](images/1-6-1/03_vertices.png)
>1. Eine Liste von Punkten. Alle Listen in Grasshopper beginnen mit einem Index von 0
2. Die Menge an Punkten mit ihrem entsprechenden Index benannt

**Faces**

Eine Netzfläche ist eine geordnete Liste von drei oder vier Eckpunkten. Die Flächendarstellung einer Netzfläche ist deshalb durch die Position der Eckpunkte beschrieben. Wir haben bereits eine Liste von Eckpunkten, die ein Polygonnetz bestimmen, also werden wir einfach die Indices der Eckpunkte heranziehen, anstatt einzelne Punkte zur Beschreibung der Netzflächen bereitzustellen. Dies ermöglicht es uns dieselben Eckpunkte in mehreren Netzflächen zu nutzen.

![IMAGE](images/1-6-1/04_faces.png)
>1. Eine viereckige Netzfläche bestehend aus Indices 0, 1, 2, und 3
2. Eine dreieckige Netzfläche bestehend aus Indices 1, 4, und 2

In Grasshopper werden Netzflächen entweder mit **Mesh Triangle** oder mit **Mesh Quad** Komponenten erzeugt. Der Eingabeparameter für diese Komponenten besteht aus Integerlisten, die den Indices der Eckpunkten entsprechen, die wir für unsere Netzfläche nutzen wollen. Indem wir ein **Panel** mit dem Ausgabeparameter dieser Komponente verbinden, können wir sehen, dass dreieckige Netzflächen als T{A;B;C} beschrieben werden und viereckige Netzflächen als Q{A;B;C;D}. Netzflächen mit mehr als vier Seiten sind nicht zulässig. Um ein fünfseitiges Polygonnetzelement herzustellen, muss das Polygonnetz in zwei oder mehr Netzflächen zerlegt werden.

![IMAGE](images/1-6-1/05_construct-faces.png)
>1. **Mesh Quad** Komponente mit Indices 0, 1, 2, und 3
2. **Mesh Triangle** Komponente mit Indices 1, 4, und 2

Es ist wichtig sich daran zu erinnern, dass diese Komponenten nicht zur Erzeugung einer Polygonnetzgeometrie führen, sondern der Ausgabeparameter eine Liste von Indices liefert, die definieren, wie ein Polygonnetz erzeugt werden soll. Indem wir dem Format dieser Liste Beachtung schenken, können wir auch manuell Netzflächen editieren, indem wir eine **Panel** Komponente nutzen, um ein korrektes Format für entweder eine dreieckige oder eine viereckige Netzfläche anzugeben.

![IMAGE](images/1-6-1/06_faces-with-panel.png)
>1. Eine Netzfläche, die mit einer **Mesh Quad** Komponente erzeugt wird
2. Ein Netzfläche, die mit einem **Panel** erzeugt wird
3. Ein Paneel Eigenschaftenfenster wird automatisch geöffnet, wenn ein Paneel doppelgeklickt wird oder nach einem Rechtsklick "Edit Notes..." gewählt wird

So weit haben wir eine Liste mit Eckpunkten und ein Set Netzflächendefinitionen, aber noch kein Polygonnetz erzeugt. Damit ein Polygonnetz erzeugt wird, müssen wir die Netzflächen und Eckpunkte miteinander durch eine **Construct Mesh** Komponente verbinden. Wir verbinden unsere Liste mit Eckpunkten mit dem V Eingabeparameter, und eine verschmolzene Liste der Netzflächen mit dem F Eingabeparameter (Die Komponente hat auch einen optionalen Farbeingabeparameter, den wir unten noch behandeln werden.). Wenn wir ein Paneel mit dem Ausgabeparameter der **Construct Mesh** Komponente verbinden, werden wir die Informationen zu der Anzahl der Netzflächen und Eckpunkte erhalten.

![IMAGE](images/1-6-1/07_construct-mesh.png)
>1. Die **Construct Mesh** Komponente nimmt eine Liste von Eckpunkten und Netzflächen als Eingabeparameter. Der Farbeingabeparameter ist optional und bleibt im Moment ungenutzt.
2. Ein Paneel zeigt, dass wir ein Polygonnetz mit 5 Eckpunkten und 2 Netzflächen erzeugt haben
3. Das resultierende Polygonnetz (die Eckpunkte wurden mit ihren Indizes benannt)

Als Standard zeigt Grasshopper die Kanten von Polygonnetzgeometrien in der Vorschau nicht an. Um die Kanten in der Vorschau zu sehen, kannst Du die Polygonnetzkantenvorschau mit dem Tastaturkürzel Strg+M oder im Ansichtsmenü die Option 'Preview Mesh Edges' auswählen.

![IMAGE](images/1-6-1/08_preview-mesh-edges.png)

Es ist extrem wichtig, der Ordnung der Indices Aufmerksamkeit zu schenken, wenn Du eine Netzfläche erstellst. Die Netzfläche wird hergestellt, indem die Eckpunkte in der angegebenen Abfolge verbunden werden. Bei viereckigen Netzflächen sind Q{0,1,2,3} und Q{1,0,2,3} sehr verschieden, auch wenn sie beide aus denselben Eckpunkten bestehen. Eine falsche Eckpunktenreihenfolge kann zu Problemen wie Löchern im Polygonnetz oder nicht-mannigfaltigen Polygonnetzgeometrien oder nicht-orientierbaren Flächen führen. Solche Polygonnetzgeometrien werden üblicherweise nicht korrekt gerendert und sind nicht möglich 3D gedruckt zu werden. Diese Schwierigkeiten werden im Abschnitt **Understanding Topology** tiefer behandelt.

![IMAGE](images/1-6-1/08_bowtie.png)
>1. Eine viereckige Netzfläche mit den Indices 0,1,2,3
2. Eine viereckige Netzfläche mit den Indices 0,3,1,2

#### 1.6.1.2 Implizite Polygonnetz Daten

Zusätzlich zu Netzflächen und Eckpunkten gibt es andere Informationen über Polygonnetze, die wir benutzen werden. In Netzfläche-Eckpunkt-basierten Polygonnetzen werden Daten wie *edges* und *normals* basierend auf Netzflächen und Eckpunkten implizit kalkuliert. Dieser Abschnitt beschreibt, wie wir diese Informationen erheben.

**Edges**

Die *edges* eines Polygonnetzes sind Linien, die zwei aufeinanderfolgende Eckpunkte einer Netzfläche miteinander verbinden. Merke, dass einige Kanten zwischen mehreren Netzflächen geteilt werden, während andere Kanten nur an eine Netzfläche angrenzen. Die Anzahl an Netzflächen, die an eine Kante angrenzen, wird *Valenz* der Kante genannt.

Grasshopper gruppiert Kanten basierend auf ihrer Valenz in drei Kategorien:

1. E1 - 'Naked Edges' haben eine Valenz von 1. Sie bestimmen die äußeren Grenzen des Polygonnetzes.
2. E2 - 'Interior Edges' haben eine Valenz von 2. 
3. E3 - 'Non-Manifold Edges' haben eine Valenz von 3 oder größer. Polygonnetze, die solche Strukturen enthalten, werden "Non-Manifold" genannt und im nächsten Abschnitt besprochen.

![IMAGE](images/1-6-1/09_edge-valence.png)
>1. "Naked edge" mit einer Valenz von 1
2. "Interior edge" mit einer Valenz von 2
3. "Non-manifold edge" mit einer Valenz von 3

Wir können die **Mesh Edges** Komponente nutzen, um die Kanten eines Polygonnetzes entsprechend ihrer Valenz auszugeben. Dies ermöglicht es, Kanten entlang der Polygonnetzgrenze oder nicht-mannigfaltige Kanten zu identifizieren. Manchmal jedoch ist es nützlicher, die gesamte Grenze jeder Netzfläche zu erhalten. Dazu nutzen wir die **Face Boundaries** Komponente. Diese wird die Grenze einer jeden Netzfläche als Polylinie ausgeben.

![IMAGE](images/1-6-1/10_edge-component.png)
>1. Die **Mesh Edges** Komponente gibt drei Sets von Kanten aus. Dieses Polygonnetz hat 5 "naked edges", 1 "interior edge" und keine "non-manifold edges"
2. Der E3 Ausgabeparameter ist leer, da dieses Polygonnetz keine nicht-mannigfaltigen Kanten hat.
3. Die **Face Boundaries** Komponente gibt eine Polylinie für jede Netzfläche aus

**Face Normals**

Ein *Normalenvektor* ist ein Vektor mit einer Magnitude von eins und ist rechtwinklig zu einer Fläche angeordnet. Im Fall einer dreieckigen Netzfläche wissen wir, dass alle drei Punkte auf einer ebenen Fläche liegen, sodass die Normale immer rechtwinklig zu dieser Ebene liegen. Woher wissen wir nun, in welche Richtung der Normalenvektor deutet ("hoch" oder "runter")? Wieder einmal ist die Reihenfolge der Indices ausschlaggebend. Polygonnetzflächen werden in Grasshopper gegen den Uhrzeigersinn definiert, sodass eine Netzfläche mit Eckpunkten {0,1,2} sich umgekehrt zu einer mit Eckpunkten {1,0,2} verhält. Ein anderer Weg, um die Richtung zu visualisieren ist die *Rechtehandregel*. 

![IMAGE](images/1-6-1/11_face-normals.png)
>1. Die **Face Normals** Komponente wird eine Liste von Zentren und Normalenvektoren für jede Netzfläche ausgeben
2. Netzflächennormalen entsprechend zur Abfolge von Eckpunkten
3. "Rechtehandregel" zur Bestimmung der Normalenrichtung

Grasshopper erlaubt auch viereckige Netzflächen in Polygonnetzen, in welchem Fall die vier Punkte nicht auf einer ebenen Fläche liegen. Für diese Netzflächen wird das Zentrum aus dem Mittelwert der Koordinaten der vier Eckpunkte gebildet (im Fall einer nicht-ebenen viereckigen Netzfläche liegt dieser Punkt nicht notwendigerweise auf dem Polygonnetz). Um die Normale einer vierseitigen Netzfläche zu berechnen, müssen wir diese zuerst triangulieren, indem wir sie in zwei Dreiecke teilen. Die Normale der viereckigen Gesamtoberfläche ist dann der Mittelwert der beiden Normalenvektoren, gewichtet nach der Fläche der beiden Dreiecke.

**Eckpunktnormalen**

Zusätzlich zu den Netzflächennormalen ist es auch eine Möglichkeit die Normalen für jeden Eckpunkt des Polygonnetzes zu berechnen. Für einen Eckpunkt, der nur in einer einzigen Netzfläche genutzt wird, ist die Normale klar definiert. Wenn der Eckpunkt an mehrere Netzflächen grenzt, ist die Normale an diesem Eckpunkt der Mittelwert der beiden Netzflächennormalen. 

Während die Eckpunktnormalen weniger intuitiv berechnet werden, sind sie doch wichtig für die geglättete Darstellung von Polygonnetzen. Du hast vielleicht sogar festgestellt, dass, auch wenn ein Polygonnetz aus ebenen Netzflächen aufgebaut ist, es trotzdem glatt und gerundet wirken kann, wenn es in Rhino schattiert wurde. Diese geglättete Darstellung wird durch die Eckpunktnormalen ermöglicht.

![IMAGE](images/1-6-1/12_vertex-normals.png)
>1. Normalen entsprechend der Netzflächennormalen ergeben eine diskrete, polygonale Schattierung
2. Angrenzende Netzflächennormale werden gegeneinander ausgemittelt, um Eckpunktnormalen zu erzeugen, was zu einer geglätteten Schattierung entlang der Oberflächen führt.

#### 1.6.1.3 Polygonnetzeigenschaften

Polygonnetze können andere Eigenschaften mit den Eckpunkten oder Netzflächen verknüpft haben. Die einfachste dieser Eigenschaften ist die Eckpunktfarbe, welche unterhalb beschrieben wird, aber auch andere Eigenschaften existieren, wie UV Koordinaten von Texturen (Manche Programme erlauben auch Eckpunktnormalen als Eigenschaften, anstatt wie in unserem Fall abgeleitet von Oberflächen oder Eckpunkten, welche dann noch größere Flexibilität in der Erscheinung der gerenderten Fläche erlauben).

**Farbe**

Wenn Du eine **Construct Mesh** Komponente verwendest, gibt es einen optionalen Eingabeparameter für die Eckpunktfarbe. Farben können auch einem bestehenden Polygonnetz mit der **Mesh Color** Komponente zugewiesen werden. Ein einzelner Farbton kann so das gesamte Polygonnetz einfärben.

![IMAGE](images/1-6-1/13_single-colors.png)
>Dreieckige Polygonnetzobjekte mit rot, grün und blau eingefärbt

Während die oben aufgeführten Beispiele das gesamte Polygonnetz einfärbten, werden die Farbdaten eigentlich an den Eckpunkten zugewiesen. Indem wir eine Liste von drei Farben zuweisen, können wir jeden Eckpunkt einzeln einfärben. Diese Farben werden für Visualisierungen verwendet, wobei jede Netzfläche mit einem interpolierten Farbton der Eckpunkte gerendert wird. Zum Beispiel wird im unterhalb angeführten Bild eine dreieckige Oberfläche mit Eckpunktfarben rot, grün und blau gezeigt.

![IMAGE](images/1-6-1/14_multi-color.png)
>1. Rot, grün und blau werden an den drei Eckpunkten des Polygonnetzes zugewiesen
2. Das resultierende Polygonnetz interpoliert die Farben der Eckpunkte

#### 1.6.1.4 Übung
{% if gitbook.generator == "pdf" or gitbook.generator == "mobi" or gitbook.generator == "epub" %}
>Beispieldateien zu diesem Abschnitt: [http://grasshopperprimer.com/appendix/A-2/1_gh-files.html](http://grasshopperprimer.com/appendix/A-2/1_gh-files.html)
{% else %}
>Beispieldateien zu diesem Abschnitt: [Download](../../appendix/A-2/gh-files/1.6.1_what is a mesh.gh)
{% endif %}

<style>
td:nth-child(1) {color: #008DB2}
td:nth-child(3)	{width: 10%;}
td {background-color: #F9F9F9;}
thead {display: none}
</style>


||||
|--|--|--|
|01.| Beginne eine neue Definition, drücke Strg+N (in Grasshopper)||
|02.| **Mesh/Primitive/Mesh Quad** - Ziehe eine **Mesh Quad** Komponente auf die Leinwand|![IMAGE](images/1-6-1/mesh-quad.png)|
|03.| **Mesh/Primitive/Construct Mesh** - Ziehe eine **Construct Mesh** Komponente auf die Leinwand|![IMAGE](images/1-6-1/construct-mesh.png)
|04.| Verbinde einen Netzfläche (F) Ausgabeparameter der **Mesh Quad** Komponente mit dem Netzfläche (F) Eingabeparameter der **Construct Mesh** Komponente|||

![IMAGE](images/1-6-1/exercise-01.png)
> **Mesh Quad** und **Construct Mesh** haben Standardwerte, die einzelne Polygonnetzoberflächen erstellen. Als nächstes werden wir die Standardwerte mit unseren eigenen Eckpunkten und Netzflächen ersetzen.

||||
|--|--|--|
|05.| **Params/Input/Panel** - Ziehe eine **Panel** Komponente auf die Leinwand||
|06.| Doppelklicke die **Panel** Komponente und setze den Wert auf '0'||
|07.| **Params/Input/Panel** - Ziehe vier weitere **Panel** Komponenten auf die Leinwand und setze ihre Werte auf 1,2,3, und 4 <br><br><blockquote>Du kannst auch die ursprüngliche **Panel** Komponente kopieren, indem Du sie anklickst und ziehst, während Du die Alttaste drückst, bevor Du den Klick wieder loslässt</blockquote>|
|08.| Verbinde die **Panels** mit den Eingabeparametern der **Mesh Quad** Komponente in folgender Reihenfolge:<ul>0 - A<br>1 - B<br>2 - C<br>3 - D</ul>||
|09.| **Mesh/Primitive/Mesh Triangle** - Ziehe eine **Mesh Triangle** Komponente auf die Leinwand|![IMAGE](images/1-6-1/mesh-triangle.png)|
|10.| Verbinde die **Panels** mit den Eingabeparametern der **Mesh Triangle** Komponente in der folgenden Reihenfolge: <ul>1 - A<br>2 - B<br>4 - C</ul>||
|11.| **Sets/Tree/Merge** - Ziehe eine **Merge** Komponente auf die Leinwand|![IMAGE](images/1-6-1/merge.png)|
|12.| Verbinde den Netzflächen (F) Ausgabeparameter der **Mesh Quad** Komponente mit dem Daten 1 (D1) Eingabeparameter der **Merge** Komponente und den Netzflächen (F) Ausgabeparameter der **Mesh Triangle** Komponente mit dem Daten 2 (D2) Eingabeparameter der **Merge** Komponente||
|13.| Verbinde den Ergebnis (R) Ausgabeparameter der **Merge** Komponente mit dem Netzflächen (F) Eingabeparameter der **Construct Mesh** Komponente|||

![IMAGE](images/1-6-1/exercise-02.png)
>Die Standard Eckpunkte (V) Liste der **Construct Mesh** Komponente hat vier Punkte, aber die **Mesh Triangle** Komponente nutzt einen Index von 4, was einem fünften Punkt in einer Liste entsprechen würde. Da hier nicht genug Eckpunkte vorliegen, gibt die **Construct Mesh** Komponente eine Fehlerwarnung aus. Um dies zu beheben, werden wir unsere eigene Liste von Punkten eingeben.

||||
|--|--|--|
|14.| **Params/Input/Panel** - Ziehe eine **Panel** Komponente auf die Leinwand||
|15.| Rechtsklicke auf die **Panel** Komponente und entferne die Auswahl von 'Multiline Data' option<br><br><blockquote>Als Standard ist die Option 'Multiline Data' im Paneel aktiviert. Indem wir sie deaktivieren, wird jede Zeile des Paneel als separates Element innerhalb der Liste gelesen.</blockquote>||
|16.| Doppelklicke die **Panel** Komponente, um sie zu bearbeiten und gib folgende Punkte ein: <ul>{0,0,0}<br>{1,0,0}<br>{1,1,0}<br>{0,1,0}<br>{2,0,0}</ul><blockquote>Versichere Dich, dass Du die richtige Schreibweise verwendest. Um einen Punkt in einem **Panel**, zu beschreiben, musst Du die geschweiften Klammern verwenden: '{' und '}' mit Komma zwischen den x, y, und z Werten</blockquote>||
|17.| Verbinde die **Panel** Komponente mit dem Eckpunkte (V) Eingabeparameter der **Construct Mesh** Komponente|||

![IMAGE](images/1-6-1/exercise-03.png)
>Wir haben nun ein Polygonnetz mit zwei Netzflächen und fünf Eckpunkten.  

Optional können wir die **Mesh Quad** und **Mesh Triangle** Komponenten mit einem Paneel ersetzen, das die Indices der Oberflächen definiert.

||||
|--|--|--|
|18.|**Params/Input/Panel** - Ziehe eine **Panel** Komponente auf die Leinwand||
|19.|Rechtsklicke auf die **Panel** Komponente und entferne die Auswahl von 'Multiline Data' <br><br><blockquote>Alternativ kannst Du die bestehende **Panel** Komponente, die wir für die Punkte verwendet haben, kopieren, da diese bereits 'Multiline Data' deaktiviert hat</blockquote>||
|20.|Doppelklicke auf die **Panel** Komponente, um sie zu bearbeiten und gib folgende Daten ein: <ul>Q{0,1,2,3}<br>T{1,2,4}</ul>||
|21.|Verbinde die **Panel** Komponente mit dem Netzflächen (F) Eingabeparameter der **Construct Mesh** Komponente|||

![IMAGE](images/1-6-1/exercise-04.png)

||||
|--|--|--|
|22.| **Params/Input/Colour Swatch** - Ziehe eine **Colour Swatch** Komponente auf die Leinwand|![IMAGE](images/1-6-1/colour-swatch.png)|
|23.| Klicke auf den farbigen Abschnitt der Komponente (der Standard ist weiß), um das Farbauswahlpaneel zu öffnen||
|24.| Nutze den Schieberegler, um die Werte G und B auf null zu stellen. Die angezeigte Farbe sollte nun rot sein||
|25.| **Params/Input/Colour Swatch** - Ziehe zwei weitere **Colour Swatch** Komponenten auf die Leinwand und setze ihre Farben auf blau und grün|
|26.| **Sets/Tree/Merge** - Ziehe eine **Merge** Komponente auf die Leinwand||
|27.| Verbinde die drei **Color Swatch** Komponenten mit den D1, D2, und D3 Eingabeparametern der **Merge** Komponente.||
|28.| Verbinde den Ergebnis (R) Ausgabeparameter der **Merge** Komponente mit dem Farbe (C) Eingabeparameter der **Construct Mesh** Komponente|||

![IMAGE](images/1-6-1/exercise-05.png)
>Wir haben fünf Eckpunkte, aber nur drei Farben. Grasshopper wird die Farben in einem sich wiederholenden Muster zuweisen. In diesem Fall werden die Eckpunkte 0 und 3 rot, die Eckpunkte 1 und 4 grün und der Eckpunkt 2 blau dargestellt.















