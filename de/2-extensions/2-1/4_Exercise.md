### 2.1.4. Übung

##### In diesem Abschnitt werden wir durch eine einfache Übung mit den Element* primitiven Netzkörpern als Basis gehen. Wir werden die Halbkantendatenstruktur einarbeiten und beide Merkmale der Transformationskomponenten nutzen (uniform und pro Eckpunkt)
![IMAGE](images/2-1-4/2-1-4_000_Cover.png)

{% if gitbook.generator == "pdf" or gitbook.generator == "mobi" or gitbook.generator == "epub" %}
>Beispieldateien zu diesem Abschnitt: [http://grasshopperprimer.com/appendix/A-2/1_gh-files.html](http://grasshopperprimer.com/appendix/A-2/1_gh-files.html)
{% else %}
>Beispieldateien zu diesem Abschnitt: [Download](../../appendix/A-2/gh-files/2.1_element addon.gh)
{% endif %}

<style>
td:nth-child(1) {color: #008DB2}
td:nth-child(3)	{width: 10%;}
td {background-color: #F9F9F9;}
thead {display: none}
</style>


||||
|--|--|--|
|01.| Beginne eine neue Definition, drücke Strg-N (in Grasshopper)||
|02.| **Element\*/Primitive/Icosohedron** - Ziehe eine **Icosohedron** Komponente auf die Leinwand|![IMAGE](images/2-1-4/2-1-4_001_Icosohedron.png)|
|03.| **Params/Input/Number Slider** - Ziehe eine **Number Slider** Komponente auf die Leinwand||
|04.| Verbinde den **Number Slider** mit dem Radius (R) Eingabeparameter der **Icosohedron** Komponente||
|05.| Doppelklicke den **Number Slider** und setze folgende Werte: <ul>Name: Radius<br>Rounding: Integer<br>Lower Limit: 5<br>Upper Limit: 50<br>Value: 25</ul> ||
|06.| **Element\*/Data/Face Neighbors** - Ziehe eine **Face Neighbors** Komponente auf die Leinwand| ![IMAGE](images/2-1-4/2-1-4_002_Face-Neighbors.png)|
|07.| Verbinde den Polygonnetz (M) Ausgabeparameter der **Icosohedron** Komponente mit dem Polygonnetz (M) Eingabeparameter der **Face Neighbors** Komponente.|||

![IMAGE](images/2-1-4/2-1-4_003_Definition.png)
>Wenn wir die Daten des Ausgabeparameters für benachbarte Netzflächenkanten (NE) ansehen, erkennen wir einen Baum mit 20 Ästen, wobei jeder Ast drei Linien beinhaltet. Die 20 Äste repräsentieren jeweils eine Netzfläche des Ikosaeder, während die drei Linien die jeweiligen Kanten der dreieckigen Netzflächen darstellt.

||||
|--|--|--|
|08.| **Params/Input/Number Slider** - Ziehe eine **Number Slider** Komponente auf die Leinwand und setze folgende Werte: <ul>Rounding: Float<br>Lower Limit:0<br>Upper Limit: 0.5</ul>||
|09.| **Params/Input/Panel** - Ziehe eine **Panel** Komponente auf die Leinwand||
|10.| Doppelklicke die **Panel** Komponente und gebe "1" in das Textfeld ein||
|11.| **Math/Operators/Subtraction** - Ziehe eine **Subtraction** Komponente auf die Leinwand|![IMAGE](images/2-1-4/2-1-4_004_Subtraction.png)|
|12.| Verbinde die **Panel** Komponente mit dem Wert "1" mit dem A Eingabeparameter und verbinde den Schieberegler mit dem B Eingabeparameter der **Subtraction** Komponente||
|13.| **Sets/Tree/Merge** - Ziehe eine **Merge** Komponente auf die Leinwand|![IMAGE](images/2-1-4/2-1-4_005_Merge.png)|
|14.| Verbinde den **Number Slider** mit dem D1 Eingabeparameter der **Merge** Komponente, und verbinde den Ausgabeparameter R der **Subtraction** Komponente mit dem D2 Eingabeparameter der **Merge** Komponente||
|15.| **Curve/Analysis/Evaluate Curve** - Ziehe eine **Evaluate Curve** Komponente auf die Leinwand|![IMAGE](images/2-1-4/2-1-4_006_Evaluate-Curve.png)
|16.| Verbinde den Netzflächenkanten (NE) Ausgabeparameter der **Face Neighbors** Komponente mit dem Kurve (C) Eingabeparameter der **Evaluate Curve** Komponente||
|17.| Rechtsklicke den Kurve (C) Eingabeparameter der **Evaluate Curve** Komponente und wähle "Graft". Dies wird einen neuen Datenast für jede Kante erstellen.||
|18.| Verbinde den Ergebnis (R) Ausgabeparameter der **Merge** Komponente mit dem Parameter (t) Eingabeparameter der **Evaluate Curve** Komponente. Auf Grund des Aufpropfens (Graft) des Kurveneingabeparameters wird jede Kante an den Werten von beiden Parametern der **Merge** Komponente ausgewertet|||

![IMAGE](images/2-1-4/2-1-4_007_Definition.png)


||||
|--|--|--|
|19.| **Sets/Tree/Trim Tree** - Ziehe eine **Trim Tree** Komponente auf die Leinwand|![IMAGE](images/2-1-4/2-1-4_008_Trim-Tree.png)|
|20.| Verbinde den Punkte (P) Ausgabeparameter der **Evaluate Curve** mit dem Baum (T) Eingabeparameter der **Trim Tree** Komponente. <br><blockquote>Der Standardwert des Tiefe (D) Eingabeparameters fuer **Trim Tree** ist 1. Dies reduziert die Tiefe unseres Datenbaumes um eine Ebene, indem die äußersten Äste miteinander verschmolzen werden. Das Ergebnis sind 20 Äste zu je sechs Punkten. </blockquote>||
|21.| **Curve/Spline/Polyline** - Ziehe eine **Polyline** Komponente auf die Leinwand|![IMAGE](images/2-1-4/2-1-4_009_Polyline.png)|
|22.| Verbinde den Baum (T) Ausgabeparameter der **Trim Tree** Komponente mit dem Eckpunkte (V) Eingabeparameter der **Polyline** Komponente||
|23.| Rechtsklicke den Geschlossen (C) Eingabeparameter der **Polyline** Komponente, klicke "Set Boolean" und setze den Wert auf Wahr <br><blockquote>Dieser Schritt hat eine geschlossene Polylinie mit sechs Seiten für jede ursprüngliche Netzfläche des Polygonnetzes erzeugt.</blockquote>||
|24.| **Element\*/Transform/Mesh Frame** - Ziehe eine **Mesh Frame** Komponente auf die Leinwand.|![IMAGE](images/2-1-4/2-1-4_010_Mesh-Frame.png)
|25.| Verbinde den Polylinie (Pl) Ausgabeparameter der **Polyline** Komponente mit dem Geometrie (G) Eingabeparameter der **Mesh Frame** Komponente <br><blockquote>Merke, dass die **Mesh Frame** Komponente entweder Polygonnetze oder eine Liste geschlossener Polylinien als Eingabeparameter annehmen kann</blockquote>||
|26.| **Params/Input/Number Slider** - Ziehe eine **Number Silder** Komponente auf die Leinwand. Wir werden das Standardintervall von 0 bis 1 für den Schieberegler beibehalten||
|27.| Verbinde den **Number Slider** mit dem Faktor (F) Eingabeparameter der **Mesh Frame** Komponente|||

![IMAGE](images/2-1-4/2-1-4_011_Definition.png)
![IMAGE](images/2-1-4/2-1-4_012_Definition.png)

||||
|--|--|--|
|28.| **Element\*/Utility/Mesh Combine and Clean** - Ziehe eine **Mesh Combine and Clean** Komponente auf die Leinwand|![IMAGE](images/2-1-4/2-1-4_013_Combine-and-Clean.png)|
|29.| Verbinde den Polygonnetz (M) Ausgabeparameter der **Mesh Frames** Komponente mit dem Polygonnetz (M) Eingabeparameter der **Mesh Combine and Clean** Komponente||
|30.| Rechtsklicke den Polgonnetz (M) Eingabeparameter der **Mesh Combine and Clean** Komponente und wähle "Flatten" <br><blockquote>Durch das Einebnen des Datenbaums der Polygonnetze, wird**Combine and Clean** alle 20 Netzflächen zu einem einzigen Polygonnetz verbinden</blockquote>||
|31.| **Element\*/Transform/Mesh Thicken** - Ziehe eine **Mesh Thicken** Komponente auf die Leinwand|![IMAGE](images/2-1-4/2-1-4_014_Mesh-Thicken.png)|
|32.| Verbinde den Polygonnetz (M) Ausgabeparameter der **Combine and Clean** Komponente mit dem Polygonnetz (M) Eingabeparameter der **Mesh Thicken** Komponente||
|33.| **Element\*/Subdivide/Catmull Clark Subdivision** - Ziehe eine **Catmull Clark Subdivision** Komponente auf die Leinwand|![IMAGE](images/2-1-4/2-1-4_015_Catmull-Clark.png)
|34.| Verbinde den Polygonnetz (M) Ausgabeparameter der **Mesh Thicken** Komponente mit dem Polygonnetz (M) Eingabeparameter der **Catmull Clark Subdivision** Komponente|||

![IMAGE](images/2-1-4/2-1-4_016_Definition.png)
![IMAGE](images/2-1-4/2-1-4_017_Definition.png)
>Wir haben die dreieckigen Netzflächen des ursprünglichen Polygonnetzes abgeflacht und damit Ringe rund um die ursprünglichen Eckpunkte geschaffen. Wir haben auch einen Rahmen für jede Netzfläche erzeugt und dann das gesamte Polygonnetz mit einer Wandstärke versehen, bevor wir es durch Unterteilung weiter verfeinert haben. Als nächstes werden wir den Vorteil der Anwendung der Transformierungskomponente auf die jeweiligen Eckpunkte des Polygonnetzes nutzen, indem wir einen Attraktorpunkt einführen.

||||
|--|--|--|
|35.| **Params/Geometry/Point** - Ziehe einen **Point** Container auf die Leinwand|![IMAGE](images/2-1-4/2-1-4_018_Point.png)|
|36.| Rechtsklicke den **Point** Container und wähle "Set on point", um einen Punkt aus dem Rhino Ansichtsfenster auszuwählen <br><blockquote>Tip - Du kannst auch einen Punkt direkt in Grasshopper erzeugen, indem Du auf die Leinwand doppelklickst und so das Suchfenster öffnest, bevor Du die Koordinaten des Punktes, wie z.B. "10,10,0" (ohne die Anführungszeichen) eingibst</blockquote>||
|37.| **Mesh/Analysis/Deconstruct Mesh** - Ziehe eine **Deconstruct Mesh** Komponente auf die Leinwand|![IMAGE](images/2-1-4/2-1-4_019_Deconstruct-Mesh.png)|
|38.| Verbinde den Polygonnetz (M) Ausgabeparameter der **Combine and Clean** Komponente mit dem Polygonnetz (M) Eingabeparameter der **Deconstruct Mesh** Komponente. <br><blockquote>Wir werden hierdurch die Eckpunkte unseres kombinierten Polygonnetzes extrahieren und im Anschluss den Attraktorpunkt auf diese anwenden</blockquote>||
|39.| **Vector/Point/Distance** - Ziehe eine **Distance** Komponente auf die Leinwand|![IMAGE](images/2-1-4/2-1-4_020_Distance.png)|
|40.| Verbinde den Eckpunkte (V) Ausgabeparameter der **Deconstruct Mesh** Komponente mit dem A Eingabeparameter der **Distance** Komponente||
|41.| Verbinde den **Point** Container mit dem B Eingabeparameter der **Distance** Komponente||
|42.| Verbinde den Distanz (D) Ausgabeparameter der **Distance** Komponente mit dem PerVertex Daten (VD) Eingabeparameter der **Thicken** Komponente||
|43.| **Params/Input/Number Slider** - Ziehe zwei **Number Slider** Komponenten auf die Leinwand. Wir werden diese benutzen, um die obere und untere Grenze für die **Mesh Thicken** Komponente zu bestimmen||
|44.| Doppelklicke die beiden **Number Sliders** und setze die Werte. In diesem Beispiel haben wir den ersten Schieberegler auf den Standardwerten belassen und die obere Grenze für den zweiten Schieberegler auf 5.0 gesetzt||
|45.| **Maths/Domain/Construct Domain** - Ziehe eine **Construct Domain** Komponente auf die Leinwand|![IMAGE](images/2-1-4/2-1-4_021_Construct-Domain.png)
|46.| Verbinde die beiden Schieberegler mit den A und B Eingabeparametern der **Construct Domain** Komponente||
|47.| Verbinde den Domäne (I) Ausgabeparameter der **Construct Domain** Komponente mit den Min und Max Werte (D) Eingabeparameter der **Mesh Thicken** Komponente.||
|48.| Rechtsklicke den Typ (T) Eingabeparameter der **Thicken** Komponente, wähle "Set Integer" und gib den Wert 1 ein <br><blockquote>Du kannst auch die Option PerVertex Daten einschalten, indem Du die *Boolean Toggle** Komponente auf Wahr setzt.</blockquote>|||

![IMAGE](images/2-1-4/2-1-4_022_Definition.png)
![IMAGE](images/2-1-4/2-1-4_023_Definition.png)
---
![IMAGE](images/2-1-4/2-1-4_024_Definition.png)

