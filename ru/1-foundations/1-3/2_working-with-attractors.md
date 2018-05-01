<style>
td:nth-child(1) {color: #008DB2}
td:nth-child(3)	{font-size: 70%;width: 15%;}
td {background-color: #F9F9F9;}
thead {display: none}
</style>
### 1.3.2. Работая с аттракторами

##### Аттракторы - это точки, которые ведут себя как виртуальные магниты - либо притягивают либо отталкивают другие объекты. В Grasshopper, любая геометрия, взятая из Rhino или созданная в Grasshopper, может быть использована как аттрактор. Аттракторы могут влиять на любое число параметров окружающих объектов включая масштаб, вращение, цвет и положение. Эти параметры изменяются на основе их отношений с геометрией аттрактора.

![Overview](images/1-3-2/1-3-2_001-attractor-overview.png)
>1. Точка аттрактора
2. Векторы
3. Круги ориентируются по направлению к аттрактору на основе их нормалей

На изображении выше, векторы изображены между точкой аттрактора и точкой начала 
координат каждого круга. Эти векторы используются для определения ориентации кругов, 
таким образом, что они всегда обращены к точке аттрактора. Тот же самый аттрактор 
может быть использован для изменения других параметров кругов. Например, те круги,
которые ближе всего к аттрактору, могут иметь больший размер, используя длину 
каждого вектора, чтобы масштабировать радиус каждого круга.

![Examples](images/1-3-2/1-3-2_002-attractor-examples.png)

#### 1.3.2.1. ОПРЕДЕЛЕНИЕ АТТРАКТОРА
{% if gitbook.generator == "pdf" or gitbook.generator == "mobi" or gitbook.generator == "epub" %}
>Файлы упражнения, которые сопровождают этот раздел: [http://grasshopperprimer.com/appendix/A-2/1_gh-files.html](http://grasshopperprimer.com/appendix/A-2/1_gh-files.html)
{% else %}
>Файлы упражнения, которые сопровождают этот раздел: [Download](../../appendix/A-2/gh-files/1.3.2.1_attractor definition.gh)
{% endif %}

В этом примере, мы будем использовать точку аттрактора, чтобы расположить сетку кругов, основанную на векторах между точками начала координат кругов и точками аттракторов. Каждый круг будет ориентироваться таким образом, что он будет перпендикулярен (обращен) к точке аттрактора.

||||
|--|--|--|
|01.| Чтобы начать новое определение, нажмите Ctrl+N в Grasshopper||
|02.| Зайдите в **Vector/Grid/Hexagonal** - перетащите компонент **Hexagonal Grid** на холст|[![IMAGE](images/1-3-2/1-3-2_003-hex-grid-component.png)](../../appendix/A-1/0_index-of-components.html#VGHexGrid)|
|03.| Зайдите в **Params/Input/Slider** - перетащите два слайдера **Numeric Sliders** на холст||
|04.| Дважды кликните по первому слайдеру **Numeric Sliders** и установите следующее:<ul>Name (Имя): Cell Radius (радиус ячейки)<br>Rounding (Округление): Floating Point (с плавающей точкой)<br>Lower Limit (нижняя граница): 0.000<br>Upper Limit (верхняя граница): 1.000<br>Value (значение): 0.500</ul>||
|05.| Дважды кликните по второму слайдеру **Numeric Sliders** и установите следующее:<ul>Name (Имя): # of Cells (число ячеек)<br>Rounding (Округление): Integers (целые числа)<br>Lower Limit (нижняя граница): 0<br>Upper Limit (верхняя граница): 10<br>Value (значение): 10</ul>||
|06.| Соедините слайдер **Number Slider** (Cell Radius) с входом Size (S) компонента Hexagon Grid||
|07.| Соедините слайдер **Number Slider** (# of Cells) с входом Extent X (Ex) и входом Extent Y (Ey)  компонента Hexagon Grid|||

![](images/1-3-2/1-3-2_004-definition1.png)

||||
|--|--|--|
|08.| Зайдите в **Curve/Primitive/Circle CNR** - перетащите компонент **Circle CNR** на холст|[![](images/1-3-2/1-3-2_005-circle-CNR.png)](../../appendix/A-1/0_index-of-components.html#CPCirCNR)|
|09.| Соедините выход Points (P) компонента **Hexagon Grid** с входом Center (C) компонента **Circle CNR**||
|10.| Соедините слайдер **Number Slider** (Cell Radius) с входом Radius (R) компонента **Circle CNR**.||
|11.| Зайдите в **Vector/Vector/Vector 2Pt** - перетащите компонент **Vector 2Pt**на холст|[![IMAGE](images/1-3-2/1-3-2_006-vector-2pt.png)](../../appendix/A-1/0_index-of-components.html#VVVec2Pt)|
|12.| Соедините выход Points (P) компонента **Hexagonal Grid** с входом Base Point (A) компонента **Vector 2Pt**.||
|13.| Зайдите в **Params/Geometry/Point** – перетащите компонент **Point** на холст|[![IMAGE](images/1-3-2/1-3-2_007-point.png)](../../appendix/A-1/0_index-of-components.html#PGPt)|
|14.| Кликните правой клавишей мыши по компоненту **Point** и выберите set one point. В модели пространства выберите место, где вы хотите разместить точку аттрактора||
|15.| Соедините компонент **Point** с входом Tip Point (B) компонента **Vector 2Pt**||
|16.| Соедините выход Vector (V) компонента **Vector 2Pt** с входом Normal (N) компонента **Circle CNR**.|||

![IMAGE](images/1-3-2/1-3-2_008-definition2.png)

||||
|--|--|--|
|17.| Зайдите в **Curve/Util/Offset** – перетащите компонент **Offset Component** на холст.|[![IMAGE](images/1-3-2/1-3-2_009-offset.png)](../../appendix/A-1/0_index-of-components.html#CUOffset)|
|18.| Зайдите в **Params/Input/Slider** - перетащите слайдер **Numeric Slider** на холст||
|19.| Дважды кликните по слайдеру и установите следующее:<ul>Name: Offset Distance<br>Rounding: Floating Point<br>Lower Limit: - 0.500<br>Upper Limit: 0.500<br>Value: -0.250</ul>||
|20.| Соедините слайдер **Number Slider** (Offset Distance) с входом Distance (D) компонента **Offset**|||

![IMAGE](images/1-3-2/1-3-2_010-definition3.png)

![IMAGE](images/1-3-2/1-3-2_011-output3.png)

||||
|--|--|--|
|21.| Зайдите в **Surface/Freeform/Boundary Surfaces** – перетащите компонент **Boundary Surfaces** на холст|[![IMAGE](images/1-3-2/1-3-2_012-boundary-surface.png)](../../appendix/A-1/0_index-of-components.html#SFBoundary)|
|22.| Соедините выход Curves (C) компонента **Offset** с входом Edges (E) компонента **Boundary Surfaces**|||

![IMAGE](images/1-3-2/1-3-2_013-definition4.png)


![](images/1-3-2/1-3-2_014-small-examples.png)

![](images/1-3-2/1-3-2_015-large-example.png)
