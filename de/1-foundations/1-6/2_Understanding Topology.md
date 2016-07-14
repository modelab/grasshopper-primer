### 1.6.2 Topologie verstehen

##### Während die Eckpunkte eines Polygonnetzes Information über Positionen erhält, sind es wirklich die Verbindungen zwischen den Eckpunkten, die einer Polygonnetzstruktur ihre einzigartige Struktur und Flexibilität geben.

![IMAGE](images/1-6-2/01_meshMorph2.png)

#### 1.6.2.1 Was ist Topologie?

Eine Einführung in die Polygonnetzgeometrie wäre unvollständig ohne zumindest eine grundlegende Einführung in die Topologie. Weil Topologie sich mit den Verhältnissen zwischen einer Menge von "Dingen" und deren Eigenschaften eher als mit den "Dingen" selbst beschäftigt, mobilisiert es eine riesige Bandbreite von greifbaren und ungreifbaren Anwendungen. In diesem Primer sind wir an der grundsätzlichen Anwendung in einem parametrischen Arbeitsablauf interessiert, der uns die Möglichkeit zur Erstellung und Kontrolle von Polygonnetzgeometrien gibt.

In Grasshopper gibt es zwei grundlegende Typen von Informationen, die ein Polygonnetz definieren und zwar Geometrie und Konnektivität; in anderen Worten, eine Menge an Punkten im Rhinoraum (Eckpunkte) und eine Menge von entsprechenden Punktzuordnungen (Netzflächen).

Ohne Verbindungsinformation ist ein Polygonnetz unstrukturiert und daher immer noch undefiniert. Die Einführung einer Anzahl von Oberflächen ist der Schritt (oder Sprung) der letztendlich ein Polygonnetz erzeugt und seinen Charakter bezüglich Kontinuität, Konvergenz und Verbindungen generiert; dieses strukturelle Netzwerk wird als *topologischer Raum* bezeichnet.

![IMAGE - points with different connectivity](images/1-6-2/02_meshConnect.png)
>Dieselbe Menge an Eckpunkten kann unterschiedliche Verbindungsinformationen haben und ergibt unterschiedliche Topologien.

**Homeoeomorphismus**

![IMAGE - simple mesh diagram](images/1-6-2/03_meshMorph1.png)
>Die Punkte eines Polygonnetzes können bewegt werden ohne die Konnektivitätsinformation zu verändern. Das neue Polygonnetz hat dieselbe Topologie wie das ursprüngliche.

Es ist möglich für zwei bestimmte Polygonnetzformen topologisch identisch zu sein. All dies würde bedeuten, dass sie aus derselben Anzahl von Punkten bestehen und dass die Punkte durch denselben Satz Netzflächen strukturiert sind. Früher haben wir festgelegt, dass Netzflächen nur auf Indizes eines Satzes von Punkten beruhen und sich nicht auf die eigentliche Position im Rhinoraum beziehen. Deshalb ergibt sich, wenn der einzige Unterschied zwischen zwei Polygonnetzen eine bestimmte dreidimensionale Position von Punkten ist, die durch den Nutzer definert werden, dann sind die beiden Polygonnetze als "homoeomorphisch"zu betrachten (topologisch equivalent) und teilen deshalb alle topologischen Eigenschaften.

![IMAGE - homeomorphic alphabet](images/1-6-2/04_Alphabet_homeo.png)
>Ein Beispiel von Homoeomorphismus sind Buchstaben (merke, dass einige der homoeomorphen Gruppen oberhalb sich dadurch unterscheiden, welche Schriftart sie nutzen).

![IMAGE](images/1-6-2/05_Mug_and_Torus_morph.gif)
>Topologisch equivalente Schale und Donut 
 
#### 1.6.2.2 Polygonnetzcharakteristika

**Orientierbar**

Ein Polygonnetz wird als *orientierbar* betrachtet, wenn es wohldefinierte Seiten aufweist. Ein einfaches Beispiel eines nicht orientierbaren Polygonnetzes ergibt sich, wenn nebeneinander liegende Normalen in entgegengesetzte Richtungen zeigen. Diese "umgekehrten Oberflächen" können Probleme in der Visualisierung und beim Rendern darstellen, sowie bei der Fertigung von 3D-Drucken bereiten.

![IMAGE](images/1-6-2/06_orientable.png)
>1. Eine orientierbare Fläche mit Netzflächennormalen, die in dieselbe Richtung deuten
2. Eine nicht orientierbare Fläche hat angrenzende Normalen, die in verschiedene Richtungen deuten. 

**Open vs Closed**

