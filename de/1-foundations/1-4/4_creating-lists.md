### 1.4.4. Listen erstellen
{% if gitbook.generator == "pdf" or "mobi" or "epub" %}
>Beispieldatein fuer diesen Abschnitt: [http://grasshopperprimer.com/appendix/A-2/1_gh-files.html](http://grasshopperprimer.com/appendix/A-2/1_gh-files.html)
{% else %}
>Beispieldatein fuer diesen Abschnitt: [Download](../../appendix/A-2/gh-files/1.4.4_list creation.gh)
{% endif %}

#####Es gibt viele verschiedene Wege um Listen in Grasshopper zu erzeugen. Weiter unten werden wir ein paar Methodes zur Erzeugung von Listen anschauen und dann genauer untersuchen, wie die Daten genutzt werden koennen um Informationen im Ansichtsfenster zu visualisieren.

####1.4.4.1. HAENDISCHE ERZEUGUNG VON LISTEN
Vielleicht der einfachste Weg um Listen zu erstellen (und die am meisten uebersehene Methode) ist die haendische Eingabe von Werten einer Liste in einen Parameter. Die Nutzung dieser Methode erhoeht die Verantworrung die der Nutzer traegt, weil diese Methode auf der direkten Eingabe durch den Nutzer beruht (d.h. persistente Daten) um die Liste zu erstellen. Damit die Werte der Liste veraendert werden muss der Nutzer jeden einzelnen Wert individuell eingeben, was sich entsprechend schwierig gestaltet, wenn die Liste viele Werte beinhaltet. Es gibt einige Wege um Listen haendisch zu erstellen. Ein Weg ist es einen Zahlenparameter zu nutzen. Rechtsklicke auf den Zahlenparameter und waehle “Manage Number Collection.”

![IMAGE](images/1-4-4/1-4-4_001-manual-list-creation.png)
>1. Rechtsklicke den Zahlenparameter um den "Number collection Manager" zu oeffnen.
2. Klicke das "Add Item" Symbol um eine Zahl zur Liste hinzuzufuegen.
3. Doppelklicke eine Zahl um ihren Wert zu aendern.

Eine andere Methode ist die manuelle Eingabe der Liste in ein Paneel. Versichere Dich, dass die Option “Multiline Data” ausgeschaltet ist.

![IMAGE](images/1-4-4/1-4-4_002-panel.png)

####1.4.4.2. RANGE
Die "Range" Komponente, die unter "Sets/Sequence/Range" gefunden werden kann, erzeugt eine Liste von gleichmaessig verteilten Zahlen zwischen einem Tief- und einem Hochwert, genannt Domaene. Eine Domaene (manchmal auch Intervall genannt) besteht aus jeder moeglichen Zahl zwischen zwei nummerischen Extremen.

Eine "Range" Komponente unterteilt eine nummerische Domaene in gleiche Segmente und gibt eine entsprechende Liste von Werten aus.

![IMAGE](images/1-4-4/1-4-4_003-range.png)
>1. Anzahl von Schritten = 10
2. Domaene erstreckt sich von 0 bis 1
3. Gesamtanzahl von Punkten = 13

Im Beispiel unterhalb, wurde die nummerische Domaene zwischen 0 und 20 definiert. Die  "Range" Komponente nimmt diese Domaene und teile sie durch die Anzahl von Schritten (in diesem Fall 10). Nun haben wir 10 gleichmaessig verteilte Segmente. Die "Range" Komponente gibt die Liste von Werten zurueck. Weil der erste und letzte Wert der Liste erhalten bleiben, ergibt die Ausgabe einer "Range" Komponente immer eine Zahl mehr als die angegebene Anzahl von Schritten. Im Beispiel oben haben wir 10 Schritte angegeben, also liefert die "Range" Komponente 11 Werte.

![IMAGE](images/1-4-4/1-4-4_004-range_2.png)
>Erstelle eine Liste mit der "Range" Komponente indem Du eine Domaene und eine Anzahl von Schritten definierst.

Dir ist vielleicht aufgefallen, dass an dem eben erstellten Setup etwas seltsam ist. Wir wissen, dass eine domaene immer durch zwei Werte definiert wird (dem Hoch- und Tiefwert). Jedoch haben wir in unserer Definition nur einen einzelnen Wert mit dem Eingabeparameter der Domaene verbunden. Um Fehler zu vermeiden, nimmt Grasshopper an, dass wir versuchen eine Domaene zu erstellen, die von null bis zu einem bestimmten Wert (dem Wert unseres Schiebereglers) geht. Damit die Reihe zwischen zwei Werten erstellt wird, die nicht bei null beginnen, muessen wir die "Construct Domain" Komponente nutzen um die Domaene zu spezifizieren.

![IMAGE](images/1-4-4/1-4-4_005-construct-domain.png)
>Um eine Reihe mit einer Domaene zu erstellen, die nicht bei null beginnt, nutze die "Construct Domain" Komponente.

####1.4.4.3. SERIEN
Die "Series" Komponente ist aehnlich zur "Range" Komponente, da sie auch eine Liste mit Zahlen erstellt. Jedoch ist die "Series" Komponete auch verschieden, weil sie eine Reihe von bestimmten Zahlen erstellt, die durch einen Startwert, die Schrittgroesse und die Anzahl der gewuenschten Werte beschrieben wird.

![IMAGE](images/1-4-4/1-4-4_006-series.png)
>Die "Series" Komponente erstellt eine Liste basierend auf einem Startwert, der Schrittgroesse und der Anzahl von Werten, die in der Liste enthalten sein sollen.

###1.4.4.4. RANDOM
Die "Random" Komponente (Sets/Sequence/Random) kann sogenannte pseudorandomierte Werte erzeugen. Sie werden "pseudo" randomiert gennant, da sie eine einzigartige Zahlenfolde beschreiben, die stabil aus einem Samenwert hervorgehen. Deshalb kannst Du eine komplett zufaellige Zahl nur dadurch erzeugen, dass Du den Samenwert veraenderst (S Eingabeparameter). Die Domaene, wie im vorangegangenen Beispiel, wird durch ein Intervall zwischen zwei nummerischen Extremen definiert.

![IMAGE](images/1-4-4/1-4-4_007-random.png)
