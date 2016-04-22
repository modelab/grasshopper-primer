### 1.4.6. Listen Managen
{% if gitbook.generator == "pdf" or "mobi" or "epub" %}
>Beispiele zu diesem Abschnitt: [http://grasshopperprimer.com/appendix/A-2/1_gh-files.html](http://grasshopperprimer.com/appendix/A-2/1_gh-files.html)
{% else %}
>Beispiele zu diesem Abschnitt: [Download](../../appendix/A-2/gh-files/1.4.6_list management.gh)
{% endif %}

#####Eine der maechtigsten Eigenschaften von Grasshopper ist die Moeglichkeit schnell Listen zu erstellen und zu bearbeiten. Wir speichern viele verschiedene Datentypen in einer Liste (Nummern, Punkte, Vektoren, Kurven, Flaechen, Breps, usw.) und es gibt eine Menge nuetzlicher Werzeuge hierfuer unter der "Sets/List" Unterkategorie.

####1.4.6.1. LISTENLAENGE
Die "List Length" Komponente (Sets/List/List Length) misst grundsaetzlich die Laenge einer Liste. Da unsere Listen immer bei null beginnen, ist der hoechste moegliche Wert unseres Indexes einer Liste gleich der Laenge der Liste minus eins. In diesem Beispiel haben wir unsere Ausgangsliste mit dem L Eingabeparameter der "List Length" Komponente verbunden, um zu zeigen, dass in der Liste 6 Eintraege vorhanden sind.

![IMAGE](images/1-4-6/1-4-6_001-list-length.png)

##>#1.4.6.2. LISTENELEMENTE
Unsere Liste wird mit einer "List Item" Komponente (Sets/List/List Item) verbunden, um einen bestimmten Eintrag aus der Liste zu erhalten. Wenn wir auf ein individuelles Element einer Liste zugreifen wollen, muessen wir den i Eingabeparameter bestimmen; welcher mit dem Index uebereinstimmt, auf den wir zugreifen wollen. Wir koennen einen einzelnen Integerwert oder eine Liste von Integerwerten in den i Eingabeparameter eingeben, abhaengig davon, welche Elemente wir erhalten wollen. Der L Eingabeparameter definiert die Ausgangsliste, die wir analzsieren wollen. In diesem Beispiel haben wir den i Eingabeparameter mit 5.0 angegeben, so dass die "List Item" Komponente uns die Daten, die mit dem fuenften Eintrag der Liste verknuepft sind, ausgibt.

![IMAGE](images/1-4-6/1-4-6_002-list-item.png)

####1.4.6.3. LISTEN UMKEHREN
Wir koennen eine Liste in ihrer Reihenfolge umkehren, indem wir die "Reverse List" Komponente (Sets/List/Reverse) anwenden. Wenn wir eine aufsteigende Liste mit Zahlen von 0.0 bis 9.0 in die "Reverse List" Komponente eingeben, gibt uns der Ausgabeparameter eine absteigende Liste von 9.0 bis 0.0 zurueck.

![IMAGE](images/1-4-6/1-4-6_003-reverse-list.png)

####1.4.6.4. VERSCHIEBEN VON LISTEN
Die "Shift List" Komponente (Sets/Sequence/Shift List) wird die Reihenfolge der Liste nach oben oder unten verschieben, je nachdem welchen Wert wir fuer die Verschiebung angeben. Wir habn den Ausgabeparameter der Liste mit dem L Eingabeparameter der "Shift List" Komponente verbunden, waehrend wir eine Zahl mit dem S Eingabeparameter verknuepfen. Wenn wir die Verschiebung mit -1 angeben, werden alle Werte in der Liste um einen Eintrag nach unten verschoben. Ebenso werden alle Werte in der Liste um einen Eintrag nach oben verschoben, wenn wir die Verschiebung mit +1 angeben. In diesem Beispiel haben wir die Verschiebung mit +1 festgelegt, so dass unsere Leiste um einen Eintrag nach oben verschoben wird. Wenn wir den "Wrap" Wert auf "false" stellen, wird der letzte Eintrag nach oben verschoben und aus der Liste fallen, was den Wert grundsaetzlich aus der Liste entfernt (so dass die Laenge der Liste sich um eins reduziert). Jedoch, wenn wir den "Warp" wert auf "true" setzen, wird der letzte Eintrag der Liste wieder unten an der Liste angefuegt.

![IMAGE](images/1-4-6/1-4-6_004-shift-list.png)

####1.4.6.5. ELEMENTE EINFUEGEN
Die "Insert Items" Komponente (Sets/Lists/Insert Items) ermoeglicht es eine Menge an Werten in eine Liste einzufuegen. Damit dies anstaendig funktioniert, muessen wir fuer jedes Element wissen, welche Elemente wir an welcher Indexposisiton einfuegen wollen. Im unteren Beispiel werden wir die Buchstaben A, B und C an die Indexposition drei einfuegen.
![IMAGE](images/1-4-6/1-4-6_005-insert-item.png)

####1.4.6.6. WEBEN
Die "Weave" Komponente (Sets/Lists/Weave) fuehrt zwei Listen basierend auf einem Webemuster (P Eingabeparameter) zusammen. Wenn das Muster und die Datenstroeme nicht perfekt aufeinander abgebildet werden koennen, wird die Komponente entweder "null" Werte in die Eingabestroeme einfuegen, oder sie kann Stroeme ignorieren, die noch nicht erschoepft wurden.

![IMAGE](images/1-4-6/1-4-6_006-weave.png)

####1.4.6.7. AUSSORTIEREN MIT MUSTER
Die "Cull" Komponente (Sets/Sequence/Cull Pattern) entfernt Elemente einer Liste mit einer sich wiederholenden Maske. Die Maske ist definiert als eine Liste boolscher Werte (wahr oder falsch). Die Maske wird wiederholt, bis alle Elemente der Datenliste ausgewertet wurden.

![IMAGE](images/1-4-6/1-4-6_007-cull-pattern.png)

