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

## 2.1. Индекс

#####Этот индекс содержит дополнительную информацию по всем компонентам, использованным в этом пособии, а также другие компоненты, которые могут оказаться вам полезными. Это небольшое введение в более чем 500 компонентов в плагине Grasshopper.

Параметры
--

####Geometry
||||
|--|--|--|
|<a name="PGCrv"></a>P.G.Crv|Curve Parameter<br>Представляет набор геометрии Curve (кривая). Геометрия Curve - это общий знаменатель всех типов кривых в Grasshopper.|![IMAGE](images/PGCrv.png)|
|<a name="PGCircle"></a>P.G.Circle|Circle Parameter<br>Представляет набор примитивов Circle (круг).|![IMAGE](images/PGCircle.png)|
|<a name="PGGeo"></a>P.G.Geo|Geometry Parameter<br>Представляет набор 3D геометрии.|![IMAGE](images/PGGeo.png)|
|<a name="PGPipeline"></a>P.G.Pipeline|Geometry Pipeline<br>Определяет геометрию pipeline из Rhino в Grasshopper.|![IMAGE](images/PGPipeline.png)|
|<a name="PGPt"></a>P.G.Pt|Point Parameter<br>Параметр Point (точка) способен хранить постоянные данные. Вы можете настроить запись постоянных данных через меню Parameter.|![IMAGE](images/PGPt.png)|
|<a name="PGSrf"></a>P.G.Srf|Surface Parameter<br>Представляет набор геометрии Surface (поверхность). Surface геометрия - это общий знаменатель всех типов поверхности в Grasshopper.|![IMAGE](images/PGSrf.png)|

####Primitive
||||
|--|--|--|
|<a name="PPBool"></a>P.P.Bool|Boolean Parameter<br>Представляет набор Булевых значений (Правда/Ложь).|![IMAGE](images/PPBool.png)|
|<a name="PPD"></a>P.P.D|Domain Parameter<br>Представляет набор одно-пространственных Диапазонов. Диапазоны обычно используются для представления фрагментов кривых и длительных числовых диапазонов. Диапазон состоит из двух чисел, которые показывают ограничения диапазона, все, что между этими числами является частью диапазона.|![IMAGE](images/PPD.png)|
|<a name="PPD2"></a>P.P.D2|Domain<sup>2</sup> Parameter<br>Содержит набор двух-пространственных диапазонов. 2D диапазоны обычно используются для представления фрагментов поверхности. Двух-пространственный диапазон состоит из двух одно-пространственных диапазонов.|![IMAGE](images/PPD2.png)|
|<a name="PPID"></a>P.P.ID|Guid Parameter<br>Представляет набор Globally Unique Identifiers (глобально уникальных идентификаторов). Параметры Guid способны хранить постоянные данные. Вы можете настроить запись постоянных данных через меню Parameter.|![IMAGE](images/PPID.png)|
|<a name="PPInt"></a>P.P.Int|Integer Parameter<br>Представляет набор Integer (целых) численных значений. Параметры Integers способны хранить постоянные данные. Вы можете настроить запись постоянных данных через меню Parameter.|![IMAGE](images/PPInt.png)|
|<a name="PPNum"></a>P.P.Num|Number Parameter<br>Представляет набор численных значений с плавающей точкой. Параметры Number способны хранить постоянные данные. Вы можете настроить запись постоянных данных через меню Parameter.|![IMAGE](images/PPNum.png)|
|<a name="PPPath"></a>P.P.Path|File Path<br>Содержит набор путей файла.|![IMAGE](images/PPPath.png)|