Es ist oftmals notwendig zu wissen, ob ein Polygonnetz ein *geschlossenes* Polygonnetz ist, das einen Körper beschreibt, oder ein *offenes* Polygonnetz, das lediglich eine 2D Fläche darstellt. Der Unterschied kann Imperativ bezüglich der Herstellbarkeit sein. Du kannst keine einzelne Fläche ohne Dicke 3D drucken, sondern musst dem Polygonnetz zusätzlich eine Dicke geben, sodass es ein Körper wird. Polygonnetzkörper sind auch Voraussetzung für boolsche Operationen (die im nachfolgenden Abschnitt behandelt werden).

Die **Mesh Edges** Komponente kann genutzt werden, um dies zu bestimmen. Wenn keine der Kanten des Polygonnetzes eine Valenz von 1 hat (wenn der E1 Ausgabeparameter *null* ausgibt), dann wissen wir, dass alle Kanten 'innenliegende Kanten' sind und das Polygonnetz keine äußere Begrenzungskante hat, also ein geschlossenes Polygonnetz ist.

Auf der anderen Seite, wenn es 'offene Kanten' gibt, muss es sich um die Begrenzung des Polygonnetzes handeln und das Polygonnetz ist nicht geschlossen.

![IMAGE](images/1-6-2/07_open-closed.png)
>1. Ein geschlossenes Polygonnetz. Alle Kanten sind mit genau zwei Netzflächen benachbart.
2. Ein offenes Polygonnetz. Die weißen Kanten grenzen nur an eine Netzfläche an.

**Mannigfaltig oder Nicht-Mannigfaltig**

Nicht-mannigfaltige Geometrien sind essentielle Geometrien, die nicht in der "realen Welt" existieren können. Das bedeutet nicht notwendigerweise, dass sie "schlechte Geometrie" erzeugen, aber dass man darauf achten muss, dass es Schwierigkeiten für Werkzeuge und Operationen bedeuten kann (z.B.: das Rendern von lichbrechenden Effekten, Fluidsimulationen, boolsche Operationen, 3D Druck). Häufige Bedingungen, die in nicht-mannigfaltigen Polygonnetzen resultieren, beinhalten: Selbstverschneidung, offene Kanten (von Löchern oder innenliegenden Netzflächen), unverbundene Topologie und überlappende/duplizierte Flächen. Ein Polygonnetz kann auch als *mannigfaltig* betrachtet werden, wenn es Eckpunkte beinhaltet, die von Netzflächen geteilt werden, die keine Kanten miteinander teilen oder deren Valenz größer als 2 ist und somit Verbindung mit mindestens drei Netzflächen herstellen.

![IMAGE](images/1-6-2/08_non-manifold.png)
>1. Ein einfaches mannigfaltiges Polygonnetz
2. Drei Netzflächen treffen sich in einer einzelnen Kante und sind nicht-mannigfaltig, stellen also eine T-Verbindung her
3. Zwei Netzflächen treffen sich in einem Punkt, aber teilen keine Kante und sind deshalb nicht-mannigfaltig

 
#### 1.6.2.3 Polygonnetze oder NURBS

Inwiefern sind Polygonnetzgeometrien unterschiedlich von NURBS Geometrien? Wann ist es besser die eine oder die andere zu nutzen?

#####Parametrisierung
In einem früheren Kapitel haben wir gesehen, dass NURBS Flächen durch eine Serie von NURBS Kurven in beiden Richtungen definiert sind. Diese Richtungen sind mit U und V benannt und ermöglichen eine NURBS Fläche entsprechend einer zweidimensionalen Domäne zu parametrisieren. Die Kurven selbst werden als Gleichungen im Computer gespeichert, wodurch die resultierende Fläche mit beliebiger Präzision berechnet werden kann. Das Verbinden zweier NURBS Flächen wird in einer Polyfläche resultieren, in der verschiedene Schnitte der Geometrie verschiedene UV Parameter und Kurvendefinitionen haben werden.

Polygonnetze auf der anderen Seite werden durch eine konkrete Anzahl von genau definierten Eckpunkten und Netzflächen bestimmt. Das Netzwerk von Eckpunkten wird generell nicht mit einfachen UV Koordinaten beschrieben werden können. Die Darstellungspräzision kann nun nur durch Verfeinerung des Polygonnetzes oder das Hinzufügen weiterer Netzflächen verbessert werden, weil die Netzflächen die Darstellungspräzision durch ihre Darstellung klar definieren. Das Fehlen von UV Koordinaten jedoch ermöglicht es, Polygonnetze komplizierterer Geometrie flexibel in einem Polygonnetz handzuhaben, statt wie beim Fall der NURBS Darstellung auf eine Polyfläche zurückgreifen zu müssen.

