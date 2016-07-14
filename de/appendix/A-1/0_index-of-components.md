<style>
h4{color: #008DB2}
td {background-color:white; vertical-align:top}
td img{
display: block;
width: 100%;
max-width: 150px;
margin-left: auto;
margin-right: auto;
}
td:nth-child(1){width:150px;}
td:nth-child(2){width:500px;}
td:nth-child(3){
vertical-align:middle;
width:150px;
}
thead {display: none}
</style>

## 2.1. Index

##### Dieser Index stellt zusätzliche Informationen über alle Komponenten, die in diesem Primer verwendet werden, zur Verfügung und ergänzt diese mit weiteren Komponenten, die Du nützlich finden könntest. Hier findest Du eine Einführung in die Welt der über 500 Komponenten im Grasshopper Plugin.

--

#### Geometrie
||||
|--|--|--|
|<a name="PGCrv"></a>P.G.Crv|Curve Parameter<br>Stellt eine Sammlung von Kurvengeometrien dar. Kurvengeometrien sind der gemeinsame Nenner aller Kurvenarten in Grasshopper.|![IMAGE](images/PGCrv.png)|
|<a name="PGCircle"></a>P.G.Circle|Circle Parameter<br>Repräsentiert eine Sammlung von Kreisgeometrien.|![IMAGE](images/PGCircle.png)|
|<a name="PGGeo"></a>P.G.Geo|Geometry Parameter<br>Stellt eine Sammlung von Geometrien dar.|![IMAGE](images/PGGeo.png)|
|<a name="PGPipeline"></a>P.G.Pipeline|Geometry Pipeline<br>Definiert eine Pipeline für Geometrien von Rhino zu Grasshopper.|![IMAGE](images/PGPipeline.png)|
|<a name="PGPt"></a>P.G.Pt|Point Parameter<br>Punktparameter können persistente Daten speichern. Du kannst einen persistenten Eintrag durch das Parametermenü herstellen.|![IMAGE](images/PGPt.png)|
|<a name="PGSrf"></a>P.G.Srf|Surface Parameter<br>Stellt eine Kollektion von Flächengeometrien dar. Flächengeometrien sind der gemeinsame Nenner aller Flächenarten in Grasshopper.|![IMAGE](images/PGSrf.png)|

#### Grundparameter
||||
|--|--|--|
|<a name="PPBool"></a>P.P.Bool|Boolean Parameter<br>Stellt eine Sammlung von boolschen Werten (Wahr/Falsch) dar.|![IMAGE](images/PPBool.png)|
|<a name="PPD"></a>P.P.D|Domain Parameter<br>Repräsentiert eine Kollektion von eindimensionalen Intervallen. Intervalle werden typischerweise genutzt, um Kurvenfragmente und kontinuierliche numerische Bereiche darzustellen. Ein Intervall besteht aus zwei Zahlen, welche die jeweiligen Grenzen des Intervalls definieren. Der gesamte Bereich zwischen diesen Grenzen ist Teil des Intervalls.|![IMAGE](images/PPD.png)|
|<a name="PPD2"></a>P.P.D2|Domain<sup>2</sup> Parameter<br>Enthält eine Sammlung von zweidimensionalen Intervallen. 2D Intervalle werden typischerweise benutzt, um Flächenfragmente zu beschreiben. Ein zweidimensionales Intervall wird durch zwei eindimensionale Intervalle bestimmt|![IMAGE](images/PPD2.png)|
|<a name="PPID"></a>P.P.ID|Guid Parameter<br>Repräsentiert eine Sammlung von Globalen Einzigartigen Identifikatoren (Guid). Guid Parameter haben die Fähigkeit, persistente Daten zu speichern. Du kannst einen persistenten Eintrag durch das Parametermenü hinzufügen.|![IMAGE](images/PPID.png)|
|<a name="PPInt"></a>P.P.Int|Integer Parameter<br>Stellt eine Sammlung numerischer Integerwerte dar. Integerparameter können persistente Daten speichern. Du kannst einen persistenten Eintrag durch das Parametermenü hinzufügen.|![IMAGE](images/PPInt.png)|
|<a name="PPNum"></a>P.P.Num|Number Parameter<br>Stellt eine Kollektion von Fließkommawerten dar. Numerische Parameter können persistente Daten speichern. Du kannst einen persistenten Eintrag durch das Parametermenü hinzufügen.|![IMAGE](images/PPNum.png)|
|<a name="PPPath"></a>P.P.Path|File Path<br>Enthält eine Sammlung von Dateipfaden.|![IMAGE](images/PPPath.png)|

#### Eingabeparameter
||||
|--|--|--|
|<a name="PIToggle"></a>P.I.Toggle|Boolean Toggle<br>Boolscher Schalter (Wahr/Falsch).|![IMAGE](images/PIToggle.png)|
|<a name="PIButton"></a>P.I.Button|Button<br>Druckknopfobjekt mit zwei Werten. Wenn das Druckknopfobjekt gedrückt wird, sendet es einen Wahrwert, bevor es sich wieder auf Falsch zurücksetzt.|![IMAGE](images/PIButton.png)|
|<a name="PISwatch"></a>P.I.Swatch|Color Swatch<br>Das Muster ist eine spezielle Schnittstelle, die es ermöglicht, individuelle Farbwerte einfach einzustellen. Du kannst die Farben der Musterkomponente durch das Kontextmenü anpassen.|![IMAGE](images/PISwatch.png)|
|<a name="PIGrad"></a>P.I.Grad|Gradient Control<br>Gradienten ermöglichen es Dir, einen Farbverlauf in einem numerischen Intervall zu bestimmen. Als Standard wird das Einheitsintervall (0.0 ~ 1.0) verwendet, aber dieses kann durch die Eingabeparameter L0 und L1 angepasst werden. Du kannst einen weiteren Griff zur Anpassung der Farbe im Gradientenobjekt hinzufügen, indem Du sie von dem Farbrad an der linken oberen Ecke herunterziehst und den Wert des Griffes anpassen, indem Du ihn rechtsklickst.|![IMAGE](images/PIGrad.png)|
|<a name="PIGraph"></a>P.I.Graph|Graph Mapper<br>Graphmapperobjekte ermöglichen es Dir, einer Reihe von Zahlen neue Werte zuzuweisen. Als Standard werden die {x} und {y} Intervalle der Graphfunktion auf die Einheitsintervalle (0.0 ~ 1.0) bezogen, aber diese können innerhalb des Grapheditors angepasst werden. Graphmapper können eine einzelne Zuweisungsfunktion enthalten, welche durch ein Kontextmenü ausgewählt werden können. Graphen haben typischerweise zwei Griffe (kleine Kreise), welche zur Modifikation der Variablen herangezogen werden können, um die Graphfunktion graphisch zu bestimmen. Ein Graphmapperobjekt enthält zu Beginn keinen Graphen und gibt eine 1:1 Zuweisung für die eingegebenen Werte aus.|![IMAGE](images/PIGraph.png)|
|<a name="PISlider"></a>P.I.Slider|Number Slider<br>Ein Schieberegler ist ein spezielles Schnittstellenobjekt, das es ermöglicht individuelle numerische Werte schnell einzustellen. Du kannst die Werte und Eigenschaften durch ein Menü ändern, indem Du auf den Schieberegler doppelklickst. Schieberegler können länger oder kürzer dargestellt werden, indem Du die rechte Kante des Objektes nach rechts oder links ziehst. Merke, dass Schieberegler nur einen Ausgabeparameter (also keinen Eingabeparameter) haben.|![IMAGE](images/PISlider.png)|
|<a name="PIPanel"></a>P.I.Panel|Panel<br>Die Paneelkomponente wird für benutzerdefinierte Notizen und Textwerte genutzt. Sie ist typischerweise ein passives Element, das es erlaubt, Anmerkungen und Erklärungen in das Dokument einzufügen. Panelle können ihre Informationen auch aus anderen Quellen beziehen. Wenn Du einen Ausgabeparameter in ein Paneel einsteckst, kannst Du den Inhalt dieses Parameters in Echtzeit beobachten. Alle Daten in Grasshopper können auf diese Weise gesehen werden. Paneele können ihren Inhalt auch in eine Textdatei streamen.|![IMAGE](images/PIPanel.png)|
|<a name="PIList"></a>P.I.List|Value List<br>Stellt eine Liste von voreingestellten Werten zur Verfügung, aus welchen gewählt werden kann.|![IMAGE](images/PIList.png)|

#### Nützliches
||||
|--|--|--|
|<a name="P.U.Cin"></a>P.U.Cin|Cluster Input<br>Stellt einen Cluster Eingabeparameter dar.|![IMAGE](images/PUCin.png)|
|<a name="P.U.COut"></a>P.U.COut|Cluster Output<br>Stellt einen Cluster Ausgabeparameter dar.|![IMAGE](images/PUCOut.png)|
|<a name="P.U.Dam"></a>P.U.Dam|Data Dam<br>Verzoegert Daten auf ihrem Weg durch das Dokument.|![IMAGE](images/PUDam.png)|
|<a name="P.U.Jump"></a>P.U.Jump|Jump<br>Springt zwischen bestimmen Orten im Dokument.|![IMAGE](images/PUJump.png)|
|<a name="P.U.Viewer"></a>P.U.Viewer|Param Viewer<br>Eine Anzeige fuer Datenstrukturen.|![IMAGE](images/PUViewer.png)|
|<a name="P.U.Scribble"></a>P.U.Scribble|Scribble<br>Fuer schnelle Notizen.|![IMAGE](images/PUScribble.png)|

Mathematik
--

#### Intervalle
||||
|--|--|--|
|<a name="M.D.Bnd"></a>M.D.Bnd|Bounds<br>Erstellt ein numerisches Intervall, welches eine Liste von numerischen Werten umfasst.|![IMAGE](images/MDBnd.png)|
|<a name="M.D.Consec"></a>M.D.Consec|Consecutive Domains<br>Erstellt ein fortlaufendes Intervall aus einer Liste von Zahlen.|![IMAGE](images/MDConsec.png)|
|<a name="MDDom"></a>M.D.Dom|Construct Domain<br>Erstellt ein numerisches Intervall aus zwei Grenzwerten.|![IMAGE](images/MDDom.png)|
|<a name="MDDom2Num"></a>M.D.Dom2Num|Construct Domain²<br>Erstellt ein zweidimensionales Intervall aus vier Zahlen.|![IMAGE](images/MDDom2Num.png)|
|<a name="MDDeDomain"></a>M.D.DeDomain|Deconstruct Domain<br>Zerlegt ein numerisches Intervall in seine Bestandteile.|![IMAGE](images/MDDeDomain.png)|
|<a name="MDDeDom2Num"></a>M.D.DeDom2Num|Deconstruct Domain²<br>Zerlegt ein zweidimensionales Intervall in vier Zahlen.|![IMAGE](images/MDDeDom2Num.png)|
|<a name="MDDivide"></a>M.D.Divide|Divide Domain²<br>Teilt ein zweidimensionales Intervall in gleichgroße Teile.|![IMAGE](images/MDDivide.png)|
|<a name="MDInc"></a>M.D.Inc|Includes<br>Testet einen numerischen Wert auf seine Zugehörigkeit zu einem Intervall.|![IMAGE](images/MDInc.png)|
|<a name="MDReMap"></a>M.D.ReMap|Remap Numbers<br>Zuweisung von Zahlen in ein neues numerisches Intervall.|![IMAGE](images/MDReMap.png)|


#### Operatoren
||||
|--|--|--|
|<a name="MOAdd"></a>M.O.Add|Addition<br>Mathematische Addition.|![IMAGE](images/MOAdd.png)|
|<a name="MODiv"></a>M.O.Div|Division<br>Mathematische Division.|![IMAGE](images/MODiv.png)|
|<a name="MOEquals"></a>M.O.Equals|Equality<br>Testet die (Un)gleichheit zweier Zahlen.|![IMAGE](images/MOEquals.png)|
|<a name="MOAnd"></a>M.O.And|Gate And<br>Führt eine boolsche Konjunktion (AND Gatter) aus. Beide Eingabeparameter müssen Wahr sein, um Wahr als Ergebnis der Operation zu erhalten.|![IMAGE](images/MOAnd.png)|
|<a name="MONot"></a>M.O.Not|Gate Not<br>Führt eine boolsche Negation (NOT Gatter) aus.|![IMAGE](images/MONot.png)|
|<a name="MOOr"></a>M.O.Or|Gate Or<br>Führt eine boolsche Disjunktion (OR Gatter) aus. Nur ein einzelner Eingabeparameter muss den Wert Wahr enthalten, um Wahr als Ergebnis der Operation zu erhalten.|![IMAGE](images/MOOr.png)|
|<a name="MOLarger"></a>M.O.Larger|Larger Than<br>Größer (oder gleich).|![IMAGE](images/MOLarger.png)|
|<a name="MOMultiply"></a>M.O.Multiply|Multiplication<br>Mathematische Multiplikation.|![IMAGE](images/MOMultiply.png)|
|<a name="MOSmaller"></a>M.O.Smaller|Smaller Than<br>Kleiner oder gleich).|![IMAGE](images/MOSmaller.png)|
|<a name="MOSimilar"></a>M.O.Similar|Similarity<br>Testet die Ähnlichkeit zweier Zahlen.|![IMAGE](images/MOSimilar.png)|
|<a name="MOSub"></a>M.O.Sub|Subtraction<br>Mathematische Subtraktion.|![IMAGE](images/MOSub.png)|