####Input
||||
|--|--|--|
|<a name="PIToggle"></a>P.I.Toggle|Boolean Toggle<br>Переключатель булевых значений (правда/ложь).|![IMAGE](images/PIToggle.png)|
|<a name="PIButton"></a>P.I.Button|Button<brКнопка с двумя значениями. При нажатии, кнопка возвращает значение true (правда) и затем сбрасывает значение на false (ложь).|![IMAGE](images/PIButton.png)|
|<a name="PISwatch"></a>P.I.Swatch|Color Swatch<br>Swatch (образец) - это особый объект интерфейса, который позволяет быстро настроить индивидуальные цветовые значения. Вы можете поменять цвет образца через контекстное меню.|![IMAGE](images/PISwatch.png)|
|<a name="PIGrad"></a>P.I.Grad|Gradient Control<br>Gradient control (контроль градиента) позволяет определить градиент цвета внутри числового диапазона. По умолчанию используется диапазон (от 0.0 до 1.0), но это можно настроить через параметры ввода L0 и L1. Также вы можете добавить цветовые ползунки к градиенту перетаскивая из верхнего левого угла цветовое колесико и настраивая цветовые ползунки кликая правой клавишей мыши.|![IMAGE](images/PIGrad.png)|
|<a name="PIGraph"></a>P.I.Graph|Graph Mapper<br>Graph Mapper позволяет вам перенести набор чисел. По умолчанию диапазоны {x} и {y} графической функции - это диапазон секции (0.0 ~ 1.0), но это также можно настроить через Graph Editor. Graph Mapper может содержать одиночную функцию переноса, которую можно выбрать через контекстное меню. Графы обычно имеют ползунки (небольшие круги), которые можно использовать для изменения переменных, которые определяют графическое уравнение. По умолчанию, объекты graph mapper не содержат графиков и выполняют перенос значений 1:1.|![IMAGE](images/PIGraph.png)|
|<a name="PISlider"></a>P.I.Slider|Number Slider<br>Slider (слайдер) - это особый объект интерфейса, который позволяет быстро настроить индивидуальные числовые значения. Вы можете менять значения и характеристики через меню или двойным кликом на поверхности слайдера. Слайдеры можно удлинить или укоротить перетаскивая самое крайнее правое ребро влево или вправо. Заметьте, что слайдеры имеют только вход (т.е. не имеют выхода).|![IMAGE](images/PISlider.png)|
|<a name="PIPanel"></a>P.I.Panel|Panel<br>Panel (панель) для разных заметок и текстовых значений. Обычно, это неактивный объект, который позволяет вам добавлять комментарии или объяснения к Документу. Панели могут получать информацию откуда угодно. Если вы подключите параметр выхода в панель, вы увидите содержание этого параметра в реальном времени. Все данные в Grasshopper можно просматривать таким образом. Панели также могут передавать их содержание в текстовый файл.|![IMAGE](images/PIPanel.png)|
|<a name="PIList"></a>P.I.List|Value List<br>Предоставляет список преднастроенных значений из которых можно выбрать.|![IMAGE](images/PIList.png)|

####Utilities
||||
|--|--|--|
|<a name="P.U.Cin"></a>P.U.Cin|Cluster Input<br>Представляет параметр Cluster Input.|![IMAGE](images/PUCin.png)|
|<a name="P.U.COut"></a>P.U.COut|Cluster Output<br>Представляет параметр Cluster Output.|![IMAGE](images/PUCOut.png)|
|<a name="P.U.Dam"></a>P.U.Dam|Data Dam<br>Задерживает данные на их пути по всему документу.|![IMAGE](images/PUDam.png)|
|<a name="P.U.Jump"></a>P.U.Jump|Jump<br>Прыжок между различными местами.|![IMAGE](images/PUJump.png)|
|<a name="P.U.Viewer"></a>P.U.Viewer|Param Viewer<br>Просмотрщик структуры данных.|![IMAGE](images/PUViewer.png)|
|<a name="P.U.Scribble"></a>P.U.Scribble|Scribble<br>Быстрая заметка.|![IMAGE](images/PUScribble.png)|

Maths
--

####Domain
||||
|--|--|--|
|<a name="M.D.Bnd"></a>M.D.Bnd|Bounds<br>Создает числовой диапазон, который содержит список чисел.|![IMAGE](images/MDBnd.png)|
|<a name="M.D.Consec"></a>M.D.Consec|Consecutive Domains<br>Создает последовательные диапазоны из списка чисел.|![IMAGE](images/MDConsec.png)|
|<a name="MDDom"></a>M.D.Dom|Construct Domain<br>Создает числовой диапазон из двух числовых экстремум.|![IMAGE](images/MDDom.png)|
|<a name="MDDom2Num"></a>M.D.Dom2Num|Construct Domain²<br>Создает двух-пространственный диапазон из четырех чисел.|![IMAGE](images/MDDom2Num.png)|
|<a name="MDDeDomain"></a>M.D.DeDomain|Deconstruct Domain<br>Разрушает числовой диапазон на его компоненты.|![IMAGE](images/MDDeDomain.png)|
|<a name="MDDeDom2Num"></a>M.D.DeDom2Num|Deconstruct Domain²<br>Разрушает двух-пространственный диапазон на четыре числа.|![IMAGE](images/MDDeDom2Num.png)|
|<a name="MDDivide"></a>M.D.Divide|Divide Domain²<br>Разделяет двух-пространственный диапазон на равные сегменты.|![IMAGE](images/MDDivide.png)|
|<a name="MDInc"></a>M.D.Inc|Includes<br>Проверяет числовое значение, включено ли оно в диапазон.|![IMAGE](images/MDInc.png)|
|<a name="MDReMap"></a>M.D.ReMap|Remap Numbers<br>Переносит числа в новый числовой диапазон.|![IMAGE](images/MDReMap.png)|


