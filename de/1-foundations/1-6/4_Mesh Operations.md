### 1.6.4 Polygonnetzoperationen

##### Im letzten Abschnitt haben wir die grundlegende Struktur von Polygonnetzen angeschaut. In diesem Abschnitt werden wir Wege ansehen, wie man Polygonnetzgeometrien manipulieren kann.

#### 1.6.4.1 Glättung

![IMAGE](images/1-6-4/smooth.png)

Glattere Polygonnetze können erreicht werden, indem die Anzahl der Netzflächen erhöht wird. Dieser Prozess wird *Unterteilung* genannt. Dies kann oft zu sehr großen Datensätzen führen, welche viel Rechenzeit und zusätzliche Erweiterungen für Grasshopper benötigen. In dieser Situation kann die **Smooth** Komponente als Alternative genutzt werden, um weniger facettierte Polygonnetze zu erzeugen ohne die Anzahl der Eckpunkte und Netzflächen zu erhöhen oder die Topologie zu verändern. Die *Stärke*, *Anzahl der Iterationen* und *Versatzbegrenzung* können genutzt werden, um die Art zu beeinflussen, in der die Glättung passiert.

Verbindung eines boolschen Wertes mit einem Eingabeparameter N gibt uns die Option freie Eckpunkte zu überspringen. Eckpunkte sind frei, wenn sie mit einer offenen Kante verbunden sind, mit der Bedeutung, dass sie sich in der äußeren Begrenzung des Polygonnetzes befindet. Indem Du diese Option einschaltest, kannst Du die äußeren Begrenzungen eines Polygonnetzes erhalten, während Du die inneren Kanten des Polygonnetzes glättest.

![IMAGE](images/1-6-4/03_smooth.png)
>1. Ursprüngliches Polygonnetz einer Kiste mit drei Netzflächen entfernt
2. Glättung nach 2 Iterationen
3. 6 Iterationen
4. 25 Iterationen
5. 50 Iterationen

#### 1.6.4.2 Unschärfe

![IMAGE](images/1-6-4/blur.png)

Die **Blur** Komponente verhält sich ähnlich wie die "Smooth" Komponente, abgesehen von den Eckpunktfarben. Es kann auch benutzt werden, um die gezackte Erscheinung von Farbpolygonnetzen weichzuzeichnen, auch wenn der Effekt geringer ist, da die Geometrie nicht verändert wird.

![IMAGE](images/1-6-4/04_blur.png)
>1. Ursprüngliches Polygonnetz
2. Weichzeichnen nach 1 Iteration
3. 6 Iterationen
4. 12 Iterationen
5. 20 Iterationen

#### 1.6.4.3 Triangulierung

![IMAGE](images/1-6-4/triangulate.png)

Um die Planarität einer jeden Netzfläche zu sichern oder um das Polygonnetz zu anderen Programmen zu exportieren, die keine viereckigen Netzflächen erlauben, ist es manchmal nötig ein Polygonnetz zu triangulieren. Mit der Nutzung der **Triangulate** Komponente, wird jede viereckige Netzfläche durch zwei dreieckige ersetzt. Grasshopper nimmt immer die kürzeste Diagonale der Netzfläche, um eine Netzfläche mit einer neuen Kante zu unterteilen.

![IMAGE](images/1-6-4/05_triangulate.png)
>1. Ursprüngliches Polygonnetz mit viereckigen Netzflächen
2. Hinzugefügte Kanten in Übereinstimmung mit der kürzesten Distanz zwischen viereckigen Netzflächen
3. Trianguliertes Polygonnetz als Ergebnis

#### 1.6.4.4 Schweißen

![IMAGE](images/1-6-4/weld.png)

Im letzten Abschnitt haben wir festgestellt, dass ein einzelner Eckpunkt von benachbarten Netzflächen geteilt werden kann und dass die Normale für diesen Eckpunkt aus dem Durchschnitt der Normalen der angrenzenden Netzflächen berechnet wird, was eine glattere Darstellung ergibt. Manchmal ist es jedoch gewünscht, dass eine scharfe Kante oder ein Saum erzeugt werden, an welchen ein glatter Übergang zwischen einer Netzfläche und der benachbarten nicht stattfinden soll. In dieser Situation ist es notwendig für jede Netzfläche an einem Schnittpunkt eine eigene Exkpunktnormale zu definieren. Die Liste von Eckpunkten würde mindestens zwei Punkte enthalten, die eine Koordinate teilen aber verschiedene Indizes besitzen.

![IMAGE](images/1-6-4/06_simple-weld.png)
>1. Verschweißte Netzfläche - Beide Netzflächen teilen die Eckpunke 1 und 2. Die Eckpunktnormalen an diesen Eckpunkten entsprechen dem Durchschnitt der Netzflächennormalen der angrenzenden Netzflächen.
2. Unverschweißte Netzfläche - Duplizierte Eckpunkte wurden der Liste hinzugefügt. Eckpunkte 1 und 6 und Eckpunkte 2 und 5 haben identische Koordinaten, aber unterschiedliche Eckpunkte. Sie haben jeweils ihre eigenen Eckpunktnormalen. Der Prozess zwei Eckpunkte in derselben Position zu nehmen und sie zu einem gemeinsamen Eckpunkt zusammenzuführen nennen wir *schweißen*, wobei *entschweißen* bedeutet einen einzelnen Eckpunkt in mehrere Eckpunkte zu teilen.

Die **Weld** Komponente nutzt einen Grenzwinkel als Eingabeparameter. Alle benachbarten Netzflächen mit einem eingeschlossenen Winkel kleiner dem Grenzwinkel werden miteinander verschweißt, wodurch gemeinsame Eckpunkte mit geteilten Eckpunktnormalen entstehen, die die Werte der angrenzenden Flächennormalen mitteln. **Unweld** funktioniert auf die entgegengesetzte Art und Weise, in der angrenzende Netzflächen mit einem Winkel größer dem Grenzwinkel entschweißt werden und die bisher geteilten Eckpunkte dupliziert werden.

![IMAGE](images/1-6-4/07_box-weld.png)
>1. Die Standardpolygonnetzkiste hat 726 Eckpunkte. Das Polygonnetz ist an den Ecken der Kiste gekantet und die Eckpunkte an den angrenzenden Eckpunkten sind dupliziert.
2. Wenn das Polygonnetz mit einem Winkel größer als 90 Grad verschweißt wird, werden die Netzflächen alle verschweißt und die Anzahl der Endpunkte wurde auf 602 reduziert, während die Anzahl der Netzflächen dieselbe bleibt.
3. Wenn wir uns die Vorschaugeometrie ansehen, können wir auch feststellen, dass das gerenderte verschweißte Polygonnetz geglättete Ecken hat.
4. Entgegen der "Smooth" Komponente, welche die Polygonnetzgeometrie verändert, wirkt dieses Polygonnetz nur geglättet, weil die Eckpunktnormalen eine Rolle in Rendering und Schattierung spielen. Die eigentliche Position der Eckpunkte bleibt unverändert.

Im oben gezeigten Bild haben wir einen Winkel von 91 Grad angenommen, weil wir wissen, dass die Seiten eines Quadrats 90 Grad Winkel enthalten. Um ein Polygonnetz vollständig zu verschweißen solltest Du einen Winkel von 180 Grad angeben.