#### Skripten
||||
|--|--|--|
|<a name="MSEval"></a>M.S.Eval|Evaluate<br>Wertet eine Funktion mit einer flexiblen Zahl als Variable aus.|![IMAGE](images/MSEval.png)|
|<a name="MSExpression"></a>M.S.Expression|Expression<br>Wertet einen mathematischen Ausdruck aus.|![IMAGE](images/MSExpression.png)|

#### Trigonometrie
||||
|--|--|--|
|<a name="MTCos"></a>M.T.Cos|Cosine<br>Berechnet den Kosinuswert.|![IMAGE](images/MTCos.png)|
|<a name="MTDeg"></a>M.T.Deg|Degrees<br>Rechnet einen Winkel von Bogenmaß zu Grad um.|![IMAGE](images/MTDeg.png)|
|<a name="MTRad"></a>M.T.Rad|Radians<br>Rechnet einen Winkel von Grad zu Bogenmaß um.|![IMAGE](images/MTRad.png)|
|<a name="MTSin"></a>M.T.Sin|Sine<br>Berechnet den Sinuswert.|![IMAGE](images/MTSin.png)|

#### Nützliches
||||
|--|--|--|
|<a name="MUAvr"></a>M.U.Avr|Average<br>Berechnet den arithmetrischen Durchschnitt für einen Satz von Objekten.|![IMAGE](images/MUAvr.png)|
|<a name="MUPhi"></a>M.U.Phi|Golden Ratio<br>Gibt ein vielfaches des Goldenen Schnittes (Phi) aus.|![IMAGE](images/MUPhi.png)|
|<a name="MUPi"></a>M.U.Pi|Pi<br>Gibt ein Vielfaches von Pi aus.|![IMAGE](images/MUPi.png)|

