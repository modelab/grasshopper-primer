### 1.2.2. GRASSHOPPER KOMPONENTEN

##### Komponenten sind die Objekte, welche Du auf der Leinwand platzierst und mit Kabeln miteinander verbindest um ein visuelles Programm zu erstellen. Komponenten repräsentieren Rhino Geometrien und verhalten sich wie mathematische Funktionen. Komponenten haben Eingabe- und Ausgabeparameter. 


![IMAGE](images/1-2-2/1-2-2_001-component-parts.png)
>1. Die drei Eingabeparameter einer "Circle CNR" Komponente.
2. Das "Circle CNR" Komponentenlabel.
3. Die Ausgabeparameter der "Circle CNR" Komponente.

Eine Komponente benötigt Daten, damit sie ihre Aktionen ausführen kann und dann normalerweise ein Ergebnis darstellt. Das ist der Grund, warum die meisten Komponenten eine verschachtelte Struktur von Parametern haben, die als Eingabe- und Ausgabeparameter bezeichnet werden. Eingabeparameter sind an der linken Seite angeordnet, Ausgabeparameter an der rechten Seite.

Es gibt einige Grasshopperkomponenten, die nur Eingabe-, aber keine Ausgabeparameter haben, oder andersherum. Wenn eine Komponente keine Eingabe- oder Ausgabeparameter hat, wird es eine gezackte Kante haben.

![IMAGE](images/1-2-2/1-2-2_002-components-without-outputs.png)

#### 1.2.2.1. LABEL ODER SYMBOL DARSTELLUNG
Jedes Grasshopperobjekt hat ein einzigartiges Symbol. Diese Symbole werden im Zentrum des entsprechenden Objektes dargestellt und korrespondieren mit den Symbolen, die in der Komponentenpalette dargestellt werden. Objekte können auch mit Text beschriftet dargestellt werden. Um zwischen Symbol- und Textdarstellung umzuschalten, wähle “Draw Icons” im Ansichtsmenu. Du kannst auch “Draw Full Names” auswählen, um den gesamten Namen eines Objekts mitsamt seinen Eingabe- und Ausgabeparametern darzustellen.

![IMAGE](images/1-2-2/1-2-2_003-label-icon-screenshot.png)
>1. Schalte zwischen Symbol- und Textdarstellung um.
2. Zeige den gesamten Namen einer Komponente mitsamt seinen Eingabe- und Ausgabeparametern an.

![IMAGE](images/1-2-2/1-2-2_004-label-icon-fullnames.png)
>1. Die "Circle CNR" Komponente in Textdarstellung
2. Die "Circle CNR" Komponente in Symboldarstellung
3. Die "Circle CNR" Komponente mit gesamtem Namen angezeigt


Wir empfehlen die Symboldarstellung, um Dich mit den Symbolen in der Komponentenpalette vertraut zu machen. Dies wird Dir auch helfen Definitionen auf einen Blick zu verstehen. Textlabels können verwirrend sein, weil verschiedene Komponenten dieselbe Bezeichnung teilen können.

![IMAGE](images/1-2-2/1-2-2_005-circle-label-vs-icon.png)
>"Circle CNR" und "Circle 3pt" haben dasselbe Textlabel, aber unterschiedliche Symbole.

Eine Eigenschaft, die Dir helfen kann, Dich mit der Position von Komponenten in der entsprechenden Palette vertraut zu machen, besteht darin Strg + Alt zu halten, während Du auf eine bestehende Komponente auf der Leinwand klickst. Dies wird die Position der Komponente in der Palette anzeigen.

![IMAGE](images/1-2-2/1-2-2_006-reveal-location.png)

#### 1.2.2.2. KOMPONENTEN HILFE
Rechtsklicke auf ein Objekt und wähle “Help” im Drop-down menu um das Grasshopper Hilfefenster zu öffnen. Das Hilfefenster enthält eine detailliertere Beschreibung des Objekts, eine Liste der Eingabe- und Ausgabeparameter und einige Anmerkungen.

![IMAGE](images/1-2-2/1-2-2_007-component-help.png)
>1. Grasshopper Hilfefenster für einen Punktparameter
2. Die Anmerkungen im Hilfefenster geben zusätzliche Hinweise zum Punktparameter.

#### 1.2.2.3. WERKZEUGTIPPS
Eingabeparameter von Komponenten erwarten, bestimmte Datentypen zu erhalten. Beispielsweise kann eine Komponente anzeigen, dass Du einen Punkt oder eine Ebene als Eingabe mit ihr verbinden sollst. Wenn Du mit Deiner Maus über die verschiedenen Teile der Komponente fährst, wirst Du verschiedene Werkzeugtipps sehen, die einen bestimmten Typ anzeigen, den das Unterobjekt, das sich gerade unter der Mausanzeige befindet, erfordert. Werkzeugtipps sind relativ informativ, da sie Dir von den erforderlichen Typen und Daten der bestimmten Parameter berichten.