####Operators
||||
|--|--|--|
|<a name="MOAdd"></a>M.O.Add|Addition<br>Математическое добавление.|![IMAGE](images/MOAdd.png)|
|<a name="MODiv"></a>M.O.Div|Division<br>Математическое разделение.|![IMAGE](images/MODiv.png)|
|<a name="MOEquals"></a>M.O.Equals|Equality<br>Проверяет на (не)равенство двух чисел.|![IMAGE](images/MOEquals.png)|
|<a name="MOAnd"></a>M.O.And|Gate And<br>Выполняет соединение булевых значений (AND gate). Оба входа должны быть True, для того чтобы результат был True.|![IMAGE](images/MOAnd.png)|
|<a name="MONot"></a>M.O.Not|Gate Not<br>Выполняет отрицание булевых значений (NOT gate).|![IMAGE](images/MONot.png)|
|<a name="MOOr"></a>M.O.Or|Gate Or<br>Выполняет разъединение булевых значений (OR gate). Только один вход должен быть True, для того чтобы результат был True|![IMAGE](images/MOOr.png)|
|<a name="MOLarger"></a>M.O.Larger|Larger Than<br>Больше чем (или равно).|![IMAGE](images/MOLarger.png)|
|<a name="MOMultiply"></a>M.O.Multiply|Multiplication<br>Математическое умножение.|![IMAGE](images/MOMultiply.png)|
|<a name="MOSmaller"></a>M.O.Smaller|Smaller Than<br>Меньше чем (или равно).|![IMAGE](images/MOSmaller.png)|
|<a name="MOSimilar"></a>M.O.Similar|Similarity<br>Проверяет на сходство двух чисел.|![IMAGE](images/MOSimilar.png)|
|<a name="MOSub"></a>M.O.Sub|Subtraction<br>Математическое извлечение.|![IMAGE](images/MOSub.png)|

####Script
||||
|--|--|--|
|<a name="MSEval"></a>M.S.Eval|Evaluate<br>Определяет выражение с гибкими числами переменных.|![IMAGE](images/MSEval.png)|
|<a name="MSExpression"></a>M.S.Expression|Expression<br>Определяет выражение.|![IMAGE](images/MSExpression.png)|

####Trig
||||
|--|--|--|
|<a name="MTCos"></a>M.T.Cos|Cosine<br>Вычисляет косинус значения.|![IMAGE](images/MTCos.png)|
|<a name="MTDeg"></a>M.T.Deg|Degrees<br>Конвертирует угол, указанный в радианах, в градусы.|![IMAGE](images/MTDeg.png)|
|<a name="MTRad"></a>M.T.Rad|Radians<br>Конвертирует угол, указанный в градусах, в радианы.|![IMAGE](images/MTRad.png)|
|<a name="MTSin"></a>M.T.Sin|Sine<br>Вычисляет синус значения.|![IMAGE](images/MTSin.png)|

####Utilities
||||
|--|--|--|
|<a name="MUAvr"></a>M.U.Avr|Average<br>Проверяет среднее арифметическое для набора элементов.|![IMAGE](images/MUAvr.png)|
|<a name="MUPhi"></a>M.U.Phi|Golden Ratio<br>Выдает множество золотого сечения (Phi).|![IMAGE](images/MUPhi.png)|
|<a name="MUPi"></a>M.U.Pi|Pi<br>Выдает множество Pi.|![IMAGE](images/MUPi.png)|

Sets
--

