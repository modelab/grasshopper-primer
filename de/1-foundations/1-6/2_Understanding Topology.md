### 1.6.2 Topology verstehen

#####Waehrend die Eckpunkte eines Polygonnetzes Information ueber Positionen erhaelt sind es wirklich die Verbindungen zwischen den Eckpunkten, die eine Polygonnetzstruktur ihre einzigartige Struktur und Flexibilitaet geben.

![IMAGE](images/1-6-2/01_meshMorph2.png)

#### 1.6.2.1 Was ist Topology?

Eine Einfuehrung zur Polygonnetzgeometrie waere unvollstaendig ohne zumindest eine grundlegende Einfuehrung zur Topologie. Weil Topologie aich mit den Verhaeltnissen zwischen eine Menge von "Dingen"und deren Eigenschaften eher als mit den "Dingen"selbst beschaeftigt, mobilisiert es eine riesige Bandbreite von greifbaren und ungreifbaren Anwendungen. In diesem Primer, sind wir an der grundsaetzlichen Anwenfung in einem parametrischen Arbeitsablauf interessiert, der uns die Moeglichkeit zur Erstellung und Kontrolle von Polygonnetzgeometrien gibt.

In Grasshopper gibt es zwei grundlegende Typen von Informationen, die ein Polygonnetz definieren und zwar Geometrie und Konnektivitaet; in anderen Worten, eine Menge an Punkten im Rhinoraum (Eckpunkte) und eine Menge von entsprechenden Punktzuordnungen (Oberflaechen).

Ohne Verbindungsinformation, ist ein Polygonnetz unstrukturier und daher immer noch undefiniert. Die Einfuehrung einer Anzahl von Oberflaechen ist der Schritt (oder Sprung) der letztendlich ein Polygonnetz erzeugt und seinen Charakter bezueglich Kontinuitaet, Konvergenz und Verbindungen generiert; dieses strukturelle Netzwerk wird als *topologischer Raum* bezeichnet.

![IMAGE - points with different connectivity](images/1-6-2/02_meshConnect.png)
>Die selbe Menge an Eckpunkten kannn unterschiedliche Verbindungsinformationen haben und ergibt unterschiedliche Topologien.

**Homeoeomorphismus**

![IMAGE - simple mesh diagram](images/1-6-2/03_meshMorph1.png)
>Die Punkte eines Polygonnetzes koennen bewegt werden ohne die Konnektivitaetsinformation zu veraendern. Das neue Polygonnetz hat die selbe Topologie wie das urspruengliche.

Es ist moeglich fuer zwei bestimmte Polygonnetzformen topologisch identisch zu sein. All dies wuerde bedeuten, dass sie aus der selben Anzahl von Punkten bestehen und dass die Punkte durch den selben Satz Netzflaechen strukturiert sind. Frueher haben wir festgelegt, dass Netzflaechen nur auf Indizes eines Satzes von Punkten beruhen und sich nicht auf die eigentliche Position im Rhinoraum beziehen. Deshalb ergibt sich, wenn der einzige Unterschied zwischen zwei Polygonnetzen eine bestimmte dreidimensionale Position von Punkten ist, die durch den Nutzer definert werden, dann sind die beiden Polygonnetze als "homoeomorphisch"zu betrachten (topologisch equivalent) und teilen deshalb alle topologischen Eigenschaften.

![IMAGE - homeomorphic alphabet](images/1-6-2/04_Alphabet_homeo.png)
>Ein Beispiel von Homoeomorphismus sind Buchstaben (merke dass einige der homoeomorphen Gruppen oberhalb sich dadurch unterscheiden, welche Schriftart sie nutzen).

![IMAGE](images/1-6-2/05_Mug_and_Torus_morph.gif)
>Topologisch equivalente Schale und Donut 
 
####1.6.2.2 Polygonnetzcharakteristika

**Orientierbar**

Ein Polygonnetz wird als *orientiebar* betrachtet, wenn es wohldefinierte Seite aufweist. Ein einfachess Beispiel eine nicht orientierbaren Polygonnetzes ergibt sich, wenn nebeneinander liegende Normales in entgegengesetzte Richtungen zeigen. Diese "umgekehrten Netzflaechen" koennen Probleme in der Visualisierung und beim Rendern darstellen, sowie bei der Fertigung von 3D-Drucken bereiten.

![IMAGE](images/1-6-2/06_orientable.png)
>1. Eine orientierbare Flaeche mit Netzflaechennormalen, die in die selbe Richtung deuten
2. Eine nicht orientierbare Flaeche hat angrenzende Normalen, die in verschiedene Richtungen deuten. 

**Open vs Closed**

