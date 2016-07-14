### 1.1.3. MIT RHINO REDEN

##### Im Unterschied zu einem Rhinodokument enthält eine Grasshopperdefinition keine tatsächlichen Objekte oder Geometrien. Stattdessen repräsentiert eine Grasshopperdefinition eine Reihe von Regeln und Instruktionen, wie Rhino Aufgaben automatisieren kann. 
![IMAGE](images/1-1-3/1-1-3_001-talking-to-rhino.png)
>1. Grasshoppervorschau für Geometrien.
2. Rhino Darstellungsfenster.
3. Grasshopper Anwendungsfenster.




#### 1.1.3.1. REAKTION DER DARSTELLUNGSFENSTER
Alle Geometrie, die mit den verschiedenen Grasshopperkomponenten erzeugt wird, wird (standardmässig) im Rhino Darstellungsfenster auftauchen. Diese Vorschau ist nur eine Open GL Annäherung der eigentlichen Geometrie, und als solche kann sie nicht als Geometrie im Rhino Darstellungsfenster ausgewählt werden (Du musst sie zuerst in die Szene "backen"). Du kannst die Geometrievorschau ein- bzw. ausschalten, indem Du eine Komponente mit einem Rechtsklick anklickst und die Vorschauoption auswählst. Die Geometrie im Darstellungsfenster ist farbkodiert um visuelles Feedback zu geben. Das unten gezeigt Bild umreisst das Standardfarbschema. 
>Merke: Dies ist ein Standardfarbschema, welches mit den Dokumentenvorschaueinstellungen in der Canvaswerkzeugleiste angepasst werden kann.

![IMAGE](images/1-1-3/1-1-3_002-viewport-feedback.png)
>1. Grüne Geometrien im Darstellungsfenster gehören zur gerade ausgewählten Komponente.
2. Rote Geometrien im Darstellungsfenster gehören zu einer Komponente, die gerade nicht ausgewählt ist.
3. Punktgeometien sind als Kreuz dargestellt, um sie von den rechteckig dargestellten Rhino Punktobjekten unterscheiden zu können.
4. Blaue Rückmeldungen bedeuten, dass Du gerade eine Auswahl im Rhino Darstellungsfenster ausführst. 

#### 1.1.3.2. LEBHAFTE KABEL
Grasshopper ist ein dynamisches Umfeld. Änderungen, die gemacht werden sind live und ihre Vorschau wird im Rhino Darstellungsfenster stets aktualisiert. 
![IMAGE](images/1-1-3/1-1-3_003-live-wires.png)

#### 1.1.3.3. GUMBALL WIDGET
Wenn eine Geometrie in einen Grasshopper Parameter internalisiert gespeichert wird, erlaubt der Gumball Dir mit der Geomerie im Rhino Darstellungsfenster zu interagieren. Diese Interaktion ist live und Aktualisierungen werden durchgeführt, während Du mit dem Gumball arbeitest. Im Gegensatz werden direkt von Rhino referenzierte Geometrien weiter im Rhinodokument existieren und Aktualisierungen werden erst nach dem Aufteten von Änderungen ausgeführt (anstatt währenddessen).
![IMAGE](images/1-1-3/1-1-3_004-gumball.png)

#### 1.1.3.4. BACKEN VON GEOMETRIEN
Um mit Geometrien in Rhino zu bearbeiten (auswählen, editieren, transformieren, etc.), die in Grasshopper erstellt wurden, musst Du sie “backen”. Backen erstellt neue Geometrien als Instanzen im Rhinodokument, basierend auf dem momentanen Zustand des Grasshoppergraphen. Sie werden im Weiteren nicht mehr durch weitere Änderungen der Definition ansprechbar sein.
![IMAGE](images/1-1-3/1-1-3_005-baking.png)
>1. Backe durch Rechtsklick auf eine Komponente und Auswahl der Funktion Bake.
2. Ein Dialog wird auftauchen, der es Dir erlaubt auszuwählen, auf welcher Rhinoebene die Geometrie eingefügt wird.
3. Gruppieren von gebackener Geometien ist ein komfortabler Weg um instantiierte Geometrien zu verwalten, besonders wenn Du viele Objekte in Grasshopper erzeugst. 

#### 1.1.3.5. EINHEITEN & TOLERANZEN
Grasshopper übernimmt Einheiten und Toleranzen von Rhino. Um die Einheiten zu ändern, gebe _Document Properties in die Rhino Befehlszeile ein, wodurch Du Zugang zum Menu für Dokumenteneigenschaften erhältst. Wähle Einheiten um Einheiten und Toleranzen zu ändern.

![IMAGE](images/1-1-3/1-1-3_006-units.png)
>Ändere Einheiten und Toleranzen im Rhinomenu für Dokumenteneigenschaften.

#### 1.1.3.6. FERNBEDIENUNGSPANEEL
Wenn Du einmal angefangen hast, ist Grasshopper ein unglaublich mächtiges und flexibles Werkzeug, das es Dir erlaubt verschiedene Iterationen während des Entwurfsprozesses mit der graphischen Oberfläche zu erkunden.
Jedoch hast Du vielleicht schon gemerkt, dass, wenn Du an einem einzelnen Bildschirm arbeitest, der Grasshoppereditor einen grossen Teil der Bildschirmoberfläche einnimmt. Abgesehen von  konstantem Ein- und Auszoomen und Verschieben der Fenster auf dem Bildschirm, gibt es noch keine elegante Lösung des Problems. Das heisst… bis zur Veröffentlichung des Fernbedienungspaneels!