####List
||||
|--|--|--|
|<a name="SLCombine"></a>S.L.Combine|Combine Data<br>Сочетает не-неизвестные значения из нескольких входов.|![IMAGE](images/SLCombine.png)|
|<a name="SLCrossRef"></a>S.L.CrossRef|Cross Reference<br>Производит кросс-референс данных из множества списков.|![IMAGE](images/SLCrossRef.png)|
|<a name="SLDispatch"></a>S.L.Dispatch|Dispatch<br>Распаковывает элементы списка в два целевых списка. List Dispatching очень похоже на компонент [Cull Pattern], за исключением того, что оба списка предоставляются как выходы.|![IMAGE](images/SLDispatch.png)|
|<a name="SLIns"></a>S.L.Ins|Insert Items<br>Вставляет коллекцию элементов в список.|![IMAGE](images/SLIns.png)|
|<a name="SLItem"></a>S.L.Item|List Item<br>Извлекает особые элементы из списка.|![IMAGE](images/SLItem.png)|
|<a name="SLLng"></a>S.L.Lng|List Length<br>Измеряет длину списка. Элементы списка идентифицируются по их индексу. Первый элемент сохраняется под индексом ноль, второй элемент под индексом один и так далее. Самый большой возможный индекс в списке равняется длине списка минус один.|![IMAGE](images/SLLng.png)|
|<a name="SLLong"></a>S.L.Long|Longest List<br>Выращивает набор списков по самому длинному среди них.|![IMAGE](images/SLLong.png)|
|<a name="SLSplit"></a>S.L.Split|Split List<br>Разделяет лист на отдельные части.|![IMAGE](images/SLSplit.png)|
|<a name="SLReplace"></a>S.L.Replace|Replace Items<br>Заменяет определенные элементы в списке.|![IMAGE](images/SLReplace.png)|
|<a name="SLRev"></a>S.L.Rev|Reverse List<br>Разворачивает порядок списка. Новый индекс каждого элемента будет N-i, где N - наивысший индекс в списке и i - старый индекс элемента.|![IMAGE](images/SLRev.png)|
|<a name="SLShift"></a>S.L.Shift|Shift List<br>Смещает все элементы в списке. Элементы в списке смещаются (перемещаются) к концу списка, если shift смещение имеет положительное значение. Если Wrap равняется True, тогда те элементы, которые выпадают за края, присоединяются заново.|![IMAGE](images/SLShift.png)|
|<a name="SLShort"></a>S.L.Short|Shortest List<br>Сжимает коллекцию списков по длине самого короткого из них.|![IMAGE](images/SLShort.png)|
|<a name="SLSift"></a>S.L.Sift|Sift Pattern<br>Sift элементы в списке используют повторяющийся паттерн индексов.|![IMAGE](images/SLSift.png)|
|<a name="SLSort"></a>S.L.Sort|Sort List<br>Сортирует список числовых ключей. Чтобы что-то отсортировать, это должно быть сначала сопоставлено. Большинство типов данных не может быть сопоставлена, Numbers и Strings - единственное исключение. Если вы хотите отсортировать другие типы данных, такие как кривые, сначала вам потребуется создать список ключей.|![IMAGE](images/SLSort.png)|
|<a name="SLWeave"></a>S.L.Weave|Weave<br>Соединяет набор вводных данных используя определенный шаблон. Шаблон определяется как список индекс значений (целых), которые определяют порядок, в котором вводные данные собираются.|![IMAGE](images/SLWeave.png)|

