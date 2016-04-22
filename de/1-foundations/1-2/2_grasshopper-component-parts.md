### 1.2.2. GRASSHOPPER KOMPONENTEN

#####Komponenten sind die Objekte, welche Du auf der Leinwand platzierst und mit Kabeln miteinander verbindest um ein visuelles Programm zu erstellen. Komponenten repraesentieren Rhino Geometrien und verhalten sich wie mathematische Funktionen. Komponenten haben Eingabe- und Ausgabeparameter. 


![IMAGE](images/1-2-2/1-2-2_001-component-parts.png)
>1. Die drei Eingabeparameter einer "Circle CNR" Komponente.
2. Das "Circle CNR" Komponentenlabel.
3. Die Ausgabeparameter der "Circle CNR" Komponente.

Eine Komponente benoetigt Daten, damit sie ihre Aktionen ausfuehren kann und dann normalerweise ein Ergebnis darstellt. Das ist der Grund warum die meisten Komponenten eine verschachtelte Struktur von Parametern haben, die als Eingabe- und Ausgabeparameter bezeichnet werden. Eingabeparameter sind an der linken Seite angeordnet, Ausgabeparameter an der rechten Seite.

Es gibt einige Grasshopperkomponenten, die nur Eingabe-, aber keine Ausgabeparameter haben, oder andersherum. Wenn eine Komponente keine Eingabe- oder Ausgabeparameter hat, wird es eine gezackte Kante haben.

![IMAGE](images/1-2-2/1-2-2_002-components-without-outputs.png)

####1.2.2.1. LABEL ODER SYMBOL DARSTELLUNG
Jedes Grasshopperobjekt hat ein einzigartiges Symbol. Diese Symbole werden im Zentrum des entsprechenden Objektes dargestellt und korrespondieren mit den Symbolen, die in der Komponentenpalette dargestellt werden. Objekte koennen auch mit Text beschriftet dargestellt werden. Um zwischen Symbol- und Textdarstellung umzuschalten, waehle “Draw Icons” im Ansichtsmenu. Du kannst auch “Draw Full Names” auswaehlen, um den gesamten Namen eines Objekts mitsamt seinen Eingabe- und Ausgabeparmetern darzustellen.

![IMAGE](images/1-2-2/1-2-2_003-label-icon-screenshot.png)
>1. Schalte zwischen Symbol- und Textdarstellung um.
2. Zeige den gesamten Namen einer Kompomente mitsamt seinen Eingabe- und Ausgabeparametern an.

![IMAGE](images/1-2-2/1-2-2_004-label-icon-fullnames.png)
>1. Die "Circle CNR" Komponente in Textdarstellung
2. Die "Circle CNR" Komponente in Symboldarstellung
3. Die "Circle CNR" Komponente mit gesamtem Namen angezeigt


Wir empfehlen die Symboldarstellung, um Dich mit den Symbolen in der Komponentenpalette vertraut zu machen. Dies wird Dir auch helfen Definitionen auf einen Blick zu verstehen. Textlabels koennen verwirrend sein, weil verschiedene Komponenten die selbe Bezeichnung teilen koennen.

![IMAGE](images/1-2-2/1-2-2_005-circle-label-vs-icon.png)
>"Circle CNR" und "Circle 3pt" haben das selbe Textlabel, aber unterschiedliche Symbole.

Eine Eigenschaft, die Dir helfen kann, Dich mit der Position von Komponenten in der entsprechenden Palette vertraut zu machen, besteht darin Strg + Alt zu halten, waehrend Du auf eine bestehende Komponente auf der Leinwand klickst. Dies wird die Position der Komponente in der Palette anzeigen.

![IMAGE](images/1-2-2/1-2-2_006-reveal-location.png)

####1.2.2.2. KOMPONENTEN HILFE
Rechtsklicke auf ein Objekt und waehle “Help” im drop-down menu um das Grasshopper Hilfefenster zu oeffnen. Das Hilfefenster enthaelt eine detailliertere Beschreibung des Objekts, eine Liste der Eingabe- und Ausgabeparameter und einige Anmerkungen.

![IMAGE](images/1-2-2/1-2-2_007-component-help.png)
>1. Grasshopper Hilfefenster fuer einen Punktparameter
2. Die Anmerkungen im Hilfefenster geben zusaetzliche Hinweise zum Punktparameter.

####1.2.2.3. WERKZEUGTIPS
Eingabeparameter von Komponenten erwarten bestimme Datentypen zu erhalten. Beispielsweise kann eine Komponente anzeigen, dass Du einen Punkt oder eine Ebene als Eingabe mit ihr verbinden sollst. Wenn Du mit Deiner Maus ueber die verschiedenen Teile der der Komponente faehrst, wirst Du verschiende Werkyeugtips sehen, die einen bestimmten Typ anzeigen, den das Unterobjekt, das sich gerade unter der Mausanzeige befindet, erfordert. Werkzeugtips sind relativ informatif, da sie Dir von die erforderlichen Typen und Daten der bestimmten Parameter berichten.