Sets
--

#### Listen
||||
|--|--|--|
|<a name="SLCombine"></a>S.L.Combine|Combine Data<br>Kombiniere nicht-null Elemente verschiedener Eingabeparameter.|![IMAGE](images/SLCombine.png)|
|<a name="SLCrossRef"></a>S.L.CrossRef|Cross Reference<br>Datenquerverweise von verschiedenen Listen.|![IMAGE](images/SLCrossRef.png)|
|<a name="SLDispatch"></a>S.L.Dispatch|Dispatch<br>Verteile die Elemente einer Liste in zwei Ziellisten. Diese Komponente funktioniert sehr ähnlich wie die [Cull Pattern] Komponente, mit der Ausnahme, dass beide Listen als Ausgabe zur Verfügung stehen.|![IMAGE](images/SLDispatch.png)|
|<a name="SLIns"></a>S.L.Ins|Insert Items<br>Füge eine Sammlung von Elementen in eine Liste ein.|![IMAGE](images/SLIns.png)|
|<a name="SLItem"></a>S.L.Item|List Item<br>Beziehe ein bestimmtes Element aus einer Liste.|![IMAGE](images/SLItem.png)|
|<a name="SLLng"></a>S.L.Lng|List Length<br>Messe die Länge einer Liste. Elemente in einer Liste werden durch ihren Index eindeutig bezeichnet. Das erste Element wird unter dem Index 0 gespeichert, das zweite Element unter dem Index 1 und so weiter. Der höchst mögliche Index in einer Liste entspricht der Listenlänge minus eins.|![IMAGE](images/SLLng.png)|
|<a name="SLLong"></a>S.L.Long|Longest List<br>Erweitere eine Sammlung von Listen zur längsten Länge der Listen.|![IMAGE](images/SLLong.png)|
|<a name="SLSplit"></a>S.L.Split|Split List<br>Teile eine Liste in Teillisten.|![IMAGE](images/SLSplit.png)|
|<a name="SLReplace"></a>S.L.Replace|Replace Items<br>Ersetze bestimmte Elemente einer Liste.|![IMAGE](images/SLReplace.png)|
|<a name="SLRev"></a>S.L.Rev|Reverse List<br>Kehre die Reihenfolge einer Liste um. Der neue Index eines jeden Elementes wird N-i sein, wobei N der höchste Index in der Liste und i der ursprüngliche Index der Elemente ist.|![IMAGE](images/SLRev.png)|
|<a name="SLShift"></a>S.L.Shift|Shift List<br>Versetze alle Elemente einer Liste. Elemente in der Liste werden auf das Ende der Liste zu versetzt, wenn der angegebene Wert für den Versatz positiv ist. Wenn der Wert für Wrap auf Wahr steht, dann werden Elemente, die an den Enden der Liste entfallen, am anderen Ende wieder angehängt.|![IMAGE](images/SLShift.png)|
|<a name="SLShort"></a>S.L.Short|Shortest List<br>Verkürze eine Sammlung von Listen auf die Länge der kürzesten unter ihnen.|![IMAGE](images/SLShort.png)|
|<a name="SLSift"></a>S.L.Sift|Sift Pattern<br>Siebe Elemente einer Liste durch die Verwendung eines wiederholenden Muster auf Basis der Indices.|![IMAGE](images/SLSift.png)|
|<a name="SLSort"></a>S.L.Sort|Sort List<br>Sortiere eine Liste numerischer Werte. Damit etwas sortiert werden kann, muss es zuerst vergleichbar sein. Die meisten Arten von Daten sind nicht vergleichbar; Zahlen und Buchstabenfolgen sind grundsätzlicherweise die einzigen Ausnahmen. Falls Du andere Datentypen, wie z.B. Kurven, sortieren willst, musst Du zuerst eine Liste von Werten erzeugen, auf deren Basis die Sortierung erfolgen kann.|![IMAGE](images/SLSort.png)|
|<a name="SLWeave"></a>S.L.Weave|Weave<br>Webe mehrere Eingabedatensätze auf Basis eines benutzerdefinierten Musters. Das Muster wird bestimmt durch eine Liste von Indexwerten, die bestimmen in welcher Reihenfolge die Eingabedaten gewählt werden.|![IMAGE](images/SLWeave.png)|

