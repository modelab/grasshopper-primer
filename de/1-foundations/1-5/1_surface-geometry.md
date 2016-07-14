###1.5.1. Flächen Geometrien

#####NURBS (non-uniform rational B-splines) sind mathematische Repräsentationen, die ein Modell einer beliebigen Form akkurat aus einer einfachen 2D Linie, einem Kreis, Boden oder einer Kiste die komplexeste, organische 3D Freiformfläche oder -körper entwickeln können. Auf Grund ihrer Flexibilität und Präzision können NURBS Modelle in jedem beliebigen Prozess, von der Illustration und Animation bis zur Herstellung, genutzt werden.

Abgesehen von ein paar primitiven Flächentypen, wie Kugeln, Kegel, Flächen und Zylinder, unterstützt Rhino drei verschiedene Arten von Freiform Flächentypen, wobei der nützlichste die NURBS Fläche ist. Ähnlich wir bei den Kurven, kann mit der NURBS Fläche jede mögliche Form als Fläche dargestellt werden, was die Rückfallebene in Rhino darstellt. Sie ist außerdem die bei weitem nützlichste Flächendefinition und die, auf die wir uns konzentrieren werden.

![IMAGE](images/1-5-1/1-5-1_001-primitives.png)
>1. Kugel Primitivkörper [plane, radius]
2. Zylinder Primitivkörper [plane, radius, height]
3. Fläche Primitivkörper [plane, width, height]
4. Kegel Primitivkörper [plane, radius, height]

####1.5.1.1. NURBS FLÄCHEN
NURBS Flächen sind sehr ähnlich zu NURBS Kurven. Die selben Algorithmen werden verwendet, um die Form, Normalen, Tangenten, Krümmungen und anderen Eigenschaften zu berechnen, aber es gibt auch klare Unterschiede. Zum Beispiel haben Kurven Tangentenvektoren und Normalenebenen, während Flächen Normalenvektoren und Tangentialebenen besitzen. Das bedeutet, dass Kurven an definierten Positionen keine Orientierung haben, während Flächen keine definierte Richtung besitzen. Im Fall von NURBS Flächen gibt es genau zwei Richtungen, die in der Geometrie einbeschrieben sind, weil NURBS Flächen aus rechtwinkligen Rastern aus {u} und {v} Kurven aufgebaut sind. Auch wenn diese Richtungen oft beliebig sind, werden wir sie sowieso nutzen, weil sie uns das Leben so viel einfacher machen.

![IMAGE](images/1-5-1/1-5-1_002-nurbs-surface.png)

>Du kannst Dir NURBS Flächen als Raster aus NURBS Kurven in zwei Richtungen vorstellen. Die Form einer NURBS Fläche ist durch eine Anzahl von Kontrollpunkten und den Grad der Fläche in u und v Richtung definiert. NURBS Flächen sind eine effiziente Art um Freiformflächen mit einem hohen Grad an Präzision zu speichern und zu repräsentieren.

**Flächen Domänen**
Eine Flächendomäne ist durch einen Bereich von (u,v) Parametern bestimmt, der in einen 3D Punkt auf der Fläche ausgewertet werden kann. Die Domäne ist normalerweise in jeder Richtung (u oder v) durch zwei reelle Zahlen (u_min und u_max) und (v_min und v_max) beschrieben. Die Domäne einer Fläche zu verändern wird Reparametrisierung genannt.

In Grasshopper ist es oft nützlich eine NURBS Fläche zu reparametrisieren, sodass die u und v Domäne jeweils von 0 bis 1 reicht. Dies ermöglicht es uns die Fläche einfach auszuwerten und mit ihr zu arbeiten.

![IMAGE](images/1-5-1/1-5-1_003-surface-domain.png)
>Auswertung von Parametern eines gleichmäßigen Intervalls im 2D Parameterraster wird nicht notwendigerweise eine gleichmäßige Unterteilung des 3D Raums bedeuten.

**Flächenauswertung**
Die Auswertung einer Fläche an einem Parameter innerhalb der Flächendomäne resultiert in einem Punkt auf der Fläche. Merke Dir, dass der Mittelpunkt einer Domäne (mid-u,
mid-v) nicht notwendigerweise der Mittelpunkt der 3D Fläche ist. Wenn Du nun u- und v-Werte außerhalb der Domäne der Fläche auswerten willst, wirst Du kein nützliches Ergebnis erhalten.

![IMAGE](images/1-5-1/1-5-1_004-surface-eval.png)

**Normalenvektoren und Tangentialebenen**
Die Tangentialebene einer Fläche an einem bestimmten Punkt ist die Ebene, welche die Fläche an einem Punkt berührt. Die z-Richtung der Tangentialfläche repräsentiert die Normalentichtung der Fläche an diesem Punkt.