![IMAGE](images/1-2-2/1-2-2_008-tool-tips.png)
>1. Die Ueberschrift des Werkzeugtips zeigt Dir das Symbol fuer den Eingabetypen, den Namen der Komponente, das Label fuer die Eignabe und die Eingabetype nochmals im Textformat an.
2. Die sprachliche Beschreibung des Eingabeparameters fuer die Komponente.
3. Alle Werte, die fuer den Eingabeparameter definiert wurden - entweder lokal oder von einem verbundenen Kabel.
4. Die Ueberschrift des Ausgabewerkzeugtips stellt die selben Details bereit, wie auf der Eingabeseite, jedoch fuer den entsprechenden Ausgabeparameter.
5. Das Ergebnis der Aktion der Komponente.

####1.2.2.4. KONTEXT POPUPMENUS
Alle Objekete auf der Leinwand haben ihre eigenen Kontextmenues, die ihre Einstellungen und Details beinhalten. Du kannst diese Kontextmenus oeffnen, indem Du im Zentrum der Komponente rechtsklicks. Eingabe- und Ausgabe haben jeweils ihre eigenen Kontextmenus, welche mit einem entsprechenden Rechts-Klick zugaenglich sind.

![IMAGE](images/1-2-2/1-2-2_009-context-menus-a.png)
>1. Komponenten Kontextmenu.
2. Bearbeitbares Textfeld, das den Namen des Objektes listet.
3. Vorschauanzeige - zeigt an, ob die von diesem Objekt erzeugte Geometrie in den Rhinoansichtsfenstern sichtbar ist. Die Vorschau auszuschalten wird die Aktualisierungsrate der Ansichtsfenster in Rhino, sowie die Zeit zur Berechnung der Loesungen beschleunigen.
4. Laufzeitwarnungen - hier werden Warnungen gelistet, welche die Komponente bei der Ausfuehrung ihrer Funktion behindern.

![IMAGE](images/1-2-2/1-2-2_010-context-menus-b.png)
>1. C Eingabe Kontextmenu.
2. Waehle einen oder mehrere Punkte - ermoeglicht es Dir Referenzgeometiren im Rhinoansichtsfenster auszuwaehlen.
3. Verwalte Punktsammlungen - oeffnet ein Dialogfenster, das es Dir erlaubt Punkte zu einer Punktsammlung hinzuzufuegen oder Punkte davon zu entfernen und Informationen zu jedem Punkt einzusehen.
4. Fuege ein Element zur Sammlung hinzu.
5. Loesche die Auswahl.

####1.2.2.5. VERGROESSERBARE BENUTZEROBERFLAECHE
Einige Komponenten koennen durch vergroesserbare Benutzeroberflaechen bearbeitet werden, um die Anzahl von Eingabe- und Ausgabeparametern zu veraenden. Indem Du auf die entsprechende Komponente auf der Leinwand zoomst, kannst Du weitere Optionen einsehen, welche es Dir ermoeglichen Eingabe- und Ausgabeparameter von der Komponente zu entfernen oder u ihr hinzuzufuegen. Die "Addition" Komponente ermoegliche es Dir Eingabeparameter hinzuzufuegen und so weitere Elemente fuer die Additionsoperation darzustellen.

![IMAGE](images/1-2-2/1-2-2_011-zoomable-ui.png)
>1. Klicke auf das + Zeichen um einen Eingabeparameter hinzuzufuegen.
2. Klicke auf das - Zeichen um einen Eingabeparameter zu entfernen.

Die Paneelkomponente besitzt ebenso eine vergroesserbare Benutzeroberflaeche. Ein Paneel ist wie ein Post-It™ Sticker. Es erlaubt Dir kleine Anmerkungen und Erklaerungen zu Deinem Dokument hinzuzufuegen. Du kannst den Text des Paneels durch das Menu oder mit einem Doppelklick auf die Oberflaeche veraendert werden. Paneele koennen auch Daten aus anderen Quellen empfangen und anzeigen. Wenn Du einen Ausgabeparameter an ein Paneel anschliesst, kannst Du die Inhalte des entsprechenden Parameters in Echtzeit sehen. Alle Daten in Grasshopper koennen auf diese Weise angezeigt werden. Wenn Du auf ein Paneel zoomst, erscheint ein Menu, welches es Dir erlaubt den Hintergrund, die Schriftart und andere Eigenschaften anzuzeigen. Diese Optionen sind auch ueber einen Rechtsklick auf das Paneel zugaenglich.

![IMAGE](images/1-2-2/1-2-2_012-zoomable-panel.png)
>1. Ziehe an den Raendern, um die Paneelabmessungen zu veraendern.
2. Erhoehe oder reduziere die Schriftgroesse des Paneelinhaltes.
3. Veraendere die Ausrichtung des Paneelinhaltes.
4. Waehle die Schriftart fuer den Paneelinhalt.
5. Waehle die Farbe des Paneelhintergrundes. Du kannst einen neuen Standardfarbton fuer Paneele waehlen, indem Du nach einem Rechtsklick auf das Paneel "Set Defaut Color" ausfuehrst.