Es ist oftmals notwendig zu wissen, ob ein Polygonnetz ein *geschlossenes* Polygonnetz ist, das einen Koerper beschreibt, oder ein *offenes* Polygonnetz, das lediglich eine 2D Flaeche darstellt. Der Unterschied kann Imperativ bezueglich der Herstellbarkeit sein. Du kannst keine einzelne Flaeche ohne Dicke 3D drucken, sondern must dem Polygonnetz zusaetzlich eine Dicke geben, so dass es ein Koerper wird. Polygonnetzkoerper sind auch Voraussetzung fuer boolsche Operationen (die im nachfolgenden Abschnitt behandelt werden).

Die **Mesh Edges** Komponente kann genutzt werden um dies zu bestimmen. Wenn keine der Kanten des Polygonnetz eine Valenz von 1 hat (wenn der E1 Ausgabeparameter *null* ausgibt), dann wissen wir dass alle Kanten 'innenliegende Kanten' sind und das Polygonnetz keine auessere Begrenzungskante hat, also ein geschlossenes Polygonnetz ist.

Auf der anderen Seite, wenn es 'offene Kanten' gibt, muss es sich um die Begrenzung des Polygonnetzes handeln und das Polygonnetz ist nicht geschlossen.

![IMAGE](images/1-6-2/07_open-closed.png)
>1. Ein geschlossenes Polygonnetz. Alle Kanten sind mit genau zwei Netzflaechen benachbart.
2. Ein offenes Polygonnetz. Die weisse Kanten grenzen nur an eine Netzflaeche an.

**Mannigfaltig oder Nicht-Mannigfaltig**

Nicht-mannigfaltige Geometrien sind essentiell Geometrien, die nicht in der "realen Welt" existieren koennen. Das bedeutet nicht notwendigerweise, dass sie "schlechte Geometrie" erzeugen, aber dass man darauf achten muss, da es Schwierigkeiten fuer Werkzeuge und Operationen bedeuten kann (z.B.: das rendern von lichbrechenden Effekten, Fluidsimulationen, boolsche Operationen, 3d Druck). Haeufige Bedingunegen, die in nicht-mannigfaltigen Polygonnetzen resultieren beinhalten: Selbstverschneidung, offene Kanten (von Loechern oder innenliegenden Netzflaechen), unverbundene Topologie und ueberlappende/duplizierte Flaechen. Ein Polygonnetz kann auch als *mannigfaltig* betrachtet werden, wenn es Eckpunkte beinhaltet, die von Netzflaechen geteilt werden, die keine Janten miteinander Teilen oder deren Valenz groesser als 2 ist und somit Verbindung mit mindestens drei Netzflaechen herstellen.

![IMAGE](images/1-6-2/08_non-manifold.png)
>1. Ein einfaches mannigfaltiges Polygonnetz
2. Drei Netzflaechen treffen sich in einer einzelnen Kante und sind nicht-mannigfaltig, stellen also eine T-Verbindung her
3. Zwei Netzflaechen treffen sich in einem Punkt aber teilen keine Kante und sind deshalb nicht-mannigfaltig

 
#### 1.6.2.3 Polygonnetze oder NURBS

In wiefern sind Polygonnetzgeometrien unterschiedlich von NURBS Geometrien? Wann ist es besser die eine oder die andere zu nutzen?

#####Parametrisierung
Im einem frueheren Kapitel, haben wir gesehen dass NURBS Flaechen durch eine Serie von NURBS Kurven in beiden Richtungen definiert sind. Diese Richtungen sind mit U und V benannt und ermoeglichen eine NURBS Flaeche entsprechend einer zweidimensionalen Domaene zu parametrisieren. Die Kurven selbst werden als Gleichungen im Computer gespeichert, wodurch die resultierende Flaeche mit beliebiger Praezision berechnet werden kann. Das verbinden zweier NURBS Flaechen wird in einer Polyflaeche resultieren, in der verschiedene Schnitte der Geometrie verschiedene UV Parameter und Kurvendefinitionen haben werden.

Polygonnetze auf der anderen Seite, werden durch eine konkrete Anzahl von genau definierten Eckpunkten und Netzflaechen bestimmt. Das Netzwerk von Eckpunkten wird generell nicht mit einfacjen UV Koordinaten beschrieben werden koennen. Die Darstellungspraezisions kann nun nur durch Verfeinerung des Polygonnetzen oder das hinzufuegen weiterer Netzflaechen verbessert werden, weil die Netzflaechen die Darstellungspraezision durch ihre Darstellung klar definieren. Das Fehlen von UV Koordinaten jedoch ermoeglicht es Polygonnetzte komplizierterer Geometrie flexibel in einem Polygonnetz handzuhaben, statt wie beim Fall der NURBS Darstellung auf eine Polyflaeche zurueckgreifen zu muessen.

