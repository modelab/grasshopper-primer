### 1.2.3. DATENTYPEN

#####Die meisten Parameter können zwei verschiedene Arten von Daten speichern: Volatile und persistente Daten. Volatile Daten sind von einer oder mehreren Quellen eingespeist und werden zerstört (oder neuerhoben) wenn die Lösung erneut startet. Persistente Daten sind Daten, welche spezifisch vom Benutzer eingestellt werden.

####1.2.3.1. PERSISTENTE DATEN
Persistente Daten sind durch ein Menü, und abhängig von der Art des Parameters durch unterschiedliche Manager, zugänglich. Ein Punktparameter zum Beispiel ermöglicht es Dir einen oder mehrere Punkte durch sein Menü auszuwählen. Aber lass uns noch ein paar Schritte zurückgehen und sehen, wie sich ein Punktparameter so verhält.

Wenn Du einen Punktparameter vom "Params/Geometry Paneel" auf die Leinwand ziehst, ist der Parameter orange, was anzeigt, dass der Parameter eine Warnung enthält. Es ist nichts Ernstes, da die Warnung Dich einfach darüber informiert, dass der Parameter leer ist (er enthält keine persistenten Einträge und er konnte keine volatilen Daten empfangen) und deshalb keinen Effekt auf das Ergebnis der Lösung hat. Das Kontextmenu des Parameters bietet zwei Wege der Einstellung von persistenten Daten: einzelne oder mehrere. Rechtsklicke auf den Parameter um mehrere Punkte zu setzen. Sobald Du auf eines dieser Menuelemente klickst, wird das Grasshopperfenster verschwinden und Du wirst aufgefordert werden einen Punkt in einem der Rhinoansichtsfenster auszuwählen.

![IMAGE](images/1-2-3/1-2-3_001-set-multiple-points.png)

Sobald Du alle Punkte bestimmt hast, kannst Du Enter drücken und sie werden Bestandteil der persistenten Datensammlung des Parameters werden. Das bedeutet, dass der Parameter nicht mehr leer ist und seine Farbe von orange zu grau ändert. (Merke, dass der Informationsballon in der rechten oberen Ecke der Komponente ebenfalls verschwunden ist und keine Warnungen mehr vorhanden sind). An diesem Punkt kannst Du die gespeicherten Punkte in diesem Parameter für jede weitere folgende Eingabe in Deiner Definition verwenden.

![IMAGE](images/1-2-3/1-2-3_002-parameter-persistent-data.png)
>1. Der Parameter ist orange und zeigt damit an, dass er keine persistenten Dateneinträge enthält (und keine volatilen Daten empfangen hat) und somit keinen Effekt auf das Ergebnis der Lösung hat. Rechtsklicke auf einen beliebigen Parameter um persistente Daten auszuwählen.
2. Sobald der Parameter einige persistente Daten enthält, wird die Komponente ihre Farbe von orange zu grau ändern.
3. Der Werkzeugtipp für einen Punktparameter zeigt die persistenten Daten (eine Sammlung von Referenzpunkten), die gespeichert sind.

####1.2.3.2. VOLATILE DATEN
Volatile Daten, wie der Name schon nahelegt, sind nicht permanent und werden jedes Mal wenn die Lösung abgeschlossen ist gelöscht. Jedoch kann eine Begebenheit auslösen, dass die Lösung wieder aufgebaut und die Szene aktualisiert wird. Generell werden die meisten Daten, die während der Erzeugung der Lösung entstehen als volatil bezeichnet.

Wie bereits genannt, werden Grasshopperdaten in Parametern gespeichert (entweder in volatiler oder in persistenter Form) und in verschiedenen Komponenten genutzt. Wenn Daten nicht als permanente Daten in Parametern gespeichert werden, muss sie implizit aus einer anderen Quelle kommen. Jeder Parameter (ausser Ausgabeparameter) definiert woher er seine Daten bezieht und die meisten Parameter sind dabei nicht besonders spezifisch. Du kannst einen "Number"-Parameter (welche nur besagt, dass es sich um eine Dezimalzahl handelt) mit einem Integereingabeparameter verbinden und er wird sich um die Umwandlung kümmern.

Du kannst den Weg in dem Daten bezogen und gespeichert werden im Kontextmenü eines Parameters oder eines Komponenteneingabeparameters verändern. Um gespeicherte Referenzgeometrien aus Rhino in der Grasshopperdefinition selbst zu verändern, rechtsklicke auf den Parameter und wähle "Internalise Data" aus dem Menu. Dies ist hilfreich, wenn Deine Grasshopperdatei unabhängig von der referenzierten Rhinodatei werden soll.

