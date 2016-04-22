###1.1.3. MIT RHINO REDEN

#####Im Unterschied zu einem Rhinodokumnet, enthaelt eine Grasshopperdefinition keine tatsaechlichen Objekte oder Geometrien. Stattdessen repraesentiert eine Grasshopperdefinition eine Reihe von Regeln und Instruktionen, wie Rhino Aufgaben automatisieren kann. 
![IMAGE](images/1-1-3/1-1-3_001-talking-to-rhino.png)
>1. Grasshoppervorschau fuer Geometrien.
2. Rhino Darstellungsfenster.
3. Grasshopper Anwendungsfenster.




####1.1.3.1. REAKTION DER DARSTELLUNGSFENSTER
Alle Geometrie, die mit den verschiedenen Grasshopperkomponenten  erzeugt wird, wir d (standartmaessig) im Rhino Darstellungsfenster auftauchen. Diese Vorschau ist nur eine Open GL
Annaeherung der eigentlichen Geometrie, und als solche kann sie nicht als Geometrie im Rhino Darstellungsfenster ausgewaehlt werden (Du musst sie zuerst in die Szene backen). Du kannst die Geometrievorschau ein- bzw. Ausschalten, indem Du eine Komponente mit einem Rechtsklick anklickst und den Vorschauschlaten auswaehlst. Die Geometrie im Darstellungsfenster ist farbkodiert um visuelles Feedback zu geben. Das unten gezeigt Bild umreisst das Standartfarbschema. 
>Merke: Dies ist ein Standartfarbschema, welches mit den Dokumentenvorschaueinstellungen in der Canvaswerkzeugleiste angepasst werden kann.

![IMAGE](images/1-1-3/1-1-3_002-viewport-feedback.png)
>1. Gruene Geometrien im Darstellungsfenster gehoert zur gerade ausgewaehlten Komponente.
2. Rote Geometrien im Darstellungsfenster gehoeren zu einer Komponente, die gerade nicht ausgewaehlt ist.
3. Punktgeometien sind as Kreuz dargestellt, um sie von den rechteckig dargestellten Rhino Punktobjekten unterscheiden zu koennen.
4. Blaue Rueckmeldungen bedeuten, dass Du gerade eine Auswahl im Rhino Darstellungsfenster ausfuehrst. 
####1.1.3.2. LEBHAFTE KABEL
Grasshopper ist ein dynamisches Umfeld. Aenderungen, die gemacht werden sind live und ihre Vorschau wird im Rheino Darstellungsfenster stets aktualisiert. 
![IMAGE](images/1-1-3/1-1-3_003-live-wires.png)

####1.1.3.3. GUMBALL WIDGET
Wenn eine Geometrie in einen Grasshopper Parameter internalisiert gespeichert wird, erlaubt der Gumball Dir mit der Geomerie im Rhino Darstellungsfenster zu interagieren. Diese Interaktion ist live und Aktualisierungen werden durchgefuehrt, waehrend Du mit dem Gumball arbeitest. Im Gegensatz werden direkt von Rhino referenzierte Geometrien weiter im Rhinodokument existieren und Aktualisierungen werden erst nach dem Aufteten von Aenderungen ausgefuehrt (anstatt waehrend dessen).
![IMAGE](images/1-1-3/1-1-3_004-gumball.png)

####1.1.3.4. BACKEN VON GEOMETRIEN
Um mit Geometrien in Rhino zu bearbeiten (auswaehlen, editieren, transformieren, etc.), die in Grasshopper erstellt wurden, musst Du sie “backen”. Backen instanziiert neue Geometrien im Rhinodokument, basierend auf dem momentanen Zustand des Grasshoppergraphen. Sie wird im Weiteren nicht mehr die weitere Aenderungen der Definition ansprechbar sein.
![IMAGE](images/1-1-3/1-1-3_005-baking.png)
>1. Backe durch Rechtsklick auf eine Komponente und Auswahl der Funktion Bake.
2. Ein Dialog wird auftauchen, der es Dir erlaubt auszuwaehlen, auf welcher Rhinoebene die Geometrie eingefuegt wird.
3. Gruppieren von gebackener Geometien ist ein komfortabler Weg um instantiierte Geometrien zu verwalten, besonders wenn Du viele Objekte in Grasshopper erzeugst. 

####1.1.3.5. EINHEITEN & TOLERANZEN
Grasshopper uebernimmt Einheiten und Toleranzen von Rhino. Um die Einheiten zu aendern, gebe _Document Properties in die Rhino Befehlszeile ein, wodurch Du Zugang zum Menu fuer Dokumenteneigenschaften erhaeltst. Waehle Einheiten um Einheiten und Toleranzen zu aendern.

![IMAGE](images/1-1-3/1-1-3_006-units.png)
>Aendere Einheiten und Toleranzen im Rhinomenu fuer Dokumenteneigenschaften.

####1.1.3.6. FERNBEDIENUNGSPANEEL
Wenn Du einmal angefangen hast, ist Grasshopper ein unglaublich maechtiges und flexibles Werkzeug, dass er Dir erlaubt verschiedene Iterationen waehrend des Entwurfsprozesses mit der graphischen Oberflaeche zu erkunden.
Jedoch hast Du vielleicht schon gemerkt, dass wenn Du an einem einzelnen Bildschirm arbeitest der Grasshoppereditor einen grossen Teil der Bildschirmoberflaeche einnimmt. Abgesehen von  konstantem ein- und auszoomen und verschieben der Fenster auf dem Bildschirm, gibt es noch keine elegante Loesung des Problems. Das heist… bis zur Veroeffentlichung des Fernbedienungspaneels!