#### Datensätze
||||
|--|--|--|
|<a name="SSCulli"></a>S.S.Culli|Cull Index<br>Entferne Indexelemente von einer Liste.|![IMAGE](images/SSCulli.png)|
|<a name="SSCull"></a>S.S.Cull|Cull Pattern<br>Entferne Elemente von einer Liste auf Grundlage einer Bitmaske. Die Bitmaske wird durch eine Liste boolscher Werte definiert. Sie wird wiederholt, bis alle Elemente des Datensatzes ausgewertet wurden.|![IMAGE](images/SSCull.png)|
|<a name="SSDup"></a>S.S.Dup|Duplicate Data<br>Dupliziere Daten auf Grundlage einer definierten Zahl. Die Daten können auf zwei Arten dupliziert werden. Entweder sie werden als Kopien der Eingabeliste an das Ende der Liste angehängt, bis die bestimmte Anzahl von Kopien erreicht wurden, oder jedes Element wird entsprechend of an der Stelle dupliziert, bis zum nächsten Element weitergegeangen wird.|![IMAGE](images/SSDup.png)|
|<a name="SSJitter"></a>S.S.Jitter|Jitter<br>Mischt die Werte einer Liste auf zufällige Weise. Die Eingabeliste wird auf Grundlage von Weißen Rauschen neu geordnet. Mischen ist ein guter Weg, um eine zufällige Verteilung der Werte zu erreichen. Der Jitter Parameter legt den Radius des Weißen Rauschens fest. Wenn der Jitterwert 0.5 entspricht, dann wird jedes Element zufällig innerhalb der halben Spanne des gesamten Datensatzes neu angeordnet.|![IMAGE](images/SSJitter.png)|
|<a name="SSRandom"></a>S.S.Random|Random<br>Generiert eine Liste pseudozufälliger Zahlen, die Sequenz der Zahlen ist einzigartig aber stabil für jeden Seedwert. Wenn Du eine bestimmte zufällige Verteilung nicht magst, probiere verschiedene Werte als Seed.|![IMAGE](images/SSRandom.png)|
|<a name="SSRange"></a>S.S.Range|Range<br>Erstelle eine Reihe von Zahlen. Die Zahlen werden gleichförmig innerhalb des numerischen Intervalls verteilt. Nutze diese Komponente, wenn Du Zahlen zwischen zwei Extremen erzeugen möchtest. Wenn Du Kontrolle über den Abstand zwischen den Werten möchtest, bist Du mit der [Series] Komponente besser beraten.|![IMAGE](images/SSRange.png)|
|<a name="SSRepeat"></a>S.S.Repeat|Repeat Data<br>Wiederhole ein Datenmuster, bis er eine bestimmte Länge erreicht.|![IMAGE](images/SSRepeat.png)|
|<a name="SSSeries"></a>S.S.Series|Series<br>Erstelle eine Serie von Werten. Die Werte sind gleichmäßig auf Grundlage des {Step} Wertes verteilt. Wenn Du Zahlen innerhalb eines bestimmten numerischen Intervalls verteilen willst, wähle stattdessen die [Range] Komponente.|![IMAGE](images/SSSeries.png)|