Grasshopper behandelt NURBS Flächen ähnlich wie Rhino, weil es diese auf demselben Kern von Operationen aufbaut, die notwendig sind, um die Fläche zu erzeugen. Da Grasshopper jedoch die Fläche oberhalb des Rhinoansichtsfenster darstellt (aus diesem Grund kann man die Geometrien, welche in Grasshopper erzeugt werden, nicht auswählen, weil sie in die Szene gebacken werden) sind manche der Mesheinstellungen etwas niedriger, um die Geschwindigkeit von Grasshopper relativ hoch zu halten. Du hast vielleicht festgestellt, dass manche Polygonnetze (Meshes) facettiert sind, aber das ist zu erwarten und ist ein Ergebnis der Grasshopper Darstellungsoptionen. Jede gebackene Geometrie wird die höheren Mesheinstellungen von Rhino verwenden.

####1.5.1.2. FLÄCHEN PROJIZIEREN
Im vorherigen Abschnitt, haben wir erklärt, dass NURBS Flächen ihren eigenen Koordinatenraum besitzen und dass dieser durch u und v Domänen beschrieben wird. Dies bedeutet, dass zweidimensionale Geometrien, welche durch x und y Koordinaten beschrieben werden auf den uv Raum der Fläche abgebildet werden können. Die Geometrie wird sich verändern und verzerren, um sich an die Krümmung der Fläche anzupassen. Dies ist unterschiedlich zu einer einfachen Projektion auf eine Fläche, bei der Vektoren von der  2D Geometrie in eine bestimmte Richtung gezeichet werden, bis sie mit einer Fläche verschneiden.

![IMAGE](images/1-5-1/1-5-1_005-surface-mapping.png)
>Du kannst Dir eine Projektion als einen Schattenwurf auf eine Fläche vorstellen und eine Abbildung als eine Geometrie, die über die Fläche gezogen wird.
1. Abgebildete Geometrie definiert durch uv Koordination
2. Projizierte Geometrie auf einer Fläche

So wie 2D Geometrie auf den uv Raum einer Fläche abgebildet werden kann, ist es möglich eine Geometie, die in einer Kiste enthalten ist, auf eine verzerrte Kiste auf einem Flächenabschnitt abzubilden. Diese Operation wird "Box Morph" genannt und ist nützlich um eine gekrümmte Fläche mit dreidimensionalen geometrischen Komponenten zu bevölkern.

![IMAGE](images/1-5-1/1-5-1_006-box-morphing.png)

Um eine Reihe verzerrter Kisten auf einer Fläche anzuordnen, muss die Flächendomäne unterteilt werden, um ein Raster von Flächenabschnitten zu erzeugen. Die verzerrten Kisten werden erzeugt, indem Normalenvektoren an den Ecken eines jeden Flächenabschnitts bis zur gewünschten Höhe angetragen werden und eine Kiste erzeugen, deren Eckpunkte durch die Endpunkte dieser Vektoren bestimmt werden.