>Anmerkung - Waehrend ein Polygonnetz keine implizite UV Parametrisierung hat, ist es manchmal sinnvoll eine soche Parametrisierung anzuwenden, um eine Textur oder ein Bild auf eine Polygonnetzgeomertie anzuwenden um sie zu rendern. Manche Modellierungsprogramme haben deshalb die Moeglichkeit UV Koordinaten fuer Polygonnetze als *Attribute* (aehnlich wie Eckpunktfarben) den Eckpunkten zuzuweisen, die dann bearbeitet und veraendert werden koennen. Diese sind normalerweise zugeweisen und werden nicht durch das Polygonnetz selbst bestimmt.

#####Lokale und Globale Einfluesse

Ein wichtiger Unterschied ist der Umfang, in welchem lokale Veraenderungen in einem Polygonnetz oder einer NURBS Geometie die Gesamtform beeinflussen. Polygonnetzgeometien sind komplett lokal. Einen Eckpunkt zu bewegen beeinflusst lediglich angrenzende Netzflaechen. Bei NURBS Flaechen, wird der Umfang des Einflusses einer Veraenderung komlizierter und haeangt vom Graf der Flaeche und den Gewichtungen und Knoten der Kontrollpunkte ab. Generell jedoch wird die Bewegung eines einzelnen Kontrollpunktes einer NURBS Flaeche eine globalere Veraenderung der Geometrie bedeuten.

![IMAGE](images/1-6-2/09_NURBSvsMESH-02.jpg)
>1. NURBS Flaechen - die Veraenderung eines Kontrollpunktes hat globale Wirkung
2. Polygonnetzgeometrie - die Bewegung eines Eckpunktes hat lokalen Einfluss

Eine Analogie, die hier hilfreich ist, ist der Vergleich einer Vektorgrafik (bestehend aus Linien und Kurven) mit einem Rasterbild (bestehend aus individuellen Punkten). Wenn Du auf ein Vektorbild zoomst, werden die Kurven scharf und klar bleiben, waehrend die Vergroesserung eines Rasterbildes in der Ansicht individueller Pixel enden wird. In dieser Analogie kann eine Vektorgraphik mit einer NURBS Flaeche verglichen werden, waehren sich ein Polygonnetz wie ein Rasterbild verhaelt.

![IMAGE](images/1-6-2/10_vector raster analogy.png)
>Vergroesserung einer NURBS Flaeche erhaelt die geglaettete Kurve, waehrend das Polygonnetzelement eine feste Aufloesung hat

Es ist interessant festzustellen, dass waehrend NURBS Flaechen als mathematische Gleichungen gespeichert werden, die letztendliche Darstellung der Flaechen Polygonnetze benoetigt. Es ist nicht moeglich in einem Computer eine kontinuierliche Gleichung darzustellen. Statt dessen muss er die Gleichungen in kleinere Teile herunterbrechen, was darin resultiert, dass fuer jede Render- und Darstellungsaktioen ein Polygonnetz der entsprechenden NURBS Flaeche berechnet werden muss. In unserer Analogie koennen wir sehen, dass der Computer, auch wenn er die Gleichung einer Kurve speichern kann, diese in eine Serie von diskreten Pixeln auf dem Bildschirm umwandeln muss, um sie darzustellen. 

#### 1.6.2.4 Vor und Nachteile von Polygonnetzen

Wenn wir uns fragen "Was sind die Vor- und Nachteile der Modellierung mit Polygonnetzen?"muessen wir uns eigentlich Fragen "Was sind die Vor- und Nachteile einer Modellierung mit Formen die nur durch eine Menge von Eckpunkten und dem entsprechenden topologischen Netzwerk bestimmt werden?". Durch diese Methode der Rahmung der Frage ist es einfacher zu sehen wie die "einfache" Natur von Polygonnetzen der ausschlaggebende Aspekt fuer die Bevorzugung einer Modellierung in dieser Technik ist, abhaengig vom Kontext der entsprechenden Anwendung.

Polygonnetzt koennen in einer Situation von Vorteil sein, in der:

- Das dynamische Rendering einer Formveraenderung ohne Veraenderung der Topologie angestrebt wird
- Eine diskrete Annaeherung einer gerundeten Geometrie ausreichend ist
- Eine Geometrie niedrigerer Aufloesung systematisch gegleatter (oder artikuliert) wird, indem computerbasierte Methoden angewendet werden um eine hoehere Aufloesung zu erzielen
- Wenn das niedrig aufgeloeste Modell gleichzeitig hohe aufloesung von Detail unterstuetzen muss

Polygonnetze koennen in folgenden Situationen von Nachteil sein:

- Wenn Kruemmung und Glaettung mit einem hohen Level an Praezision dargestellt wrden muessen
- Wahre Ableitungen berechnet werden muessen
- Die Geometrie in einen Koerper fuer industrielle Produktion umgewandelt werden muss
- Die Finale Form einfache Veraenderungen zulassen soll

 



