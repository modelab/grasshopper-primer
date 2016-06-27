<style>
td:nth-child(1) {color: #008DB2}
td:nth-child(3)	{font-size: 70%;width: 15%;}
td {background-color: #F9F9F9;}
thead {display: none}
</style>
### 1.4.7. MIT LISTEN ARBEITEN
{% if gitbook.generator == "pdf" or "mobi" or "epub" %}
>Beispieldateien zu diesem Abschnitt: [http://grasshopperprimer.com/appendix/A-2/1_gh-files.html](http://grasshopperprimer.com/appendix/A-2/1_gh-files.html)

{% else %}
>>Beispieldateien zu diesem Abschnitt: [Download](../../appendix/A-2/gh-files/1.4.7_working with lists.gh)

{% endif %}

Lass uns einen Blick auf ein Beispiel werfen, das die Komponenten des vorausgegangenen Abschnitts beinhaltet. In diesem Beispiel werden wir ein Fliesenmuster erzeugen, das durch die Abbildung von Geometrie auf ein Raster erzeugt wird. Das Muster wird durch die Nutzung der "List Item" Komponente erzeugt um die gewünschte Fliese aus einer Liste von Geometien zu beziehen.

![IMAGE](images/1-4-7/1-4-7_001-working-with-lists.png)
>1. Geometrie entsprechend Index 1
2. Geometrie entsprechend Index 0
3. Rechtwinkliges Raster

![IMAGE](images/1-4-7/1-4-7_002-mapping.png)
>1. Abbildungsmuster
2. Abgebildete Geometrie




||||
|--|--|--|
|01.| Beginne eine Rhinoceros Datei. ||
|02.| Erstelle zwei gleichgroße Quadrate.||
|03.| Erstelle verschiedene Geometrien innerhalb der beiden Quadrate.<br><blockquote>Im oben dargestellten Beispiel haben wir eine einfache Fläche mit einem Knick erstellt. Der Knick ist ausgerundet, um die Ausrichtung darzustellen und die Basis ist ausgerundet um die beiden Geometrien zu unterscheiden.</blockquote>||
|04.| Beginne eine neue Definition, drücke Strg+N (in Grasshopper).||
|05.| **Params/Geometry/Geometry** – Ziehe zwei **Geometry** Parameter auf die Leinwand.| [![IMAGE](images/1-4-7/1-4-7_003-geometry.png)](../../appendix/A-1/0_index-of-components.html#PGGeo)|
|06.| Rechtsklicke den ersten **Geometry** Parameter und wähle "Set one Geometry". Referenziere die erste Geometrie. ||
|07.| Rechtsklicke auf den zweiten **Geometry** Parameter und wähle "Set one Geometry". Wähle die zweite Geometrie, die Du referenzieren willst. <br><blockquote>Es ist möglich mehrere Geometrien in einem einzigen Parameter zu referenzieren, aber der Einfachkeit halber werden wir zwei verschiedene Parameterkomponenten benutzen.</blockquote>||
|08.| **Params/Geometry/Curve** – Ziehe zwei **Curve** Parameter auf die Leinwand.|[![IMAGE](images/1-4-7/1-4-7_004-curve.png)](../../appendix/A-1/0_index-of-components.html#PGCrv)|
|09.| Rechtsklicke den ersten **Curve** Parameter und wähle "Set one Curve". Wähle die erste Kurve, die Du referenzieren möchtest.||
|10.| Rechtsklicke den zweiten **Curve** Parameter und wähle "Set one Curve". Wähle die zweite Kurve, die Du referenzieren möchtest. <br><blockquote>Versichere Dich, dass die Geometrie und das Quadrat, welche Du auswählst, miteinander korrespondieren.</blockquote>||
|11.| **Vector/Grid/Rectangular** – Ziehe eine **Rectangular Grid** Komponente auf die Leinwand. |[![IMAGE](images/1-4-7/1-4-7_005-rectangular-grid.png)](../../appendix/A-1/0_index-of-components.html#VGRecGrid)|
|12.| **Params/Input/Slider** - Ziehe drei **Number Sliders** auf die Leinwand||
|13.| Doppelklicke auf den ersten **Number Slider** und setze folgende Werte:<ul>Rounding: Integers<br>Lower Limit: 0<br>Upper Limit: 10<br>Value: 10 </ul>||
|14.| Doppelklicke auf den zweiten **Number Slider** und setze folgende Werte:<ul>Rounding: Integers<br>Lower Limit: 0<br>Upper Limit: 10<br>Value: 10 </ul>||
|15.| Doppelklicke den dritten **Number Slider** und setze folgende Werte:<ul>Name: Extents X & Y<br>Rounding: Integers<br>Lower Limit: 0<br>Upper Limit: 10<br>Value: 10 </ul>||
|16.| Verbinde den ersten **Number Slider** mit dem Größe X (Sx) Eingabeparameter der **Rectangular Grid** Komponente.||
|17.| Verbinde den zweiten **Number Slider** mit dem Größe Y (Sy) Eingabeparameter der **Rectangular Grid** component.||
|18.| Verbinde den dritten **Number Slider** mit dem Abmessung X (Ex) Eingabeparameter und dem Abmessung Y (Ey) Eingabeparameter der **Rectangular Grid** Komponente.|||

![IMAGE](images/1-4-7/1-4-7_006-definition-1.png)

||||
|--|--|--|
|19.| **Sets/Tree/Merge** – Ziehe zwei **Merge** Komponenten auf die Leinwand.|[![IMAGE](images/1-4-7/1-4-7_007-merge.png)](../../appendix/A-1/0_index-of-components.html#STMerge)|
|20.| Verbinde den ersten **Geometry** Parameter mit dem Datenstrom 1 (D1) Eingabeparameter der ersten **Merge** Komponente. ||
|21.| Verbinde den zweiten **Geometry** Parameter mit dem Datenstrom 2 (D2) Eingabeparameter der ersten **Merge** Komponente. ||
|22.| Verbinde den ersten **Curve** Parameter mit dem Datenstrom 1 (D1) Eingabeparameter der zweiten **Merge** Komponente. ||
|23.| Verbinde den zweiten **Curve** Parameter mit dem Datenstrom 2 (D2) Eingabeparameter der zweiten**Merge** Komponente. ||
|24.| Rechtsklicke auf den Zellen (C) Ausgabeparameter der **Rectangular Grid** Komponente und wähle "Flatten". |||

![IMAGE](images/1-4-7/1-4-7_008-definition-2.png)

||||
|--|--|--|
|25.| **Sets/List/List Length** – Ziehe eine **List Length** Komponente auf die Leinwand.|[![IMAGE](images/1-4-7/1-4-7_009-list-length.png)](../../appendix/A-1/0_index-of-components.html#SLLng)|
|26.| Verbinde den Zellen (C) Ausgabeparameter der **Rectangular Grid** Komponente mit dem Liste (L) Eingabeparameter der **List Length** Komponente. ||
|27.| **Sets/Sequence/Repeat Data** – Ziehe eine **Repeat Data** Komponente auf die Leinwand.|[![IMAGE](images/1-4-7/1-4-7_010-repeat-data.png)](../../appendix/A-1/0_index-of-components.html#SSRepeat)|
|28.| Verbinde den Laenge (L) Ausgabeparameter der **List Length** Komponente mit dem Laenge (L) Eingabeparameter der **Repeat Data** Komponente. ||
|29.| **Params/Input/Panel** – Ziehe ein **Panel** auf die Leinwand.||
|30.| Doppelklicke das **Panel**. Deaktiviere "Multiline Data", "Wrap Items" und "Special Codes".
Gib folgenden Text ein:<ul>1<br>0<br>0</ul><br><blockquote>Dies ist das Muster in dem die Geometrien verteilt werden. 0 ruft die erste referenzierte Geometrie auf und 1 ruft die zweite referenzierte Geometrie auf. Änderungen an der Reihenfolge der Zahlen oder an den Abmessungen des Rasters werden das Muster verändern.</blockquote>|[![IMAGE](images/1-4-7/1-4-7_011-panel.png)](../../appendix/A-1/0_index-of-components.html#PIPanel)|
|31.| Verbinde das **Panel** mit dem Daten (D) Eingabeparameter der **Repeat Data** Komponente.|||

![IMAGE](images/1-4-7/1-4-7_012-definition-3.png)

||||
|--|--|--|
|32.| **Sets/List/List Item** – Ziehe zwei **List Item** Komponenten auf die Leinwand.|[![IMAGE](images/1-4-7/1-4-7_013-list-item.png)](../../appendix/A-1/0_index-of-components.html#SLItem)|
|33.| Verbinde den Ergebnis (R) Ausgabeparameter der ersten **Merge** Komponente mit dem Liste (L) Eingabeparameter der ersten **List Item** Komponente.||
|34.| Verbinde den Ergebnis (R) Ausgabeparameter der zweiten **Merge** Komponente mit dem Liste (L) Eingabeparameter der zweiten **List Item** Komponente.||
|35.| Verbinde den Daten (D) Ausgabeparameter der **Repeat Data** Komponente mit dem Index (i) Eingabeparameter der ersten und zweiten **List Item** Komponente.||
|36.| **Transform/Affine/Rectangle Mapping** – Ziehe eine **Rectangle Mapping** Komponente auf die Leinwand.|[![IMAGE](images/1-4-7/1-4-7_014-rectangle-mapping.png)](../../appendix/A-1/0_index-of-components.html#TARecMap)|
|37.| Verbinde den Zellen (C) Ausgabeparameter der **Rectangular Grid** Komponente mit dem Ziel (T) Eingabeparameter der **Rectangular Mapping** Komponente.||
|38.| Verbinde den Elemente (I) Ausgabeparameter der ersten **List Item** Komponente mit dem Geometrie (G) Eingabeparameter der **Rectangular Mapping** Komponente.||
|39.| Verbinde den Elemente (I) Ausgabeparameter der zweiten **List Item** Komponente mit dem Quelle (S) Eingabeparameter der **Rectangular Mapping** Komponente.|||

![IMAGE](images/1-4-7/1-4-7_015-definition-4.png)

Veränderungen an der Eingabegeometrie und am Muster werden das Fliesenmuster verändern.

![IMAGE](images/1-4-7/1-4-7_016-example-results.png)

![IMAGE](images/1-4-7/1-4-7_017-large-example.png)