####Sets
||||
|--|--|--|
|<a name="SSCulli"></a>S.S.Culli|Cull Index<br>Cull (удаляет) проиндексированные элементы в списке.|![IMAGE](images/SSCulli.png)|
|<a name="SSCull"></a>S.S.Cull|Cull Pattern<br>Cull (удаляет) элементы в списке, используя повторяющуюся битовую маску. Битовая маска определяется как список булевых значений. Битовая маска повторяется, пока все элементы из списка данных не будут определены.|![IMAGE](images/SSCull.png)|
|<a name="SSDup"></a>S.S.Dup|Duplicate Data<br>Дублировать данные предопределенное количество раз. Данные могут дублироваться двумя способами, либо копии списка прикрепляются в конце до тех пор, пока не будет достигнуто некое количество копий, либо каждый элемент дублируется некоторое число раз, прежде чем перейти к следующему элементу.|![IMAGE](images/SSDup.png)|
|<a name="SSJitter"></a>S.S.Jitter|Jitter<br>Случайным образом перемешивает список значений. Вводный список реорганизуется на основе флуктуационного шума. Jittering (создание быстрых флуктуаций) - это хороший способ получения случайного набора с хорошим распределением. Параметры jitter (создания быстрых флуктуаций) настраивают радиус флуктуационного шума. Если jitter равняется 0.5, тогда каждому элементу разрешено переместиться случайным образом в пределах половины ширины всего набора.|![IMAGE](images/SSJitter.png)|
|<a name="SSRandom"></a>S.S.Random|Random<br>Генерируется список псевдо-случайных чисел. Числовая последовательность уникальна, но стабильная для каждого значения seed. Если вам не нравится случайное распределение, попробуйте другие значения seed.|![IMAGE](images/SSRandom.png)|
|<a name="SSRange"></a>S.S.Range|Range<br>Создает диапазон чисел. Числа распределяются равномерно внутри числового диапазона. Используйте этот компонент, если вам необходимо создать числа между экстремумами. Если вы хотите контролировать интервалы между последовательными числами, вам следует использовать компонент [Series].|![IMAGE](images/SSRange.png)|
|<a name="SSRepeat"></a>S.S.Repeat|Repeat Data<br>Повторяет паттерн до тех пор, пока не достигнет определенной длины.|![IMAGE](images/SSRepeat.png)|
|<a name="SSSeries"></a>S.S.Series|Series<br>Создает последовательность чисел. Числа распределены в соответствии со значением {Step}. Если вам необходимо распределить числа внутри фиксированного числового порядка, то используйте компонент [Range].|![IMAGE](images/SSSeries.png)|

####Tree
||||
|--|--|--|
|<a name="STExplode"></a>S.T.Explode|Explode Tree<br>Извлекает все ветки из дерева.|![IMAGE](images/STExplode.png)|
|<a name="STFlatten"></a>S.T.Flatten|Flatten Tree<br>Сглаживает дерево данных путем удаления всей информации о ветках.|![IMAGE](images/STFlatten.png)|
|<a name="STFlip"></a>S.T.Flip|Flip Matrix<br>Переворот дерева данных типа матрицы меняя местами ряды и колонны.|![IMAGE](images/STFlip.png)|
|<a name="STGraft"></a>S.T.Graft|Graft Tree<br>Обычно, элементы данных хранятся в ветках в определенных индекс значениях (0 - первый элемент, 1 - второй элемент и т.д.) и ветки хранятся в деревьях в определенных путях веток, например: {0;1}, который отображает вторую под-ветку первой основной ветки. Grafting создает новую ветку для каждого отдельного элемента данных.|![IMAGE](images/STGraft.png)|
|<a name="STMerge"></a>S.T.Merge|Merge<br>Смешивает множество потоков данных.|![IMAGE](images/STMerge.png)|
|<a name="STPath"></a>S.T.Path|Path Mapper<br>Выполняет лексические операции с деревьями данных. Лексические операции - это логические переносы между путями данных и индексов, которые определяются текстовыми (лексическими) масками и паттернами.|![IMAGE](images/STPath.png)|
|<a name="STPrune"></a>S.T.Prune|Prune Tree<br>Удаляет все ветки у дерева, которое содержит определенное число элементов данных. Вы можете установить обе границы, нижнюю и верхнюю, при сокращении веток.|![IMAGE](images/STPrune.png)|
|<a name="STSimplify"></a>S.T.Simplify|Simplify Tree<br>Упрощает дерево, удаляя накладки среди всех веток.|![IMAGE](images/STSimplify.png)|
|<a name="STTStat"></a>S.T.TStat|Tree Statistics<br>Можно получить некоторую статистику касательно дерева данных.|![IMAGE](images/STTStat.png)|
|<a name="STUnflatten"></a>S.T.Unflatten|Unflatten Tree<br>Разглаживает дерево данных путем перемещения элементов обратно на ветки.|![IMAGE](images/STUnflatten.png)|

Vector
--

