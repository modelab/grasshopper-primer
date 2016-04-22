### 1.5.2. Was ist ein Datenbaum?

#####Ein Datenbaum ist einen hierarchische Struktur zur Speicherung von Daten in einer verschachtelten Liste. Datenbaeume werden erstellt, wenn Grasshopperkomponenten so strukturiert sind, dass sie einen Datensatz als Eingabe annehmen und mehrere Datensaetze ausgeben. Grasshopper behandet diese neuen Daten, indem es sie in Form von Unterlisten verschachtelt. diese verschachtelten Unterlisten verhalten sich in der selben weise wie Ordnerstrukturen auf Deinem Computer, indem sie den Zugriff auf indizierte Elemente durch eine Pfadnavigation ermoeglichen. Diese wird bestimmt durch die Erzeugung von Elternlisten und den entsprecheden Unterindizes.

Es ist moeglich mehrere Datenlisten in einem einzelnen Parameter zu speichern. Da mehrere Listen verfuegbar werden, benoetigen wir eine Moeglichkeit die individuellen Listen zu identifizieren. Ein Datenbaum ist essentiell fuer die Navigation von Listen von Listen oder manchmal auch Listen von Listen von Listen (usw.).

![IMAGE](images/1-5-2/1-5-2_001-data-tree.png)

In dem oberhalb dargestellten Bild befindet sich ein einzelner Grundast (Du kannst diesen Stamm nennen, aber da es moeglich ist mehrere Grundaeste zu haben, hinkt dieser Vergleich etwas) auf dem Pfad {0}. Dieser Pfad enthaelt keine Daten, hat aber 6 Unteraeste. Jeder dieser Unteraeste teilt den Index des Elternastes {0} und hat seinen eigenen Unterindex  (0, 1, 2, 3, 4, und 5 entsprechend). Es wuerde falsch sein diese "Index" zu nennen, da sich dieses Wort auf eine bestimmte Zahl bezieht. Es ist wahrscheinlich besser diese als Pfad zu beschreiben, da es die Idee der Ordnerstruktur auf dem Computer wiederspiegelt. An jedem dieser Unteraeste werden wir Daten vorfinden. Jedes Datenelement ist nun also Teil eines (und nur eines) Astes des Baums, und jedes Element hat einen spezifischen Index fuer seine Position innerhalb des Astes. Jeder Ast hat einen Pfad, der seine Position im Baum beschreibt.

Das Bild unterhalb illustriert den Unterschied zwischen Liste und Datenbaum. Aud der linken Seite wird eine Reihe von fuenf Spalten zu je sechs Punkten innerhalb einer Liste dargestellt. Die erste Spalte ist mit 0-5 nummeriert, die zweite mit 6-11, usw. Auf der rechten Seite ist die selbe Reihe  von Punkten in einem Datenbaum enthalten. Dieser Datenbaum ist ist eine Liste der vier Spalten und jede Spalte ist eine Liste von sechs Punkten. Der Index eines jeden Punktes ist (Spaltennummer, Zeilennummer). Dies ist ein viel nuetzlicherer Ansatz zur Organisation von Daten, weil Du einfacher auf die Daten von allen Punkten einer bestimmten Spalte oder Zeile zugreifen, jede zweite Reihe von Punkten loeschen, sich veraendernde Punkte verbinden kannst, uvm.

![IMAGE](images/1-5-2/1-5-2_002-list-data-tree.png)

####1.5.2.1. VISULISIERUNG VON DATENBAEUMEN
{% if gitbook.generator == "pdf" or "mobi" or "epub" %}
>Beispieldateien fuer diesen Abschnitt: [http://grasshopperprimer.com/appendix/A-2/1_gh-files.html](http://grasshopperprimer.com/appendix/A-2/1_gh-files.html)
{% else %}
>Beispieldateien fuer diesen Abschnitt: [Download](../../appendix/A-2/gh-files/1.5.2.1_data tree visualization.gh)
{% endif %}

Wegen der Komplexitaet koennen Datenbaume schwierig zu verstehen sein. Grasshopper hat einige Werkzeuge zur Visualisierung von in Baeumen gespeicherten Daten, um diese besser zu verstehen.

**The Param Viewer**
Der "Param Viewer" (Params/Util/Param Viewer) ermoeglicht es die Daten eines Baumes in Bild oder Text darzustellen. Verbinde einen Ausgabeparameter, der Daten enthaelt,mit dem Eingabeparameter des "Param Viewer". Um den Baum anzuzeigen, rechtsklicke auf den "Param Viewer" und waehle “Draw Tree" In disem Beispiel werden wir den "Param Viewer" mit dem Punkte (P) Ausgabeparameter der "Divide Curve" Komponente verbinden, der 10 Kurven jeweils in 10 Teile zerlegt.

![IMAGE](images/1-5-2/1-5-2_003-param-viewer.png)
>1. Pfad jeder Liste
2. Anzahl von Elementen in jeder Liste
3. Waehle "Draw Tree" um den Datenbaum darzustellen

Wenn wir ein Paneel mit dem selben Ausgabeparameter verbinden, zeigt es zehn Listen mit je elf Elementen an. Du kannst sehen, dass jedes Element ein Punkt ist, der durch drei Koordinaten beschrieben wird. Der Pfad wird an der Spitze einer jeden Liste angezeigt und entspricht dem Pfad der im "Param Viewer" aufgefuehrt ist.

![IMAGE](images/1-5-2/1-5-2_004-panel-display.png)
>1. Pfad
2. Liste mit 11 Elementen

**Baumstatistiken**
Die "Tree Statistics" Komponente (Sets/Tree/Tree Statistics) gibt einige Statistiken zu Datenbaeumen aus. Diese beinhalten:
* P - Alle Pfade des Baumes
* L - Die Laenge jedes Astes im Baum
* C - Anzahl der Pfade und Aeste in einem Baum

Wenn wir dem Punkt Ausgabeparameter der selben "Divide Curve" Komponente anschliessen, koennen wir die Pfade, die Laenge und die Anzahl der Pfade in einem Paneel darstellen. Diese Komponente ist hilfreich, da sie die Statistiken in drei Ausgabeparameter unterteilt, was es uns erlaubt nur die relevanten Daten darzustellen.

![IMAGE](images/1-5-2/1-5-2_005-tree-stats.png)

Der "Param Viewer" und die "Tree Statistics" Komponente sind beide hilfreich fuer die Visulisierung von Veraenderungen innerhalb der Struktur eines Datenbaums. Im naechsten Abschnitt werden wir uns die Operationen ansehen, die angewendet werden koennen um die Struktur von Baeumen zu veraendern.