Das Remote Control Panel (RCP) stellt eine minimale Oberfläche zur Kontrolle Deiner Definition bereit, ohne unnötig viel Platz auf dem Bildschirm einzunehmen. Das RCP kann dargestellt werden, indem Du den Schalter im Ansichtsmenu der Hauptmenuleiste anklickst. Standardmaessig ist das RCP blank - das bedeutet nicht, dass es keine Informationen über Dein aktuelles Grasshopperdokument enthält. Um das RCP mit Benutzeroberflächen(UI)-Elementen wie Schiebereglern, Schaltern und Knöpfen zu belegen, rechtsklicke einfach auf das Element und wähle Publish to Remote Panel. Dies wird eine neue Gruppe erstellen und ein synchronisiertes UI-Element im RCP erzeugen. Eine Veränderung der Werte des UI wird auch die Werte in Deinem Graphen aktualisieren und die Geometrien in den Ansichtsfenstern modifizieren, die von diesen Parametern abhängen. Du kannst mehrere Elemente im RCP veröffentlichen und die gesamte Oberfläche belegen. Diese Funktion kannst Du nutzen, um Deine Datei zu kontrollieren, ohne die Verstrickungen Deines visuellen Graphen in der Nutzeroberfläche oberhalb Deiner Rhinoansichtsfenster zeigen zu müssen.

>Merke: Das RCP wird die Namen der UI Elemente übernehmen und deren Namen als Label nutzen. Es ist gute Praxis die Schieberegler und Schalter mit entsprechend verständlichen und bedeutungsvollen Namen zu aktualisieren. Dies wird die Nutzbarkeit Deines RCP unwahrscheinlich erleichtern.

![IMAGE](images/1-1-3/1-1-3_007-remote-control1.png)
> Um ein UI Element (z.B. Schieberegler, Schalter, Knopf) im Remote Control Panel anzuzeigen, müssen wir es erst dort publizieren.

Die RCP UI kann auch personalisiert werden – um Dir zu erlauben, festzulegen an welcher Stelle Objekte in der Oberfläche erscheinen, sowie die Namen und Farben verschiedener Gruppen einzustellen. Um das Layout des RCP zu modifizieren musst Du zuerst vom "Working Mode" (die Standard RCP-Ansicht) in den "Edit Mode" umschalten. Du kannst diesen Bearbeitungsmodus erreichen, indem Du auf den grünen Bleistift in der oberen rechten Ecke des RCP klickst. Sobald Du im Bearbeitungsmodus bist, kannst Du neue UI-Gruppen erstellen, Elemente innerhalb der Gruppen neu ausrichten, Label hinzufügen, Farben ändern und vieles mehr. Um ein UI-Element zu löschen, ziehe es einfach über die Begrenzung des RCP hinaus. Du kannst die individuellen Werte der Parameter nicht ändern, solange Du Dich im Bearbeitungsmodus befindest. Stattdessen wirst Du wieder auf den grünen Bleistift klicken müssen, um in den ursprünglichen Arbeitsmodus zurückzukehren.

>_Das Remote Control Panel" hat zwei verschiedene Modi: Bearbeitungsmodus (links), der es Dir ermöglicht das Aussehen und die Handhabung des RCP anzupassen, und den Arbeitsmodus (rechts), in dem Du die eigentlichen Werte des UI bearbeiten kannst._
![IMAGE](images/1-1-3/1-1-3_008-remote2.png)
>Das "Remote Control Panel" im Bearbeitungsmodus hat einen orangenen Hintergrund.




#### 1.1.3.7. DATEI MANAGEMENT
Wenn Deine Grasshopperdatei Geometrien aus Rhino referenziert, musst Du dieselbe Datei in Rhino öffnen, damit die Definition funktioniert. Behalte Deine Dateien in einer organisierten Struktur, indem Du die Grasshopper- und Rhinodateien im selben Verzeichnis speicherst und ihnen Namen gibst, die in Beziehung zueinander stehen.

![IMAGE](images/1-1-3/1-1-3_009-file-management.png)
>1. Projektverzeichnis.
2. Rhinodatei.
3. Grasshopperdatei.

#### 1.1.3.8. TEMPLATES
Die Erstellung und Spezifizierungen einer Templatedatei mit Deinen Grasshopperpräferenzen ist ein angenehmer Weg, um neue Grasshopperdefinitionen auf Grundlage Deiner Voreinstellungen zu erzeugen. Das Template kann Grasshopperkomponenten, -paneele und -skizzen enthalten, um Deine Dokumentation zu erleichtern.


![IMAGE](images/1-1-3/1-1-3_010-templates.png)
>Erzeuge eine Templatedatei und speichere sie.

![IMAGE](images/1-1-3/1-1-3_011-templates2.png)
>1. Unter File/Preferences lade die Datei, die Du gerade als Template erstellt hast. Dein Template wird nun jedes Mal genutzt werden, wenn Du eine neue Datei erstellst.