####Grid
||||
|--|--|--|
|<a name="VGHexGrid"></a>V.G.HexGrid|Hexagonal<br>2D сетка с шестиугольными ячейками.|![IMAGE](images/VGHexGrid.png)|
|<a name="VGRecGrid"></a>V.G.RecGrid|Rectangular<br>2D сетка с прямоугольными ячейками.|![IMAGE](images/VGRecGrid.png)|
|<a name="VGSqGrid"></a>V.G.SqGrid|Square<br>2D сетка с квадратными ячейками|![IMAGE](images/VGSqGrid.png)|

####Point
||||
|--|--|--|
|<a name="VPPt"></a>V.P.Pt|Construct Point<br>Построение точки из координат {xyz}.|![IMAGE](images/VPPt.png)|
|<a name="VPpDecon"></a>V.P.pDecon|Deconstruct<br>Разбирает точку на ее компоненты.|![IMAGE](images/VPpDecon.png)|
|<a name="VPDist"></a>V.P.Dist|Distance<br>Вычисляет Евклидовое расстояние между координатами двух точек.|![IMAGE](images/VPDist.png)|

####Vector
||||
|--|--|--|
|<a name="VVX"></a>V.V.X|Unit X<br>Unit вектор параллелен мировой оси {x}.|![IMAGE](images/VVX.png)|
|<a name="VVY"></a>V.V.Y|Unit Y<br>Unit вектор параллелен мировой оси {y}.|![IMAGE](images/VVY.png)|
|<a name="VVVec2Pt"></a>V.V.Vec2Pt|Vector 2Pt<br>Создает вектор между двумя точками.|![IMAGE](images/VVVec2Pt.png)|

Curve
--

####Analysis
||||
|--|--|--|
|<a name="CACP"></a>C.A.CP|Control Points<br>Извлекает контрольные точки nurbs и узлы кривой.|![IMAGE](images/CACP.png)|

####Division
||||
|--|--|--|
|<a name="CDDivide"></a>C.D.Divide|Divide Curve<br>Разделяет кривую на равные по длине сегменты.|![IMAGE](images/CDDivide.png)|

####Primitive
||||
|--|--|--|
|<a name="CPCir"></a>C.P.Cir|Circle<br>Создает круг, определяемый основной плоскостью и радиусом.|![IMAGE](images/CPCir.png)|
|<a name="CPCir3Pt"></a>C.P.Cir3Pt|Circle 3Pt<br>Создает круг, определяемый тремя точками.|![IMAGE](images/CPCir3Pt.png)|
|<a name="CPCirCNR"></a>C.P.CirCNR|Circle CNR<br>Создает круг, определяемый центром, нормалью и радиусом.|![IMAGE](images/CPCirCNR.png)|
|<a name="CPLine"></a>C.P.Line|Line SDL<br>Создает линейный сегмент, определяемый начальной точкой, тангенсом и длиной.|![IMAGE](images/CPLine.png)|
|<a name="CPPolygon"></a>C.P.Polygon|Polygon<br>Создает полигон с дополнительными круглыми ребрами.|![IMAGE](images/CPPolygon.png)|

####Spline
||||
|--|--|--|
|<a name="CSIntCrv"></a>C.S.IntCrv|Interpolate<br>Создает интерполируемую кривую через набор точек.|![IMAGE](images/CSIntCrv.png)|
|<a name="CSKinkCrv"></a>C.S.KinkCrv|Kinky Curve<br>Строит интерполируемую кривую через набор точек с предельной величиной угла изгиба.|![IMAGE](images/CSKinkCrv.png)|
|<a name="CSNurbs"></a>C.S.Nurbs|Nurbs Curve<br>Строит кривую nurbs из контрольных точек.|![IMAGE](images/CSNurbs.png)|
|<a name="CSPLine"></a>C.S.PLine|PolyLine<br>Создает полилинию, соединяющую некоторое число точек.|![IMAGE](images/CSPLine.png)|

####Util
||||
|--|--|--|
|<a name="CUExplode"></a>C.U.Explode|Explode<br>Разбивает кривую на маленькие сегменты.|![IMAGE](images/CUExplode.png)|
|<a name="CUJoin"></a><C.U.Join|Join Curves<br>Соединяет так много кривых как возможно.|![IMAGE](images/CUJoin.png)|
|<a name="CUOffset"></a>C.U.Offset|Offset<br>Смещает кривую на определенную дистанцию.|![IMAGE](images/CUOffset.png)|

Surface
--