####1.5.1.3. MORPH DEFINITION
{% if gitbook.generator == "pdf" or "mobi" or "epub" %}
>Beispieldateien zu diesem Abschnitt: [http://grasshopperprimer.com/appendix/A-2/1_gh-files.html](http://grasshopperprimer.com/appendix/A-2/1_gh-files.html)
{% else %}
>Beispieldateien zu diesem Abschnitt: [Download](../../appendix/A-2/gh-files/1.5.1.3_morphing definition.gh)
{% endif %}


In diesem Beispiel werden wir die "Box Morph" Komponente einsetzen um eine NURBS Fläche mit geometrischen Komponenten zu bevölkern.

![IMAGE](images/1-5-1/1-5-1_007-morphing-definition.png)
>1. NURBS Fläche bevölkert mit Komponenten.
2. Ursprüngliche Komponente in ihrer Referenzkiste.
3. Fläche unterteilt in Flächenabschnitte.
4. Reihe verzerrter Kisten auf einer Fläche.

<style>
td:nth-child(1) {color: #008DB2}
td:nth-child(3)	{font-size: 70%;width: 15%;}
td {background-color: #F9F9F9;}
thead {display: none}
</style>


||||
|--|--|--|
|01.|Beginne eine neue Definition, drücke Strg+N (in Grasshopper)||
|02.|**Params/Geometry/Surface** – Ziehe einen **Surface** Parameter auf die Leinwand<br><blockquote>Diese Fläche werden wir mit geometrischen Komponenten bevölkern.</blockquote>|[![IMAGE](images/1-5-1/1-5-1_ex_01-surface.png)](../../appendix/A-1/0_index-of-components.html#PGSrf)|
|03.|**Params/Geometry/Geometry** – Ziehe einen **Geometry** Parameter auf die Leinwand<br><blockquote>Dies ist die Komponente, die auf der Fläche aufgereiht wird.</blockquote>|[![IMAGE](images/1-5-1/1-5-1_ex_02-geometry.png)](../../appendix/A-1/0_index-of-components.html#PGGeo)|
|04.|Rechtsklicke auf den **Surface** Parameter und waehle “Set One Surface” – wähle eine Fläche im Rhinoansichtsfenster, die Du referenzieren möchtest||
|05.|Rechtsklicke den **Geometry** Parameter und wähle “Set One Geometry” – wähle Deine Rhinogeometrie||
|06.|**Maths/Domain/Divide Domain2** – Ziehe eine **Divide Domain2** Komponente auf die Leinwand|[![IMAGE](images/1-5-1/1-5-1_ex_03-divide-domain2.png)](../../appendix/A-1/0_index-of-components.html#MDDivide)|
|07.|**Params/Input/Number Slider** – Ziehe drei **Number Sliders** auf die Leinwand||
|08.|Doppelklicke den ersten **Number Slider** und setze folgende Werte: <ul>Rounding: Integer<br>Lower Limit: 0<br>Upper Limit: 10<br>Value: 5</ul>||
|09.|Setze dieselben Werte beim zweiten und dritten **Number Sliders**||
|10.|Verbinde den Ausgabeparameter des **Surface** Parameter mit dem Domäne (I) Eingabeparameter der **Divide Domain2** Komponente||
|11.|Verbinde den ersten **Number Slider** mit dem Anzahl U (U) Eingabeparameter der **Divide Domain2** Komponente||
|12.|Verbinde den zweiten **Number Slider** mit dem Annzahl V (V) Eingabeparameter der **Divide Domain2** Komponente||
|13.|**Transform/Morph/Surface Box** – Ziehe die **Surface Box** Komponente auf die Leinwand|[![IMAGE](images/1-5-1/1-5-1_ex_04-surface-box.png)](../../appendix/A-1/0_index-of-components.html#TMSBox)|
|14.|Verbinde den Ausgabeparameter des **Surface** Parameter mit dem Fläche (S) Eingabeparameter der **Surface Box** Komponente||
|15.|Verbinde den Segmente (S) Ausgabeparameter der **Divide Domain2** Komponente mit dem Domäne (D) Eingabeparameter der **Surface Box** Komponente|||

![IMAGE](images/1-5-1/1-5-1_ex_05-definition1.png)
>Du musst nun ein Raster aus verzerrten Kisten sehen, die Deine Referenzfläche bevölkern. Verändere die Anzahl U und V Schieberegler um die Zahl der Kisten zu verändern und bewege den Höhenschieberegler um ihre Höhe anzupassen.

||||
|--|--|--|
|16.|Verbinde den dritten **Number Slider** mit dem Höhe (H) Eingabeparameter der**Surface Box** Komponente||
|17.|**Surface/Primitive/Bounding Box** – Ziehe eine **Bounding Box** Komponente auf die Leinwand|[![IMAGE](images/1-5-1/1-5-1_ex_06-bounding-box.png)](../../appendix/A-1/0_index-of-components.html#SPBBox)|
|18.|**Transform/Morph/Box Morph** – Ziehe eine **Box Morph** Komponente auf die Leinwand|[![IMAGE](images/1-5-1/1-5-1_ex_07-box-morph.png)](../../appendix/A-1/0_index-of-components.html#TMMorph)|
|19.|Verbinde den Ausgabeparameter des **Geometry** Parameter mit dem Inhalt (C) Eingabeparameter der **Bounding Box** Komponente||
|20.|Verbinde den Ausgabeparameter des **Geometry** Parameter mit dem Geometrie (G) Eingabeparameter der **Box Morph** Komponente||
|21.|Verbinde den Kiste (B) Ausgabaparameter der **Bounding Box** Komponente mit dem Referenz(R) Eingabeparameter der **Box Morph** Komponente||
|22.|Verbinde den verzerrte Kiste (B) Ausgabeparameter der **Surface Box** Komponente mit dem Ziel(T) Eingabeparameter der **Box Morph** Komponente|||

![IMAGE](images/1-5-1/1-5-1_ex_08-definition2.png)

>Du solltest nun sehen, wie die Fläche mit Deiner Geometrie bevölkert wurde.

![IMAGE](images/1-5-1/1-5-1_end-image.png)