#### Datenbäume
||||
|--|--|--|
|<a name="STExplode"></a>S.T.Explode|Explode Tree<br>Extrahiert alle Äste aus einem Datenbaum.|![IMAGE](images/STExplode.png)|
|<a name="STFlatten"></a>S.T.Flatten|Flatten Tree<br>Ebnet einen Datenbaum ein, indem alle Verzweigungsinformationen entfernt werden.|![IMAGE](images/STFlatten.png)|
|<a name="STFlip"></a>S.T.Flip|Flip Matrix<br>Drehe einen matrixähnlichen Datenbaum, indem Zeilen und Spalten vertauscht werden.|![IMAGE](images/STFlip.png)|
|<a name="STGraft"></a>S.T.Graft|Graft Tree<br>Typischerweise werden Datenobjekte in Ästen mit einem spezifischen Wert gespeichert (0 für das erste Element, 1 für das zweite Element, usw.) und Äste werden in Datenbäumen an bestimmten Astpfaden gespeichert, z.B.: {0;1}, welches den zweiten Unterast im ersten Hauptast bezeichnet. Aufpfropfen erstellt einen neuen Ast für jedes Datenobjekt.|![IMAGE](images/STGraft.png)|
|<a name="STMerge"></a>S.T.Merge|Merge<br>Verschmelze verschiedene Datenströme.|![IMAGE](images/STMerge.png)|
|<a name="STPath"></a>S.T.Path|Path Mapper<br>Führe lexikale Operationen für die Datenbäume aus. Lexikale Operationen sind logische Zuordnungen zwischen Datenpfaden und -indizes, welche durch textbasierte (lexikale) Masken oder Muster definiert werden.|![IMAGE](images/STPath.png)|
|<a name="STPrune"></a>S.T.Prune|Prune Tree<br>Entferne alle Äste aus einem Datenbaum, die eine bestimmte Anzahl von Datenelementen beinhalten. Du kannst eine untere und eine obere Grenze für das Beschneiden des Datenbaumes bestimmen.|![IMAGE](images/STPrune.png)|
|<a name="STSimplify"></a>S.T.Simplify|Simplify Tree<br>Vereinfache einen Datenbaum, indem die Überlappungen zwischen den verschiedenen Ästen entfernt werden.|![IMAGE](images/STSimplify.png)|
|<a name="STTStat"></a>S.T.TStat|Tree Statistics<br>Beziehe einige Statistiken bezüglich des Datenbaums.|![IMAGE](images/STTStat.png)|
|<a name="STUnflatten"></a>S.T.Unflatten|Unflatten Tree<br>Revidiere die Einebnung eines Datenbaumes, indem die verschiedenen Elemente zurück in die Äste verschoben werden.|![IMAGE](images/STUnflatten.png)|

