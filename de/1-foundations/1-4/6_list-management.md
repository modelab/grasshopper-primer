### 1.4.6. Listen Managen
{% if gitbook.generator == "pdf" or "mobi" or "epub" %}
>Beispiele zu diesem Abschnitt: [http://grasshopperprimer.com/appendix/A-2/1_gh-files.html](http://grasshopperprimer.com/appendix/A-2/1_gh-files.html)
{% else %}
>Beispiele zu diesem Abschnitt: [Download](../../appendix/A-2/gh-files/1.4.6_list management.gh)
{% endif %}

##### Eine der mächtigsten Eigenschaften von Grasshopper ist die Möglichkeit schnell Listen zu erstellen und zu bearbeiten. Wir speichern viele verschiedene Datentypen in einer Liste (Nummern, Punkte, Vektoren, Kurven, Flächen, Breps, usw.) und es gibt eine Menge nützlicher Werzeuge hierfür unter der "Sets/List" Unterkategorie.

#### 1.4.6.1. LISTENLÄNGE
Die "List Length" Komponente (Sets/List/List Length) misst grundsätzlich die Länge einer Liste. Da unsere Listen immer bei null beginnen, ist der höchste mögliche Wert unseres Indexes einer Liste gleich der Länge der Liste minus eins. In diesem Beispiel haben wir unsere Ausgangsliste mit dem L Eingabeparameter der "List Length" Komponente verbunden, um zu zeigen, dass in der Liste 6 Einträge vorhanden sind.

![IMAGE](images/1-4-6/1-4-6_001-list-length.png)

#### 1.4.6.2. LISTENELEMENTE
Unsere Liste wird mit einer "List Item" Komponente (Sets/List/List Item) verbunden, um einen bestimmten Eintrag aus der Liste zu erhalten. Wenn wir auf ein individuelles Element einer Liste zugreifen wollen, muessen wir den i Eingabeparameter bestimmen; welcher mit dem Index übereinstimmt, auf den wir zugreifen wollen. Wir können einen einzelnen Integerwert oder eine Liste von Integerwerten in den i Eingabeparameter eingeben, abhängig davon, welche Elemente wir erhalten wollen. Der L Eingabeparameter definiert die Ausgangsliste, die wir analysieren wollen. In diesem Beispiel haben wir den i Eingabeparameter mit 5.0 angegeben, so dass die "List Item" Komponente uns die Daten, die mit dem fünften Eintrag der Liste verknüpft sind, ausgibt.

![IMAGE](images/1-4-6/1-4-6_002-list-item.png)

#### 1.4.6.3. LISTEN UMKEHREN
Wir können eine Liste in ihrer Reihenfolge umkehren, indem wir die "Reverse List" Komponente (Sets/List/Reverse) anwenden. Wenn wir eine aufsteigende Liste mit Zahlen von 0.0 bis 9.0 in die "Reverse List" Komponente eingeben, gibt uns der Ausgabeparameter eine absteigende Liste von 9.0 bis 0.0 zurück.

![IMAGE](images/1-4-6/1-4-6_003-reverse-list.png)

#### 1.4.6.4. VERSCHIEBEN VON LISTEN
Die "Shift List" Komponente (Sets/Sequence/Shift List) wird die Reihenfolge der Liste nach oben oder unten verschieben, je nachdem welchen Wert wir für die Verschiebung angeben. Wir habn den Ausgabeparameter der Liste mit dem L Eingabeparameter der "Shift List" Komponente verbunden, während wir eine Zahl mit dem S Eingabeparameter verknüpfen. Wenn wir die Verschiebung mit -1 angeben, werden alle Werte in der Liste um einen Eintrag nach unten verschoben. Ebenso werden alle Werte in der Liste um einen Eintrag nach oben verschoben, wenn wir die Verschiebung mit +1 angeben. In diesem Beispiel haben wir die Verschiebung mit +1 festgelegt, so dass unsere Leiste um einen Eintrag nach oben verschoben wird. Wenn wir den "Wrap" Wert auf "false" stellen, wird der letzte Eintrag nach oben verschoben und aus der Liste fallen, was den Wert grundsätzlich aus der Liste entfernt (so dass die Länge der Liste sich um eins reduziert). Jedoch, wenn wir den "Wrap" Wert auf "true" setzen, wird der letzte Eintrag der Liste wieder unten an der Liste angefügt.

![IMAGE](images/1-4-6/1-4-6_004-shift-list.png)

#### 1.4.6.5. ELEMENTE EINFÜGEN
Die "Insert Items" Komponente (Sets/Lists/Insert Items) ermöglicht es eine Menge an Werten in eine Liste einzufügen. Damit dies anständig funktioniert, müssen wir für jedes Element wissen, welche Elemente wir an welcher Indexposition einfügen wollen. Im unteren Beispiel werden wir die Buchstaben A, B und C an die Indexposition drei einfügen.
![IMAGE](images/1-4-6/1-4-6_005-insert-item.png)

#### 1.4.6.6. WEBEN
Die "Weave" Komponente (Sets/Lists/Weave) führt zwei Listen basierend auf einem Webemuster (P Eingabeparameter) zusammen. Wenn das Muster und die Datenströme nicht perfekt aufeinander abgebildet werden können, wird die Komponente entweder "null" Werte in die Eingabeströme einfügen, oder sie kann Ströme ignorieren, die noch nicht erschöpft wurden.

![IMAGE](images/1-4-6/1-4-6_006-weave.png)

#### 1.4.6.7. AUSSORTIEREN MIT MUSTER
Die "Cull" Komponente (Sets/Sequence/Cull Pattern) entfernt Elemente einer Liste mit einer sich wiederholenden Maske. Die Maske ist definiert als eine Liste boolscher Werte (wahr oder falsch). Die Maske wird wiederholt, bis alle Elemente der Datenliste ausgewertet wurden.

![IMAGE](images/1-4-6/1-4-6_007-cull-pattern.png)