####Analysis
||||
|--|--|--|
|<a name="SADeBrep"></a>S.A.DeBrep|Deconstruct Brep<br>Разбирает brep на ее составляющие.|![IMAGE](images/SADeBrep.png)|

####Freeform
||||
|--|--|--|
|<a name="SFBoundary"></a>S.F.Boundary|Boundary Surfaces<br>Создает плоскую поверхность из коллекции граничных ребер кривых.|![IMAGE](images/SFBoundary.png)|
|<a name="SFExtr"></a>S.F.Extr|Extrude<br>Вытесняет кривые и поверхности вдоль вектора.|![IMAGE](images/SFExtr.png)|
|<a name="SFExtrPt"></a>S.F.ExtrPt|Extrude Point<br>Вытесняет кривые и поверхности к точке.|![IMAGE](images/SFExtrPt.png)|
|<a name="SFLoft"></a>S.F.Loft|Loft<br>Создает выпуклую поверхность через набор секций кривых.|![IMAGE](images/SFLoft.png)|
|<a name="SFRevSrf"></a>S.F.RevSrf|Revolution<br>Создает поверхность вращения.|![IMAGE](images/SFRevSrf.png)|
|<a name="SFSwp2"></a>S.F.Swp2|Sweep2<br>Создает загнутую поверхность с двумя rail кривыми.|![IMAGE](images/SFSwp2.png)|

####Primitive
||||
|--|--|--|
|<a name="SPBBox"></a>S.P.BBox|Bounding Box<br>Solve ориентированная геометрия граничных прямоугольников.|![IMAGE](images/SPBBox.png)|

####Util
||||
|--|--|--|
|<a name="SUSDivide"></a>S.U.SDivide|Divide Surface<br>Генерирует сетку точек {uv} на поверхности.|![IMAGE](images/SUSDivide.png)|
|<a name="SUSubSrf"></a>S.U.SubSrf|Isotrim<br>Извлекает изопараметрическое подмножество поверхности.|![IMAGE](images/SUSubSrf.png)|

Mesh
--

####Triangulation
||||
|--|--|--|
|<a name="MTVoronoi"></a>M.T.Voronoi|Voronoi<br>Плоскостная диаграмма Вороного для коллекции точек.|![IMAGE](images/MTVoronoi.png)|

Transform
--

####Affine
||||
|--|--|--|
|<a name="TARecMap"></a>T.A.RecMap|Rectangle Mapping<br>Трансформирует геометрию из одного прямоугольника в другой.|![IMAGE](images/TARecMap.png)|

####Array
||||
|--|--|--|
|<a name="TAArrLinear"></a>T.A.ArrLinear|Linear Array<br>Создает линейный массив геометрии.|![IMAGE](images/TAArrLinear.png)|

####Morph
||||
|--|--|--|
|<a name="TMMorph"></a>T.M.Morph|Box Morph<br>Превращение объекта в скрученную коробку.|![IMAGE](images/TMMorph.png)|
|<a name="TMSBox"></a>T.M.SBox|Surface Box<br>Создает скрученную коробку на участке поверхности.|![IMAGE](images/TMSBox.png)|

Display
--

####Color
||||
|--|--|--|
|<a name="DCHSL"></a>D.C.HSL|Colour HSL<br>Создает цвет из плавающих точек {HSL} каналов.|![IMAGE](images/DCHSL.png)|

####Dimensions
||||
|--|--|--|
|<a name="DDTag"></a>D.D.Tag|Text tags<br>Компонент текстовый тэг позволяет рисовать небольшие Strings в видовом окне как элементы обратной связи. Текст и расположение определяются как параметры ввода. Когда текстовые тэги запекаются, они превращаются в Text Dots (текстовые точки).|![IMAGE](images/DDTag.png)|
|<a name="DDTag3D"></a>D.D.Tag3D|Text Tag 3D<br>Представляет список 3D текстовых тэгов в видовом окне Rhino|![IMAGE](images/DDTag3D.png)|

####Preview
||||
|--|--|--|
|<a name="DPPreview"></a>D.P.Preview|Custom Preview<br>Позволяет настраивать предпросмотр геометрии.|![IMAGE](images/DPPreview.png)|

####Vector
||||
|--|--|--|
|<a name="DVPoints"></a>D.V.Points|Point List<br>Отображает подробные данные о списках точек.|![IMAGE](images/DVPoints.png)|