Vector
--

#### Raster
||||
|--|--|--|
|<a name="VGHexGrid"></a>V.G.HexGrid|Hexagonal<br>2D Raster mit hexagonalen Zellen.|![IMAGE](images/VGHexGrid.png)|
|<a name="VGRecGrid"></a>V.G.RecGrid|Rectangular<br>2D Raster mit rechteckigen Zellen.|![IMAGE](images/VGRecGrid.png)|
|<a name="VGSqGrid"></a>V.G.SqGrid|Square<br>2D Raster mit quadratischen Zellen|![IMAGE](images/VGSqGrid.png)|

#### Punkt
||||
|--|--|--|
|<a name="VPPt"></a>V.P.Pt|Construct Point<br>Konstruiere einen Punkt aus {xyz} Koordinaten.|![IMAGE](images/VPPt.png)|
|<a name="VPpDecon"></a>V.P.pDecon|Deconstruct<br>Zerlege einen Punkt in seine Bestandteile.|![IMAGE](images/VPpDecon.png)|
|<a name="VPDist"></a>V.P.Dist|Distance<br>Berechne den euklidischen Abstand zwischen zwei Punktkoordinaten.|![IMAGE](images/VPDist.png)|

#### Vektor
||||
|--|--|--|
|<a name="VVX"></a>V.V.X|Unit X<br>Einheitsvektor parallel der Welt {x} Achse.|![IMAGE](images/VVX.png)|
|<a name="VVY"></a>V.V.Y|Unit Y<br>Einheitsvektor parallel der Welt {Y} Achse.|![IMAGE](images/VVY.png)|
|<a name="VVVec2Pt"></a>V.V.Vec2Pt|Vector 2Pt<br>Erstelle einen Vektor zwischen zwei Punkten.|![IMAGE](images/VVVec2Pt.png)|

