###1.3.5. Boolsche & Logische Operatoren
{% if gitbook.generator == "pdf" or "mobi" or "epub" %}
>Beispieldateien zu diesem Abschnitt: [http://grasshopperprimer.com/appendix/A-2/1_gh-files.html](http://grasshopperprimer.com/appendix/A-2/1_gh-files.html)
{% else %}
>Beispieldateien zu diesem Abschnitt: [Download](../../appendix/A-2/gh-files/1.3.5_booleans and logical operators.gh)
{% endif %}

####1.3.5.1. BOOLSCHE OPERATOREN
Numerische Variablen können eine ganze Bandbreite verschiedener Zahlen speichern. Boolsche Variablen können lediglich zwei Werte speichern, auf die wir uns mit Ja und Nein, Wahr und Falsch oder 1 und 0 beziehen. Offensichtlich werden wir niemals boolsche Werte heranziehen um Kalkulationen durchzuführen, da ihre Werte so begrenzt sind. Wir nutzen boolsche Werte um Konditionale auszuwerten.

![](images/1-3-5/1-3-5_001-boolean-parameter.png)
>Boolsche Parameter

In Grasshopper werden boolsche Werte auf verschiedene Arten genutzt. Der boolsche Parameter ist ein Container für einzelne oder mehrere boolsche Werte, während der "Boolean Toggle" es ermöglicht schnell zwischen einzelnen Werten für wahr und falsch umzuschalten.

![](images/1-3-5/1-3-5_002-boolean-toggle.png)
>Boolean Toggle - doppelklicke um den boolschen Wert des Schalters zwischen wahr und falsch umzuschalten

Grasshopper hat auch Objekte mit denen Konditionale getestet werden können und deren Ausgabe boolsche Werte sind. Beispielsweise die "Includes" Komponente erlaubt es einen numerischen Wert auf seine Präsenz in einer Domäne zu testen.

![](images/1-3-5/1-3-5_003-includes.png)
>Die "Includes" Komponente testet ob die Zahl 6.8 in einer Domäne von 0 bis 10 enthalten ist. Sie gibt einen boolschen Wert für wahr zurück.

####1.3.5.2. LOGISCHE OPERATOREN
Logische Operatoren arbeiten meistens mit boolschen Werten und sie sind wirklich ziemlich logisch. Wie Du Dich erinnern kannst, können boolsche Werte zur zwei verschiedene Werte annehmen. Die boolsche Mathematic wurde von George Boole (1815-1864) entwickelt und ist heute Kernbestandteil der gesamten digitalen Industrie. Boolsche Algebra liefert uns die Werkzeuge mit welchen wir Datensätze analysieren, vergleichen und beschreiben können. Obwohl Boole ursprünglich sechs boolsche Operatoren beschrieb, werden wir nur drei davon genauer unter die Lupe nehmen:

1. Not
2. And
3. Or

Der Not Operator ist eine Seltsamkeit unter den Operatoren, da er keine zwei Eingabewerte benötigt. Stattdessen invertiert er einfach den Wert, den er bekommt. Stell Dir vor wir haben ein Skript, welches die Existenz von einer Menge Blockdefinitionen in Rhino überprüft. Wenn eine Blockdefinition nicht existiert, wollen wir den Nutzer informieren und das Skript abbrechen.

![](images/1-3-5/1-3-5_004-not.png)
>Der Grasshopper Not Operator (Gate)

"And" und "or" nehmen jeweils zwei Argumente. Der "and" Operator wertet als "wahr" aus, wenn beide eingegebenen Argumente "wahr" sind. Der "or" Operator ist schon damit glücklich, wenn ein einzelner Wert "wahr" ist.

Wie Du sehen kannst, ist das Problem mit den logischen Operatoren nicht die Theorie, sondern was passiert wenn Du eine Menge davon benötigst um etwas auszuwerten. Sobald man sie zusammenstrickt, hat man schnell einen unübersichtlichen Code; nicht davon zu sprechen, wenn man festlegen muss, welcher Operator Vorrang hat.

![](images/1-3-5/1-3-5_005-and.png)
>Der Grasshopper And Operator (gate)

![](images/1-3-5/1-3-5_006-or.png)
>Der Grasshopper Or Operator (gate)

Ein guter Weg um Deine eigene boolsche Logik zu trainieren ist die Verwendung von Venn Diagramme. Ein Venn Diagramm ist eine graphische Repräsentation einer boolschen Menge, in der jede Region eine Untermenge von Werten enthält, die eine gemeinsame Eigenschaft miteinander teilen. Das berühmteste ist das Drei-Kreis-Diagramm:

![](images/1-3-5/1-3-5_007-venn-diagram.png)

Jede Kreisregion enthält alle Werte, die zu einer Menge gehören; der obere Kreis zum Beispiel beschreibt eine Menge {A}. Jeder Wert innerhalb des Kreises wird für {A} als "wahr" ausgewertet und jeder Wert ausserhalb wird für {A} als "falsch" ausgewertet. Indem die Regionen eingefärbt werden, können wir die boolsche Auswertung in programmiertem Code nachahmen:

![](images/1-3-5/1-3-5_008-venn-diagram-examples.png)