![IMAGE](images/1-2-2/1-2-2_008-tool-tips.png)
>1. Die Überschrift des Werkzeugtipps zeigt Dir das Symbol für den Eingabetypen, den Namen der Komponente, das Label für die Eingabe und die Eingabetype nochmals im Textformat an.
2. Die sprachliche Beschreibung des Eingabeparameters für die Komponente.
3. Alle Werte, die für den Eingabeparameter definiert wurden - entweder lokal oder von einem verbundenen Kabel.
4. Die Überschrift des Ausgabewerkzeugtipps stellt dieselben Details bereit, wie auf der Eingabeseite, jedoch für den entsprechenden Ausgabeparameter.
5. Das Ergebnis der Aktion der Komponente.

#### 1.2.2.4. KONTEXT POPUPMENUS
Alle Objekte auf der Leinwand haben ihre eigenen Kontextmenüs, die ihre Einstellungen und Details beinhalten. Du kannst diese Kontextmenüs öffnen, indem Du im Zentrum der Komponente rechtsklickst. Eingabe- und Ausgabe haben jeweils ihre eigenen Kontextmenüs, welche mit einem entsprechenden Rechtsklick zugänglich sind.

![IMAGE](images/1-2-2/1-2-2_009-context-menus-a.png)
>1. Komponenten Kontextmenu.
2. Bearbeitbares Textfeld, das den Namen des Objektes listet.
3. Vorschauanzeige - zeigt an, ob die von diesem Objekt erzeugte Geometrie in den Rhinoansichtsfenstern sichtbar ist. Die Vorschau auszuschalten wird die Aktualisierungsrate der Ansichtsfenster in Rhino sowie die Zeit zur Berechnung der Lösungen beschleunigen.
4. Laufzeitwarnungen - hier werden Warnungen gelistet, welche die Komponente bei der Ausführung ihrer Funktion behindern.

![IMAGE](images/1-2-2/1-2-2_010-context-menus-b.png)
>1. C Eingabe Kontextmenu.
2. Wähle einen oder mehrere Punkte - ermöglicht es Dir Referenzgeometrien im Rhinoansichtsfenster auszuwählen.
3. Verwalte Punktsammlungen - öffnet ein Dialogfenster, das es Dir erlaubt Punkte zu einer Punktsammlung hinzuzufügen oder Punkte davon zu entfernen und Informationen zu jedem Punkt einzusehen.
4. Füge ein Element zur Sammlung hinzu.
5. Lösche die Auswahl.

#### 1.2.2.5. VERGRÖSSERBARE BENUTZEROBERFLÄCHE
Einige Komponenten können durch vergrößerbare Benutzeroberflächen bearbeitet werden, um die Anzahl von Eingabe- und Ausgabeparametern zu verändern. Indem Du auf die entsprechende Komponente auf der Leinwand zoomst, kannst Du weitere Optionen einsehen, welche es Dir ermöglichen Eingabe- und Ausgabeparameter von der Komponente zu entfernen oder zu ihr hinzuzufügen. Die "Addition" Komponente ermöglicht es Dir Eingabeparameter hinzuzufügen und so weitere Elemente für die Additionsoperation darzustellen.

![IMAGE](images/1-2-2/1-2-2_011-zoomable-ui.png)
>1. Klicke auf das + Zeichen um einen Eingabeparameter hinzuzufügen.
2. Klicke auf das - Zeichen um einen Eingabeparameter zu entfernen.

Die Paneelkomponente besitzt ebenso eine vergrößerbare Benutzeroberfläche. Ein Paneel ist wie ein Post-It™ Sticker. Es erlaubt Dir kleine Anmerkungen und Erklärungen zu Deinem Dokument hinzuzufügen. Du kannst den Text des Paneels durch das Menu oder mit einem Doppelklick auf die Oberfläche verändern. Paneele können auch Daten aus anderen Quellen empfangen und anzeigen. Wenn Du einen Ausgabeparameter an ein Paneel anschliesst, kannst Du die Inhalte des entsprechenden Parameters in Echtzeit sehen. Alle Daten in Grasshopper können auf diese Weise angezeigt werden. Wenn Du auf ein Paneel zoomst, erscheint ein Menu, welches es Dir erlaubt den Hintergrund, die Schriftart und andere Eigenschaften anzuzeigen. Diese Optionen sind auch über einen Rechtsklick auf das Paneel zugänglich.

![IMAGE](images/1-2-2/1-2-2_012-zoomable-panel.png)
>1. Ziehe an den Rändern, um die Paneelabmessungen zu verändern.
2. Erhöhe oder reduziere die Schriftgrösse des Paneelinhaltes.
3. Verändere die Ausrichtung des Paneelinhaltes.
4. Wähle die Schriftart für den Paneelinhalt.
5. Wähle die Farbe des Paneelhintergrundes. Du kannst einen neuen Standardfarbton für Paneele wählen, indem Du nach einem Rechtsklick auf das Paneel die Option "Set Default Color" ausführst.