Kurve
--

#### Analyse
||||
|--|--|--|
|<a name="CACP"></a>C.A.CP|Control Points<br>Extrahiere die NURBS Kontroll- und Knotenpunkte aus einer Kurve.|![IMAGE](images/CACP.png)|

#### Division
||||
|--|--|--|
|<a name="CDDivide"></a>C.D.Divide|Divide Curve<br>Teile eine Kurve in gleichlange Segmente.|![IMAGE](images/CDDivide.png)|

#### Grundparameter
||||
|--|--|--|
|<a name="CPCir"></a>C.P.Cir|Circle<br>Erstelle einen Kreis definiert durch eine Grundebene und einen Radius.|![IMAGE](images/CPCir.png)|
|<a name="CPCir3Pt"></a>C.P.Cir3Pt|Circle 3Pt<br>Erstelle einen Kreis definiert durch drei Punkte.|![IMAGE](images/CPCir3Pt.png)|
|<a name="CPCirCNR"></a>C.P.CirCNR|Circle CNR<br>Erstelle einen Kreis definiert durch Zentrum, Normale und Radius.|![IMAGE](images/CPCirCNR.png)|
|<a name="CPLine"></a>C.P.Line|Line SDL<br>Erstelle ein Liniensegment definiert durch Startpunkt, Richtung und Länge.|![IMAGE](images/CPLine.png)|
|<a name="CPPolygon"></a>C.P.Polygon|Polygon<br>Erstelle ein Polygon mit optional gerundeten Kanten.|![IMAGE](images/CPPolygon.png)|

#### Spline
||||
|--|--|--|
|<a name="CSIntCrv"></a>C.S.IntCrv|Interpolate<br>Erstelle eine interpolierte Kurve durch einen Satz von Punkten.|![IMAGE](images/CSIntCrv.png)|
|<a name="CSKinkCrv"></a>C.S.KinkCrv|Kinky Curve<br>Konstruiere eine interpolierte Kurve durch einen Satz von Punkten mit einem Schwellenwert für den Knickwinkel.|![IMAGE](images/CSKinkCrv.png)|
|<a name="CSNurbs"></a>C.S.Nurbs|Nurbs Curve<br>Konstruiere eine NURBS Kurve aus Kontrollpunkten.|![IMAGE](images/CSNurbs.png)|
|<a name="CSPLine"></a>C.S.PLine|PolyLine<br>Erstelle eine Polylinie, indem Du eine Anzahl von Punkten miteinander verbindest.|![IMAGE](images/CSPLine.png)|

#### Nützliches
||||
|--|--|--|
|<a name="CUExplode"></a>C.U.Explode|Explode<br>Zerteile eine Kurve in kleinere Segmente.|![IMAGE](images/CUExplode.png)|
|<a name="CUJoin"></a><C.U.Join|Join Curves<br>Verbinde so viele Kurven wie möglich.|![IMAGE](images/CUJoin.png)|
|<a name="CUOffset"></a>C.U.Offset|Offset<br>Versetze eine Kurve basierend auf einer definierten Distanz.|![IMAGE](images/CUOffset.png)|

Flächen
--

#### Analyse
||||
|--|--|--|
|<a name="SADeBrep"></a>S.A.DeBrep|Deconstruct Brep<br>Zerlege Polygonflächen in ihre Bestandteile.|![IMAGE](images/SADeBrep.png)|


