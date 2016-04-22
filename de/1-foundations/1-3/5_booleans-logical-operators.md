###1.3.5. Boolsche & Logische Operatoren
>Beispieldateien zu diesem Abschnitt: [http://grasshopperprimer.com/appendix/A-2/1_gh-files.html](http://grasshopperprimer.com/appendix/A-2/1_gh-files.html)

####1.3.5.1. BOOLSCHE OPERATOREN
Nummerische variablen koennen eine ganze Bandbreite verschiedener Zahlen speichern. Boolsche Variablen koennen lediglich zwei Werte speichern auf die wir uns mit die Ja und Nein, Wahr und Falsch oder 1 und 0 beziehen. Offensichtlich werden wir niemals boolsche Werte heranziehen um Kalkulationen durchzufuehren, da ihre Werte so begrenztsind. Wir nutzen boolsche Werte um Konditionale auszuwerten.

![](images/1-3-5/1-3-5_001-boolean-parameter.png)
>Boolsche Parameter

In Grasshopper werden boolsche Werte auf verschiedene Arten genutzt. Der boolsche Parameter ist ein Container fuer einzelne oder mehrere boolsche Werte, waehrend der "Boolean Toggle" ermoeglicht es schnell zeischen einzelnen Werten fuer wahr und falsch umzuschalten.

![](images/1-3-5/1-3-5_002-boolean-toggle.png)
>Boolean Toggle - doppelklicke um den boolschen Wert des Schalters zwischen wahr und falsch umzuschalten

Grasshopper hat auch Objekte mit denen Konditionale getestet werden koennen und deren Ausgabe boolsche Werte sind. Beispielsweise die "Includes" Komponente erlaubt es einen nummerischen Wert auf seine Praesenz in einer Domaene zu testen.

![](images/1-3-5/1-3-5_003-includes.png)
>Die "Includes" Komponente testet ob die Zahl 6.8 in einer Domaene von 0 bis 10 enthalten ist. Sie gibt einen boolschen Wert fuer wahr zurueck.

####1.3.5.2. LOGISCHE OPERATOREN
Logische Operatoren arbeiten meistens mit boolschen Werten und sie sind wirklich ziemlich logisch. Wie Du Dich erinnern kannst, koennen boolsche Werte zur zwei verschiedene Werte annehmen. Die boolsche Mathematic wurde von George Boole (1815-1864) entwickelt und ist heute Kernbestandteil der gesamten digitalen Industrie. Boolsche Algebra liefert uns die Werkzeuge mit welchen wir Datensaetze analysieren, vergleichen und beschreiben koennen. Obwohl Boole urspruenglich sechs boolsche Operatoren beschrieb, werden wir nur drei davon genauer unter die Lupe nehmen:

1. Not
2. And
3. Or

Der Not Operator ist eine Seltsamkeit unter den Operatoren, da er keine zwei Eingabewerte benoetigt. Stattdessen invertiert er einfach den Wert, den er bekommt. Stell Dir vor wir haben ein Skript, welches die Existenz von einer Menge Blockdefinitionen in Rhino ueberprueft. Wenn eine Blockdefinition nicht existiert, wollen wir den Nutzer informieren und das Skript abbrechen.

![](images/1-3-5/1-3-5_004-not.png)
>Der Grasshopper Not Operator (Gate)

"And" und "or" nehmen jeweils zwei Argumente. Der "and" Operator wertet als "wahr" aus, wenn beide eingegebenen Argumente "wahr" sind. Der "or" Operator ist schon damit gluecklich, wenn ein einzelner Wert "wahr" ist.

Wie Du sehen kannst, ist das Problem mit den logischen Operatoren nicht die Theorie, sondern was passiert wenn Du eine Menge davon benoetigst um etwas auszuwerten. Sobold man sie zusammenstrickt, hat man schnell einen unuebersichtlichen Code; nicht davon zu sprechen, wenn man festlegen muss, welcher Operator Vorrang hat.

![](images/1-3-5/1-3-5_005-and.png)
>Der Grasshopper And Operator (gate)

![](images/1-3-5/1-3-5_006-or.png)
>Der Grasshopper Or Operator (gate)

Ein guter Weg um Deine eigene boolsche Logik zu trainieren ist die Verwendung von Venn Diagramme. Ein Venn Diagramm ist eine graphische Repraesentation einer boolschen Menge, in der jede Regin eine Untermenge von Werten enthaelt, die eine gemeinsame Eigenschaft miteinander teilen. das beruehteste ist das Drei-Kreis-Diagramm:

![](images/1-3-5/1-3-5_007-venn-diagram.png)

Jede Kreisregion enthaelt alle Werte, die zu einer Menge gehoeren; der obere Kreis zum Beispiel beschreibt eine Menge {A}. Jeder Wert innerhalb des Kreises wird fuer {A} als "wahr" ausgewertet und jeder Wert ausserhalb wird fuer {A} als "falsch"ausgewertet. Indem die Regionen eingefaerbt werden, koennen wir die boolsche Auswertung in programmiertem Code nachahmen:

![](images/1-3-5/1-3-5_008-venn-diagram-examples.png)