>Anmerkung - Während ein Polygonnetz keine implizite UV Parametrisierung hat, ist es manchmal sinnvoll eine solche Parametrisierung anzuwenden, um eine Textur oder ein Bild auf eine Polygonnetzgeometie anzuwenden, um sie zu rendern. Manche Modellierungsprogramme haben deshalb die Möglichkeit UV Koordinaten für Polygonnetze als *Attribute* (ähnlich wie Eckpunktfarben) den Eckpunkten zuzuweisen, die dann bearbeitet und verändert werden können. Diese sind normalerweise zugewiesen und werden nicht durch das Polygonnetz selbst bestimmt.

##### Lokale und globale Einflüsse

Ein wichtiger Unterschied ist der Umfang, in welchem lokale Veränderungen in einem Polygonnetz oder einer NURBS Geometie die Gesamtform beeinflussen. Polygonnetzgeometien sind komplett lokal. Einen Eckpunkt zu bewegen beeinflusst lediglich angrenzende Netzflächen. Bei NURBS Flächen wird der Umfang des Einflusses einer Veränderung komplizierter und hängt vom Grad der Fläche und den Gewichtungen und Knoten der Kontrollpunkte ab. Generell jedoch wird die Bewegung eines einzelnen Kontrollpunktes einer NURBS Fläche eine globalere Veränderung der Geometrie bedeuten.

![IMAGE](images/1-6-2/09_NURBSvsMESH-02.jpg)
>1. NURBS Flächen - die Veränderung eines Kontrollpunktes hat globale Wirkung
2. Polygonnetzgeometrie - die Bewegung eines Eckpunktes hat lokalen Einfluss

Eine Analogie, die hier hilfreich ist, ist der Vergleich einer Vektorgrafik (bestehend aus Linien und Kurven) mit einem Rasterbild (bestehend aus individuellen Punkten). Wenn Du auf ein Vektorbild zoomst, werden die Kurven scharf und klar bleiben, während die Vergrößerung eines Rasterbildes in der Ansicht individueller Pixel enden wird. In dieser Analogie kann eine Vektorgraphik mit einer NURBS Fläche verglichen werden, während sich ein Polygonnetz wie ein Rasterbild verhält.

![IMAGE](images/1-6-2/10_vector raster analogy.png)
>Vergrößerung einer NURBS Fläche erhält die geglättete Kurve, während das Polygonnetzelement eine feste Auflösung hat

Es ist interessant festzustellen, dass, während NURBS Flächen als mathematische Gleichungen gespeichert werden, die letztendliche Darstellung der Flächen Polygonnetze benötigt. Es ist nicht möglich in einem Computer eine kontinuierliche Gleichung darzustellen. Stattdessen muss er die Gleichungen in kleinere Teile herunterbrechen, was darin resultiert, dass für jede Render- und Darstellungsaktioen ein Polygonnetz der entsprechenden NURBS Fläche berechnet werden muss. In unserer Analogie können wir sehen, dass der Computer, auch wenn er die Gleichung einer Kurve speichern kann, diese in eine Serie von diskreten Pixeln auf dem Bildschirm umwandeln muss, um sie darzustellen. 

#### 1.6.2.4 Vor- und Nachteile von Polygonnetzen

Wenn wir uns fragen: "Was sind die Vor- und Nachteile der Modellierung mit Polygonnetzen?" müssen wir uns eigentlich fragen "Was sind die Vor- und Nachteile einer Modellierung mit Formen, die nur durch eine Menge von Eckpunkten und dem entsprechenden topologischen Netzwerk bestimmt werden?". Durch diese Methode der Rahmung der Frage ist es einfacher zu sehen, wie die "einfache" Natur von Polygonnetzen der ausschlaggebende Aspekt für die Bevorzugung einer Modellierung in dieser Technik ist, abhängig vom Kontext der entsprechenden Anwendung.

Polygonnetze können in einer Situation von Vorteil sein, in der:

- Das dynamische Rendering einer Formveränderung ohne Veränderung der Topologie angestrebt wird
- Eine diskrete Annäherung einer gerundeten Geometrie ausreichend ist
- Eine Geometrie niedrigerer Auflösung systematisch geglättet (oder artikuliert) wird, indem computerbasierte Methoden angewendet werden, um eine höhere Auflösung zu erzielen
- Wenn das niedrig aufgelöste Modell gleichzeitig hohe Auflösung im Detail unterstützen muss

Polygonnetze können in folgenden Situationen von Nachteil sein:

- Wenn Krümmung und Glättung mit einem hohen Level an Präzision dargestellt werden müssen
- Wahre Ableitungen berechnet werden müssen
- Die Geometrie in einen Körper für industrielle Produktion umgewandelt werden muss
- Die finale Form einfache Veränderungen zulassen soll

 



