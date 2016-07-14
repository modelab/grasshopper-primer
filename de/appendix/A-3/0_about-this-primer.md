<style>
h5 {color:#008DB2}
.page-inner img {
clear: both;
float:left;
width:275px;
padding: 15px;
}
.test img{float:none}

</style>
## About This Primer

### Authors


![IMAGE](images/akos.png)
##### Gil Akos, Mode Lab
Gil Akos ist Gründungspartner und Direktor für Technologie bei Mode Lab, einer
multidisziplinären Designberatung spezialisiert auf technologierorientierter Prozessinnovation. 
Er bringt verschiedene professionelle Erfahrungen, technische Expertise in verschiedenen
digitalen Plattformen und eine Leidenschaft für generatives Entwerfen zum Servicemodell des Studios mit.
Seine persönlichen Interessen umgeben die Zusammenhänge zwischen Simulation und Materialisierung,
und Wege durch welche diese Verbindungen greifbar gemacht werden können.<br>
http://modelab.is<br>
http://modelab.is/education


![IMAGE](images/parsons.png)
##### Ronnie Parsons, Mode Lab
Ronnie Parsons ist Gründungspartner und Direktor für Ausbildung bei Mode Lab, einer
multidisziplinären Designberatung spezialisiert auf technologierorientierter Prozessinnovation. 
Bei Mode Lab identifiziert Ronnie neue Wege zur Verbindung und Konfiguration von
Arbeitsabläufen für Kunden durch die strategische Ausrichtung von Produktvision
mit UX-zentrierten Technologieplattformen. Ronnies Expertise befindet sich in den Feldern
fortgeschrittener Computermodelle, Konstruktionsanweisungen, Forschung und Entwicklung.<br>
http://modelab.is<br>
http://modelab.is/education


![IMAGE](images/modelab.png)
##### Mode Lab Team:
<ul>Sharon Jamison<br>
Andrew Reitz<br>
Armon Jahanshahi<br>
Luis Quinones<br>
Erick Katzenstein<br>
Kimberly Parsons<br>
Roberto Godinez<br>
Christopher Morse</ul>

### Beitragende


![IMAGE](images/payne.png)
##### Andrew Payne, Principal, Lift Architects
Andrew Payne ist ein registrierter Architekt, der LIFT architects 2007 gegründet hat. Andrews Arbeit erkundet eingebettete Informatik, intelligente Gebäude und generatives Entwerfen. Er hat wissenschaftliche Schriften publiziert und Workshops in Nordamerika, sowie in Europa gelehrt. Andrew und Jason K. Johnson haben 2010 Firefly veröffentlicht - ein umfassendes Plugin, welches die Grenzen zwischen Grasshopper, Arduino, dem Internet, audio/visuellen Werkzeugen und anderen Plattformen überwindet.<br>
http://www.liftarchitects.com/

---

Dieser Primer stellt einen umfassenden Leitfaden für die letzte Grasshopper build, version 0.90076, dar und beleuchtet, was wir als die spannendsten Erneuerungen empfinden. Es ist unser Ziel, dass dieser Primer als Führer für neue und bestehende Nutzer dient, welche ihre kreative Praxis in Verbindung mit Grasshopper erkunden.

![IMAGE](images/modelab_logo.png)
Mode Lab ist eine multidisziplinären Designberatung spezialisiert auf technologierorientierter Prozessinnovation.
Seit seiner Gründung war Mode Lab ein Ort zum Experimentieren mit Methoden und Technologien, welche zum Entwerfen und Gestalten der Welt um uns herum genutzt werden. Wir sind verpflichtet, Prozesse zur Materialisierung von Ideen zu verstehen und zu verbessern - auf diese Reise begeben wir uns in Zusammenarbeit mit unseren Kunden.
http://modelab.is

![IMAGE](images/modelab_education.png)
Unser Education brand stellt Blended-Learning-Lösungen für Konsumenten und Unternehmen zur Verfügung, die vorwärts kommen möchten. Wir entwerfen und entwickeln gezielte Lernerfahrungen, die den Lernenden ins Zentrum jeder Technik und Gestaltungsmethode stellen, die wir mit unserer Gemeinschaft teilen.
http://modelab.is/education

![IMAGE](images/rhino.png)
McNeel ist ein Unternehmen für Softwarentwicklung mit weltweitem Verkauf, Kundenservice und Training. Gegründet 1980, ist McNeel ein privat geführtes, sich im Mitarbeiterbesitz befindliches Unternehmen mit Verkaufs- und Kundenservicebüros, sowie Tochtergesellschaften in Seattle, Boston, Miami, Buenos Aires, Barcelona, Rome, Tokio, Taipei, Seoul, Kuala Lumpur und Shanghai mit mehr als 700 Weiterverkäufern, Verteilern, OEMs, and Trainingszentren rund um die Welt.
http://www.en.na.mcneel.com/

![IMAGE](images/grasshopper.png)
Für Entwerfer, die neue Formen mit generativen Algorithmen erkunden, gibt es Grasshopper als graphischen Algorithmeneditor integriert in  Rhino’s 3D Modellierwerkzeug. Im Unterschied zu RhinoScript benötigt Grasshopper kein Wissen über Programmierung oder Skripten, aber ermöglicht es dem Gestalter einfache sowie beeindruckende Generatoren zu erstellen.
http://www.grasshopper3d.com/



### LIZENZINFORMATION
Der Grasshopper Primer ist unter Creative Commons Attribution-NonCommercial-ShareAlike 3.0 Unported lizensiert. Der gesamte Text der Lizenz ist hier verfügbar: http://creativecommons.org/licenses/by-nc-sa/3.0/us/legalcode

Unter dieser Lizenz kannst Du:

**TO SHARE** - das Werk kopieren, verteilen und übertragen

**TO REMIX** - das Werk anpassen

Unter den folgenden Bedingungen:

**ATTRIBUTION** - Du musst das Werk wie unterhalb in “Mode Lab’s Attribution” spezifiziert benennen. Du kannst das Werk nicht auf eine Art und Weise zuordnen, die nahelegt, dass Mode Lab Dich oder Dein Werk befürwortet.

**NONCOMMERCIAL** - Du kannst dieses Werk nicht für kommerzielle Gründe verwenden.

**SHARE ALIKE** - Wenn Du das Werk anpasst, veränderst oder darauf aufbaust, kannst Du das resultierende Werk nur unter derselben Creative Commons Attribution-NonCommercial-ShareAlike 3.0 Unported license verbreiten.

Bitte schaue Dir den Volltext der Lizenz an (http://creativecommons.org/licenses/by-nc-sa/3.0/us/legalcode), um alle Rechte und Einschränkungen, die damit einhergehen, zu sehen.

**MODE LAB’S ATTRIBUTION:**
©2015 Studio Mode, LLC. All rights reserved. http://modelab.is

**TRANSLATIONS:**
Wenn Du übersetzte Versionen dieses Primers (in Übereinstimmung mit dieser Lizenz) erstellst, informiere bitte Mode Lab unter hello@modelab.is. Mode Lab kann wählen, solche übersetzte Versionen ebenfalls zu verteilen und/oder darauf zu verweisen (entweder in bestehendem Zustand, oder weiterentwickelt durch Mode Lab)