Das Remote Control Panel (RCP) stellt eine minimale Oberflaeche zur Kontrolle Deiner Definition bereit, ohne unnoetig viel Platz auf dem Bildschirm einzunehmen. Das RCP kann dargestellt werden, indem Du dem Schalter im Ansichtsmenu der Hauptmenuleiste anklickst. Standardmaessig ist das RCP blank - das bedeutet nicht, dass es keine Informationen ueber Dein aktuelle Grasshopperdokument enthaelt. Um das RCP mit Bentzeroberflaechen(UI)-Elementen wie Schiebereglern, Schaltern und Knoepfen zu belegen, rechtsklicke einfach au das Element und waehle Publish to Remote Panel. Dies wird eine neue Gruppe erstellen und ein synchronisiertes UI-Element im RCP erzeugen. Eine Veraenderung der Werte des UI wird auch die werte in Deinem Graphen aktualisieren und die Geometrien in den Ansichtsfenstern modifizieren, die von diesen Parametern abhaengen. Du kannst mehrere Elemente im RCP veroeffentlichen und die gesamte Oberflaeche belegen. Diese Funktion kannst Du nutzen, um Deine Datei zu kontrollieren, ohne dass Du die Verstrickungen Deines visuellen Graphen in der Nutzeroberflaeche oberhalb Deiner Rhinoansichtsfenster zeigen zu muessen.

>Merke: Das RCP wird die Namen der UI Elemente uebernehmen und deren Namen als Label nutzen. Es ist gute Praxis die Schieberegler und Schalter mit entsprechend verstaendlichen und bedeutungsvollen namen zu aktualisieren. Dies wird die Nutzbarkeit Deines RCP unwahrscheinlich erleichtern.

![IMAGE](images/1-1-3/1-1-3_007-remote-control1.png)
> Um ein UI Element (z.B. Schieberegler, Schalter, Knopf) im Remote Control Panel anzuzeigen, muessen wir es erst dort publizieren.

Die RCP UI kann auch personalisiert werden – um Dir zu erlauben, festzulegen an welcher Stelle Objekte in der Oberflaeche erscheinen, sowie die Namen und Farben verschiedener Gruppen einzustellen. Um das Layout des RCP zu modifizieren musst Du zuerst vom "Working Mode" (die Standard RCP-Ansicht) in den "Edit Mode" umschalten. Du kannst diesen Bearbeitungsmodus erreichen, indem Du auf den gruenen Bleistift in der oberen rechten Ecke des RCP klicks. Sobald Du im Bearbeitungsmodus bist, kannst Du neue UI-Gruppen erstellen, Elemente innerhalb der Gruppen neu ausrichten, Label hinzufuegen, Farben aendern und vieles mehr. Um ein UI-Element zu loeschen, ziehe es einfach ueber die Begrenzung des RCP hinaus. Du kannst die individuellen Werte der parameter nicht aendern, solange Du Dich im Bearbeitungsmodus befindest. Statt dessen, wirst Du wieder auf den gruenen Bleistift klicken muessen, um in den urspruenglichen Arbeitsmodus zurueckzukehren.

>_Das Remote Control Panel" hat zwei verschiedene Modi: Bearbeitungsmodus (links), der es Dir ermoeglicht das Aussehen und die Handhabung des RCP anzupassen, und den Arbeitsmodus (rechts), in dem Du die eigentlichen Werte des UI bearbeiten kannst._
![IMAGE](images/1-1-3/1-1-3_008-remote2.png)
>Das "Remote Control Panel" im Bearbeitungsmodus hat einen orangenen Hintergrund.




####1.1.3.7. DATEI MANAGEMENT
Wenn Deine Grasshopperdatei Geometrien aus Rhino referenziert, musst Du die selbe Datei in Rhino oeffnen, damit die Definition funktioniert. Behalte Deine Datein in einer organisierten Struktur, indem Du die Grasshopper- und Rhinodateien im selben Verzeichnis speicherst und Ihnen Namen gibst, die in Beziehung zueinander stehen.

![IMAGE](images/1-1-3/1-1-3_009-file-management.png)
>1. Projektverzeichnis.
2. Rhinodatei.
3. Grasshopperdatei.

####1.1.3.8. TEMPLATES
Die Erstellung und Spezifizierungen einer Templatedatei mit Deinen Grasshopperpraeferenzen ist ein angenehmer Weg um neue Grasshopperdefinitionen auf Grundlage Deiner Voreinstellungen zu erzeugen. Das Template kann Grasshopperkomponenten, -paneele und -skizzen enthalten, um Deine Dokumentation zu erleichtern.


![IMAGE](images/1-1-3/1-1-3_010-templates.png)
>Erzeuge eine Templatedatei und speichere sie.

![IMAGE](images/1-1-3/1-1-3_011-templates2.png)
>1. Unter File/Preferences, lade die Datei, die Du gerade als Template erstellt hast. Dein Template wird nun jedes Mal genutzt werden, wenn Du eine neue Datei erstellst.

