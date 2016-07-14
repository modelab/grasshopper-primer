### 1.4.5. Listen visualisieren
{% if gitbook.generator == "pdf" or "mobi" or "epub" %}
>Beispieldateien zu diesem Abschnitt: [http://grasshopperprimer.com/appendix/A-2/1_gh-files.html](http://grasshopperprimer.com/appendix/A-2/1_gh-files.html)
{% else %}
>Beispieldateien zu diesem Abschnitt: [Download](../../appendix/A-2/gh-files/1.4.5_list visualization.gh)
{% endif %}

##### Listen in Grasshopper zu verstehen kann schwierig sein, ohne die Daten von einer Komponente zur anderen fließen zu sehen. Dafür gibt es mehrere Wege um Listen zu visualisieren, die Dir helfen können Daten zu verstehen und zu verändern.

Es gibt viele verschiedene Wege Listen von Daten zu visualisieren. Der übliche Weg ist es eine Geometrie mit der Liste zu erstellen. Indem Du den R Ausgabeparameter der "Range" Komponente mit dem Y Eingabeparameter der "Construct Point" Komponente verbindest, kannst Du sehen, wie eine Reihe von Punkten in der Y Richtung dargestellt wird.

![IMAGE](images/1-4-5/1-4-5_001-list-visualization.png)

Lass uns einige Komponenten betrachten, die uns helfen Daten zu verstehen.

#### 1.4.5.1. DIE PUNKTLISTENKOMPONENTE
Die "Point List" Komponente ist ein nützliches Werkzeug, um die Reihenfolge einer Menge von Punkten in einer Liste darzustellen. Essentiell platziert die "Point List" Komponente einen Index neben die Punktgeometrie im Ansichtsfenster. Du kannst auch angeben, ob Du die Nummerierung oder die Verbindungslinien darstellen willst und welche Größe der Text haben soll.

![IMAGE](images/1-4-5/1-4-5_002-point-list.png)
>Du kannst die Reihenfolge einer Punktmenge mit der "Point List" Komponente darstellen.

#### 1.4.5.2. TEXTMARKEN
Die "Text Tag" Komponente ermöglicht es kurze Strings zu zeichnen (ein String ist eine Reihe von ASCII characters), um eine visuelle Ausgabe im Ansichtsfenster zu erhalten. Text und Position können als Eingabeparameter angegeben werden. Wenn Textmarken in die Szene gebacken werden, werden sie zu "Text Dots". Die andere interessante Sache über Textmarken ist, dass sie unabhängig von Ansichtsfenstern sind - das bedeutet, dass die Marken immer zur Kamera zeigen (inkl. Perspektive) und dass sie, unabhängig von der Vergrößerung, immer in derselben Größe dargestellt werden.

![IMAGE](images/1-4-5/1-4-5_003-text-tags.png)
>Du kannst Stringinformation im Ansichtsfenster mit der "Text Tag" Komponente darstellen. In diesem Setup haben wir uns entschieden die Werte eines jeden Punktes oberhalb der Punktposition anzugeben. Wir könnten jeden Text entsprechend darstellen.

Die "Text Tag 3d" Komponente funktioniert ähnlich wie die "Text Tag" Komponente. Sie unterscheiden sich dadurch, dass, wenn ein "Text Tag 3d" Objekt gebacken wird, es auch in Rhino ein Textobjekt wird. Die Skalierung der "Text Tag 3d" Schriftart kann auch durch einen Eingabeparameter bestimmt werden (was bei der "Text Tag" Komponente nicht geht).

![IMAGE](images/1-4-5/1-4-5_004-text-tag-3d.png)
>Du kannst die "Text Tag 3d" Komponente nutzen, um Informationen als Textobjekt in Rhino darzustellen.

#### 1.4.5.3. FARBE
Eines der anderen Dinge, die wir zur Visualisierung von Datenlisten nutzen können, ist die Zuweisung von Farben zu Geometrien. Grasshopper hat nur begrenzte Renderingmöglichkeiten, aber wir können einfache Open GL Einstellungen, wie Farbe, Glanzfarbe, Transparenz usw. festlegen. Der L0 Wert repräsentiert das untere Ende (linke Seite) eines Gradienten, wobei der L1 Wert entsprechend das obere Ende (rechte Seite) darstellt. Diese Werte entsprechen dem Start- und Endwert unserer Domäne. Die t Werte sind die Elemente der Liste, die auf die Spanne zwische L0 und L1 abgebildet werden. Die Ausgabe des Gradienten ist eine Liste von RGB Werten, welche jeweils einem Punkt in der Liste entsprechen. Rechtsklicke den Gradienten, um eine Voreinstellung für den Gradienten zu wählen oder bestimme Deine eigenen Farben an den Farbknotenpunkten.

![IMAGE](images/1-4-5/1-4-5_005-custom-preview.png)

![IMAGE](images/1-4-5/1-4-5_006-visualization-example.png)
>1. Punkte
2. Punktliste
3. Text Tag
4. Text Tag 3D
5. Benutzerdefinierte Farbvorschau