#### Freiform
||||
|--|--|--|
|<a name="SFBoundary"></a>S.F.Boundary|Boundary Surfaces<br>Erstelle eine planare Fläche aus einer Sammlung von Begrenzungskurven.|![IMAGE](images/SFBoundary.png)|
|<a name="SFExtr"></a>S.F.Extr|Extrude<br>Extrudiere Kurven und Flächen entlang eines Vektors.|![IMAGE](images/SFExtr.png)|
|<a name="SFExtrPt"></a>S.F.ExtrPt|Extrude Point<br>Extrudiere Kurven und Flächen auf einen Punkt zu.|![IMAGE](images/SFExtrPt.png)|
|<a name="SFLoft"></a>S.F.Loft|Loft<br>Erstelle eine Loftfläche aus einer Reihe von Schnittkurven.|![IMAGE](images/SFLoft.png)|
|<a name="SFRevSrf"></a>S.F.RevSrf|Revolution<br>Erstelle eine Rotationsfläche.|![IMAGE](images/SFRevSrf.png)|
|<a name="SFSwp2"></a>S.F.Swp2|Sweep2<br>Erstelle eine Sweepfläche entlang zweier Leitkurven.|![IMAGE](images/SFSwp2.png)|

#### Grundkörper
||||
|--|--|--|
|<a name="SPBBox"></a>S.P.BBox|Bounding Box<br>Erstelle eine Begrenzungskiste entlang einer orientierten Geometrie.|![IMAGE](images/SPBBox.png)|

#### Nützliches
||||
|--|--|--|
|<a name="SUSDivide"></a>S.U.SDivide|Divide Surface<br>Generiere ein Raster von {uv} Punkten auf einer Fläche.|![IMAGE](images/SUSDivide.png)|
|<a name="SUSubSrf"></a>S.U.SubSrf|Isotrim<br>Extrahiere eine isoparametrische Untermenge einer Fläche.|![IMAGE](images/SUSubSrf.png)|

Polygonnetz
--

#### Triangulation
||||
|--|--|--|
|<a name="MTVoronoi"></a>M.T.Voronoi|Voronoi<br>Planares Voronoidiagramm aus einer Sammlung von Punkten.|![IMAGE](images/MTVoronoi.png)|

Transformation
--

#### Affine
||||
|--|--|--|
|<a name="TARecMap"></a>T.A.RecMap|Rectangle Mapping<br>Transformiere eine Geometrie von einem Rechteck zu einem anderen.|![IMAGE](images/TARecMap.png)|

#### Anordnung
||||
|--|--|--|
|<a name="TAArrLinear"></a>T.A.ArrLinear|Linear Array<br>Erstelle eine lineare Anordnung von Geometrien.|![IMAGE](images/TAArrLinear.png)|

#### Morph
||||
|--|--|--|
|<a name="TMMorph"></a>T.M.Morph|Box Morph<br>Morphe ein Objekt in eine verzerrte Kiste.|![IMAGE](images/TMMorph.png)|
|<a name="TMSBox"></a>T.M.SBox|Surface Box<br>Erstelle eine verzerrte Kiste auf einem Flächenabschnitt.|![IMAGE](images/TMSBox.png)|

Anzeige
--

#### Farbe
||||
|--|--|--|
|<a name="DCHSL"></a>D.C.HSL|Colour HSL<br>Erstelle eine Farbe aus Fließkomma {HSL} Kanälen.|![IMAGE](images/DCHSL.png)|

#### Dimensionen
||||
|--|--|--|
|<a name="DDTag"></a>D.D.Tag|Text tags<br>Eine Textschildkomponente ermöglicht es Dir einen kurzen String als Anzeigeelement im Ansichtsfenster darzustellen. Text und Position werden durch die Eingabeparameter bestimmt. Wenn Textschilder gebacken werden, werden sie zu Textpunkten.|![IMAGE](images/DDTag.png)|
|<a name="DDTag3D"></a>D.D.Tag3D|Text Tag 3D<br>Stellt eine Liste von 3D Textschildern im Rhinoansichtsfenster dar|![IMAGE](images/DDTag3D.png)|

#### Vorschau
||||
|--|--|--|
|<a name="DPPreview"></a>D.P.Preview|Custom Preview<br>Erlaubt eine benutzerdefinierte Vorschau für Geometrien.|![IMAGE](images/DPPreview.png)|

#### Vektor
||||
|--|--|--|
|<a name="DVPoints"></a>D.V.Points|Point List<br>Zeigt Details zu Punktlisten an.|![IMAGE](images/DVPoints.png)|