Du kannst auch Daten in Komponenteneingabeparametern internalisieren. Sobald Du "Internalise Data" im Menü ausgewählt hast, werden alle Kabel von dem entsprechenden Eingabeparameter entfernt. Die Daten wurden von volatil zu persistent umgewandelt und werden im weiteren Verlauf nicht mehr aktualisiert.

Wenn Du willst, dass die Daten wieder volatil werden, kannst Du einfach wieder Kabel in den Eingabeparameter einstecken und die Werte werden automatisch ersetzt. Du kannst auch auf den Eingabeparameter rechtsklicken und "Extract parameter" wählen. Grasshopper wird einen Parameter erzeugen und ihn mit dem Eingabeparameter verbinden, der die Daten enthält.

![IMAGE](images/1-2-3/1-2-3_003-right-click.png)

####1.2.3.3. EINGABEPARAMETER
Grasshopper hat eine Bandbreite an Parametern, die Dir die Möglichkeit eröffnen, die Komponenteneingabeparameter mit den Daten zu verbinden und dadurch Kontrolle über die veränderlichen Ergebnisse in der Definition auszuüben. Diese Parameter verändern sich mit der entsprechenden Eingabe und erzeugen volatile Daten.

**Schieberegler**
Die Schieberegler ("number slider") sind die wichtigsten und am häufigsten genutzten Eingabeparameter. Sie erlauben es uns, Werte zwischen zwei Extremen auszugeben, indem wir mit einem Mausgriff interagieren. Schieberegler können benutzt werden, um einen bestimmten Wert zu spezifizieren und die Veränderung der Definition zu beobachten, die durch den Mausgriff erzeugt wird. Ein Schieberegler sollte jedoch auch als Mittel gesehen werden, um erfolgreich Wertegrenzen unserer Definition festzulegen.

![IMAGE](images/1-2-3/1-2-3_004-number-slider.png)
>1. Ziehe den Schieberegler um seinen Wert zu ändern - jedes Mal, wenn Du dies tust wird Grasshopper die Lösung erneut berechnen.
2. Rechtsklicke auf eine Schiebereglerkomponente um ihren Namen, Typ und Wert zu ändern.
3. Editierbares Textfeld für den Namen des Schiebereglers.
4. Wähle den Typ an Zahlen den der Schieberegler verwenden soll.
5. Verändere die Wertegrenzen des Schiebereglers.
6. Doppelklicke auf den Namen der Schiebereglerkomponente um den Schiebereglereditor zu öffnen.


**Graph mapper**
Der "Graph Mapper" ist eine zweidimensionale Benutzeroberfläche, mit der wir die numerischen Werte modifizieren können, indem wir die Eingabewerte an der x-Achse des Graphs antragen und die entsprechenden Funktionswerte entlang der y-Achse ausgeben. Er ist sehr nützlich, um einen Satz Werte innerhalb einer intuitiven, mausgriff-basierten Benutzeroberfläche modulieren zu können.


![IMAGE](images/1-2-3/1-2-3_005-graph-mapper-a.png)
>1. Bewege die Griffe um den Graph zu bearbeiten - jedes Mal, wenn Du dies tust, wird Grasshopper die Lösung neu berechnen.
2. Rechtsklicke die "Graph mapper" Kompenente, um den Graphtypen zu wählen.

![IMAGE](images/1-2-3/1-2-3_006-graph-mapper-b.png)
>1. Doppelklicke den "Graph mapper", um den Grapheditor zu öffnen.
2. Ändere die x- und y- Domäne.

**Value List**
Die Werteliste speichert eine Sammlung von Werten entlang einer entsprechenden Liste von Labels, zugewiesen durch ein Gleichheitssymbol. Sie ist im Besonderen hilfreich, wenn Du ein paar Möglichkeiten zur Auswahl haben willst, die entsprechend bedeutungsvoll benannt wurde, um bestimmte Ausgabewerte zur Verfügung zu haben.

![IMAGE](images/1-2-3/1-2-3_007-value-list.png)
>1. Rechtsklicke auf die Werteliste Komponente und wähle eine Option aus dem Menü.
2. Doppelklicke die Werteliste Komponente, um den Editor zu öffnen und Werte hinzuzufügen oder zu ändern.
3. Im Dropdownmodus klicke auf den Pfeil, um einen der Werte auszuwählen. Die Lösung wird jedes Mal neu berechnet, wenn Du den Wert änderst.
4. Im Checklistenmodus klicke neben die Werte, um sie auszuwählen. Die Komponente wird alle ausgewählten Werte ausgeben.
5. Im Wertesequenz- und Wertezyklusmodus, klicke die Pfeile nach links und rechts, um Dich durch die Werte zu bewegen.
