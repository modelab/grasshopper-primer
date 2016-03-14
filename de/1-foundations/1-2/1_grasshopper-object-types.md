### 1.2.1. GRASSHOPPER OBJEKTTYPEN

#####Grasshopper besteht aus zwei primaeren Typen von Benutzerobjekten: Parameter und Komponenten. Parameter speichern Daten, wobei Komponenten Aktionen ausfuehren, welche wiederum Daten erzeugen. Der einfachste Weg, um Grasshopper zu verstehen ist, sich daran zu erinnern, dass wir Daten nutzen werden, um die Eingabe von Aktionen zu definieren (was neue Daten erzeugt, die wir im weiteren Verlauf nutzen koennen). 
####1.2.1.1. PARAMETER
Parameter speichern die Daten – Zahlen, Farben, Geometrien , u.a. – die wir durch den Graph unserer Definition senden. Parameter sind Containerobjekte, welche gewoehnlich als kleine rechteckige Kaestchen mit einer einzelnen Eingabe und Ausgabe angezeigt werden. Wir koennen Parameter auch an der Form des Symbols erkennen, da alle Parameterobjekte eine sechseckige Einfassung haben.

Geometrieparameter koennen Geometrien aus Rhino referenzieren oder Geometrien von anderen Komponenten aufnehmen. Punkt- und Kurvenobjekte sind beide Geometrieparameter.

![IMAGE](images/1-2-1/1-2-1_001-geometry-parameters.png)

Eingabeparameter sind dynamische Schnittstellenobjekte, die es ermoeglichen direkt mit der Definition zu interagieren. Die Schieberegler und der Graphmapper sind jeweils Eingabeparameter. 
![IMAGE](images/1-2-1/1-2-1_002-input-parameters.png)

####1.2.1.2. KOMPONENTEN
Komponenten fuehren Aktionen auf Basis der Eingaben aus, welche sie erhalten. Es gibt viele verschiedene Typen von Komponenten fuer verschiedene Aufgaben. 
![IMAGE](images/1-2-1/1-2-1_003-components.png)

>1. Die Multiplikations-Komponente ist ein Operator, der das Produkt zweier Zahlen berechnet.
2. Die Divide Curve-Komponente arbeitet mit Geometrien. Sie teilt eine Kurve in gleich lange Segmente. 

3. Die Circle CNR-Komponente konstruiert eine Kreisgeometrie von den Eingaben, dem Mittelpunkt, Normalenvektor und Radius.
4. Die Loft-Komponente konstruiert eine Loftflaeche von zwei Kurven.

####1.2.1.3. OBJEKTFARBEN
Wir koennen einige Informationen ueber die Objekte erhalten, wenn wir ihre Farben betrachten. Schauen wir uns die grundsaetzliche Farbcodierung von Grasshopper gemeinsam an. 
Ein Parameter, der keine Warnungen oder Fehlermeldungen enthaelt, wird in hellgrau angezeigt. Diese Objektfarbe zeigt an, dass dieser Parameter einwandfrei arbeitet. 
Ein Parameter, der Warnungen enthaelt, wird als orangenes Kaestchen angezeigt. Objekte, die keine Daten als Eingabe erhalten, sind verdaechtig, weil sie nicht zur Grasshopperdefinition beitragen. Deshalb werden alle Parameter, wenn sie frisch hinzugefuegt werden, erst einmal orange dargestellt, um anzuzeigen, dass sie keine Daten enthalten und keinen Einfluss auf das Ergebnis der Definition haben. Standardmaessig erhalten orange angezeigte Parameter und Komponenten einen kleinen Ballon an der rechten, oberen Ecke des Objekts. Sobald du mit der Maus ueber den Ballon faehrst, wird er Informationen darueber anzeigen, warum die Warnung aufgetreten ist. Sobald ein Parameter Daten enthaelt oder definiert, wird er in grau angezeigt und der Ballon verschwindet.

![IMAGE](images/1-2-1/1-2-1_004-parameter-warning.png)

Eine Komponente ist immer ein staerker eingebundenes Objekt, weshalb wir seine Eingabe und Ausgabe bewusst verstehen und anschliessend koordinieren muessen. Wie bei den Parametern wird eine Komponente, die Warnungen enthaelt, orange dargestellt. Behalte im Hinterkopf, dass Warnungen nicht gezwungenermassen schlecht sind, sondern dass Grasshopper dich mit ihnen lediglich auf ein potenzielles Problem in der Definition hinweisen moechte.

![IMAGE](images/1-2-1/1-2-1_005-component-warning.png)

Eine Komponente, die weder Warnungen noch Fehlermeldungen enthaelt, wird in hellgrau angezeigt.

Eine Komponente, deren Vorschau deaktiviert wurde, wird in einem etwas dunkleren Grauton dargestellt. Es gibt zwei Moeglichkeiten, um die Vorschau einer Komponente zu deaktivieren. Zuerst einmal kannst du einfach einen Rechtsklick auf der Komponente ausfuehren und den Vorschauschalter umschalten. Um die Vorschau verschiedener Komponenten gleichzeitig auszuschalten, musst du die gewuenschten Komponenten auswaehlen und dann den entsprechenden Schalter (Mann mit verbundenen Augen) im Dropdownmenue auswaehlen, nachdem du irgendwo auf der Leinwand einen rechten Mausklick ausgefuehrt hast.

Eine deaktivierte Komponente wird in einem stumpfen Grauton dargestellt. Um eine Komponente zu deaktivieren, kannst du einen Rechtsklick auf einer Komponente machen und den Disable-Schalter betaetigen, oder die gewuenschten Komponenten auswaehlen und nach einem Rechtsklick auf der Leinwand die Option Disable auswaehlen. Deaktivierte Komponenten senden keine Daten mehr an nachgelagerte Komponenten.

Eine ausgewaehlte Komponente wird in hellgruen angezeigt. Falls die Komponente Geometrien in der Rhinoszene erzeugt hat, werden diese ebenfalls gruen, um dir eine optische Rueckmeldung zu geben.
Eine Komponente, die mindestens eine Fehlermeldung enthaelt, wird rot dargestellt. Die Fehlermeldung kann durch die Komponente selbst oder ihre Eingabe und Ausgabe ausgeloest werden.

![IMAGE](images/1-2-1/1-2-1_006-object-colors.png)
>1. Ein Parameter ohne Warnungen und Fehlermeldungen
2. Ein Parameter mit Warnungen
3. Eine Komponente mit Warnungen
4. Eine Komponente ohne Warnungen und Fehlermeldungen
5. Eine Komponente mit deaktivierter Vorschau
6. Eine deaktivierte Komponente
7. Eine ausgewaehlte Komponente
8. Eine Komponente mit einer Fehlermeldung
