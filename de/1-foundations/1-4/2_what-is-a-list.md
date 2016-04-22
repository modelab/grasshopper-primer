### 1.4.2. Was ist eine Liste?

#####Es ist hilfreich ueber Grasshopper in den Begriffen von Fluessen zu denken, da es eine graphische Benutzeroberflaeche zur Bewegung von Datenfluessen in bestimmte Komponenten ist. Es sind jedoch die Daten die den Informationsfluss in und aus bestimmten Typen von Komponenten bestimmen. Zu verstehen, wie Listen manipuliert werden ist kritisch im Verstaendnis des Grasshopper Plug-Ins.

Grundsaetzlich hat Grasshopper zwei Datentypen: persistente und volatile. Auch wenn die Datentypen verschiedene Charakteristika haben, speichert Grasshopper diese Daten typischerweise in einem Array, eine Liste von Variablen.

Wenn Daten in einer Liste gespeichert werden, ist es hilfreich zu wissen an welcher Postition in der Liste jedes Element gespeichert wurde, so dass wir beginnen koennen darauf zuzugreifen oder bestimmte Elemente zu bearbeiten. Die Position eines Elementes in der Liste wir Index genannt.

![IMAGE](images/1-4-2/1-4-2_001-list-index.png)
>1. Listenelement
2. Index

Das einzige, was zu beginn etwas ungewoehnlich aussieht ist, dass der erste Index einer Liste immer 0 ist und nicht 1. Deshalb beziehen wir uns immer auf den Index 0, wenn wir ueber das erste Element einer Liste reden.

Zum Beispiel, wenn wir die Finger an unserer rechten Hand zaehlen, stehen die Chancen gut, dass Du von 1 bis 5 gezaehlt hast. Jedoch in Bezug auf Listen, die in Arrays gespeichert sind, wuerde die Liste von 0 bis 4 gezaehlt. Merke, dass wir immer noch 5 Elemente in der Liste haben; es ist lediglich so, dass ein Array ein null-basiertes Zaehlsystem verwendet. Sie koennen jeden Datentyp enthalten, den Grasshopper unterstuetzt, wie Punkte, Kurven, Flaechen, Polygonnetze, etc.

Oft ist es die einfachste Art festzustellen, welcher Datentyp in einer Liste gespeichert ist, ein "Text Panel" (Params/Input/Panel) mit dem Ausgabeparameter der zu bestimmenden Komponente zu verbinden. Standardmaessig, wird das Textpaneel alle Indices an der linken Seite des Paneels anzeigen und die entsprechenden Daten auf der rechten Seite des Paneels. Die Indices werden ein entscheidendes Element, wenn wir beginnen mit Listen zu arbeiten. Du kannst die Indices an- und ausschalten, indem Du auf das Textpaneel rechtsklicks und dann auf das “Draw Indices” Element des Untermenus klickst. Momentan lassen wir die Indices erst mal fuer alle Textpaneele eingeschalten.

![IMAGE](images/1-4-2/1-4-2_002-list-menu.png)
