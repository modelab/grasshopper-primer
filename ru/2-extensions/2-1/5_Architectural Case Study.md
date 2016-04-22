###2.1.5. Element* Изучение применения в архитектуре

#####В этом разделе мы проработает простой пример, в качестве введения в работу с инструментами Element. Мы изучим некоторые паттерны и обработку фасадов в области архитектуры, где мы подключим структуру данных Half Edge вместе с базовыми компонентами Element без использования характеристик per vertex.

![IMAGE](images/2-1-5/2-1-5_001_Main-Render.jpg)


####2.1.5.1 Пример 1

{% if gitbook.generator == "pdf" or gitbook.generator == "mobi" or gitbook.generator == "epub" %}
>Файлы упражнения, которые сопровождают этот раздел: [http://grasshopperprimer.com/appendix/A-2/1_gh-files.html](http://grasshopperprimer.com/appendix/A-2/1_gh-files.html)
{% else %}
>Файлы упражнения, которые сопровождают этот раздел: [Download](../../appendix/A-2/gh-files/2.1.5.1_Architecture Case Study_A.gh)
{% endif %}

<style>
td:nth-child(1) {color: #008DB2}
td:nth-child(3)	{width: 10%;}
td {background-color: #F9F9F9;}
thead {display: none}
</style>


---
![IMAGE](images/2-1-5/2-1-5_002_Animation.gif)
---
![IMAGE](images/2-1-5/2-1-5_003_Diagram.png)

||||
|--|--|--|
|00.| Создайте плоскость mesh в Rhino с **XFaces = 2 и YFaces = 2** и запустите новое определение, набрав Ctrl-N (в Grasshopper)||
|01.| Зайдите в **Params/Geometry/Mesh** - вытащите контейнер **Mesh** на холст|![IMAGE](images/2-1-5/2-1-5_004_Mesh.png)|
|01b.| Чтобы привязать mesh в Rhino, кликните правой клавишей мыши по компоненту **Mesh** и выберите "Set one Mesh". <br><blockquote>Мы будем использовать простую плоскость mesh в ходе работы с этим определением, но вы можете заменить эту mesh вашей собственной</blockquote>||
|02.| Зайдите в **Element\*/Utility/Mesh Combine and Clean** - перетащите компонент **Element* Mesh Combine and Clean** на холст|![IMAGE](images/2-1-5/2-1-5_005_Combine-and-Clean.png)|
|03.| Зайдите в **Element\*/Data/Vertex Neighbors** - перетащите компонент **Element* Vertex Neighbors** на холст| ![IMAGE](images/2-1-5/2-1-5_006_Vertex-Neighbors.png)|
|04.| Зайдите в **Params/Input/Number Slider** - перетащите компонент **Number Slider** на холст и установите следующие значения: <ul>Lower Limit: 0.0000<br>Upper Limit: 1.0000</ul>||
|05.| Зайдите в **Curve/Analysis/Evaluate Curve** - перетащите компонент **Evaluate Curve** на холст|![IMAGE](images/2-1-5/2-1-5_007_Evaluate-Curve.png)|
|05b.| Соедините выход Neighbouring Edges (NE) компонента **Element* Vertex Neighbors** с входом Curve (C) компонента **Evaluate Curve**||
|05c.| Соедините слайдер **Number Slider** с входом Float (t) компонента **Evaluate Curve** и установите значение на 0.5000||
|05d.| Кликните правой клавишей по входу Curve (C) компонента **Evaluate Curve** и выберите **Reparameterize** |||

![IMAGE](images/2-1-5/2-1-5_008_Definition.png)
---

||||
|--|--|--|
|06.| Зайдите в **Element\*/Analyse/Mesh Closest Point** - перетащите компонент **Element* Mesh Closest Point** на холст|![IMAGE](images/2-1-5/2-1-5_009_Element-MeshClosestPoint.png)|
|06a.| Соедините выход Mesh (M) компонента **Element\*/Utility/Mesh Combine and Clean** с входом Mesh (M) компонента **Element* Mesh Closest Point**||
|06b.| Соедините выход Points (P) компонента **Curve/Analysis/Evaluate Curve** с входом Point (P) компонента **Element* Mesh Closest Point**||
|07.| Зайдите в **Params/Input/Number Slider** - вытащите компонент **Number Slider** на холст и установите следующие значения: <ul>Rounding: Float<br>Lower Limit:0<br>Upper Limit: 10.000</ul>||
|08.| Зайдите в **Vector/Vector/Amplitude** - перетащите компонент **Amplitude** на холст|![IMAGE](images/2-1-5/2-1-5_010_Vec-Amplitude.png)|
|09.| Зайдите в **Transform/Euclidean/Move** - перетащите компонент **Move** на холст|![IMAGE](images/2-1-5/2-1-5_011_Transform-Move.png)|
|10.| Зайдите в **Params/Geometry/Point** - перетащите компонент **Point** на холст|![IMAGE](images/2-1-5/2-1-5_012_Point.png)|
|10b.| Соедините выход Face Centers (FC) компонента **Element* Vertex Neighbors** с компонентом **Point**||
|11.| Зайдите в **Sets/List/Weave** - перетащите компонент **Weave** на холст|![IMAGE](images/2-1-5/2-1-5_013_Weave.png)||


![IMAGE](images/2-1-5/2-1-5_014_Definition.png)
---
![IMAGE](images/2-1-5/2-1-5_015_Definition.png)

||||
|--|--|--|
|12.| Зайдите в **Curve/Primitive/Polyline** - перетащите компонент **Polyline** на холст|![IMAGE](images/2-1-5/2-1-5_016_Polyline.png)|
|12b.| Соедините выход Weave (W) компонента **Weave** с входом Vertices (V) компонента **Polyline**||
|12c.| Кликните правой клавишей мыши по входу Closed (C) компонента **Polyline**, кликните по "Set Boolean" и выберите значение True <br><blockquote>Так мы создали закрытую полилинию.</blockquote>||
|13.| Зайдите в **Params/Input/Number Slider** - перетащите компонент **Number Silder** на холст. Мы будем использовать по умолчанию диапазон от 0 до 1 для этого слайдера.||
|14.| Зайдите в **Element\*/Transform/Mesh Frame** - перетащите компонент **Element* Mesh Frame** на холст.|![IMAGE](images/2-1-5/2-1-5_017_Mesh-Frame.png)|
|14b.| Соедините выход Polyline (Pl) компонента **Polyline** с входом Geometry (G) компонента **Mesh Frame** <br><blockquote>Заметьте, что компонент **Mesh Frame** может принимать в качестве входа как mesh, так и список закрытых полилиний кривых</blockquote>||
|14c.| Подключите слайдер **Number Slider** к входу Factor (F) компонента **Mesh Frame**|||

![IMAGE](images/2-1-5/2-1-5_018_Diagram.png)
---

||||
|--|--|--|
|15.| Зайдите в **Element\*/Utility/Mesh Combine and Clean** - перетащите компонент **Element* Mesh Combine and Clean** на холст|![IMAGE](images/2-1-5/2-1-5_019_Combine-and-Clean.png) |
|15b.| Кликните правой клавишей мыши по входу Combine Type (CT) компонента **Element* Mesh Combine and Clean**, кликните по "Set Integer" и установите значение 1. <br><blockquote>Вход Combine Type имеет две опции (0, которая объединяет и очищает mesh) и (1, которая соединяет mesh в список и не смешивает вершины). IВ этом примере мы хотим соединить mesh  </blockquote>||
|16.| Кликните правой клавишей мыши по входу Mesh (M) компонента **Element* Mesh Combine and Clean** и выберите "Flatten". <br><blockquote>После этого мы сможем соединить список mesh.</blockquote>||
|17.| Зайдите в **Element\*/Utility/Mesh Status** - перетащите компонент **Element* Mesh Status** на холст|![IMAGE](images/2-1-5/2-1-5_020_Mesh-Status.png) |
|17b| Соедините выходы Info (I) и Status (S) компонента **Element* Mesh Status** с компонентом **Params/Input/Panel** <br><blockquote>Выход mesh **Info** содержит информацию о правильности mesh, закрытом или открытом типе и о количестве компонентов mesh (вершины, полигоны, нормали). **Status** mesh информирует пользователя о том, в "хорошем" ли состоянии mesh, а также передает данные о неоднородных ребрах, количестве неиспользованных вершин, количестве неправильных полигонов, количестве naked ребер и количестве необъединенных mesh. </blockquote>||
|18.| Зайдите в **Params/Input/Colour Swatch** - перетащите компонент **Colour Swatch** на холст||
|19.| Зайдите в **Display/Preview/Custom Preview** - перетащите компонент **Custom Preview** на холст|||

![IMAGE](images/2-1-5/2-1-5_021_Definition.png)
---
![IMAGE](images/2-1-5/2-1-5_022_Definition.png)
---

####2.1.5.2 Пример 2

{% if gitbook.generator == "pdf" or gitbook.generator == "mobi" or gitbook.generator == "epub" %}
>Файлы упражнения, которые сопровождают этот раздел: [http://grasshopperprimer.com/appendix/A-2/1_gh-files.html](http://grasshopperprimer.com/appendix/A-2/1_gh-files.html)
{% else %}
>Файлы упражнения, которые сопровождают этот раздел: [Download](../../appendix/A-2/gh-files/2.1.5.2_Architecture Case Study_B.gh)
{% endif %}

<style>
td:nth-child(1) {color: #008DB2}
td:nth-child(3)	{width: 10%;}
td {background-color: #F9F9F9;}
thead {display: none}
</style>

---
![IMAGE](images/2-1-5/2-1-5_023_Animation.gif)
---
||||
|--|--|--|
|00.| Создайте плоскость mesh в Rhino с **XFaces = 2 и YFaces = 2** и запустите новое определение, набрав Ctrl-N (в Grasshopper)||
|01.| Зайдите в **Params/Geometry/Mesh** - перетащите компонент **Mesh** на холст|![IMAGE](images/2-1-5/2-1-5_024_Mesh.png)|
|01b.| Чтобы привязать mesh в Rhino, кликните правой клавишей мыши по компоненту **Mesh** и выберите "Set one Mesh". <br><blockquote>Мы будем использовать простую плоскость mesh в ходе работы с этим определением, но вы можете заменить эту mesh вашей собственной</blockquote>||
|02.| Зайдите в **Element\*/Utility/Mesh Combine and Clean** - перетащите компонент **Element* Mesh Combine and Clean** на холст|![IMAGE](images/2-1-5/2-1-5_025_Combine-and-Clean.png)|
|03.| Зайдите в **Element\*/Data/Vertex Neighbors** - перетащите компонент **Element* Vertex Neighbors** на холст| ![IMAGE](images/2-1-5/2-1-5_026_Vertex-Neighbors.png)|
|04.| Зайдите в **Vector/Vector/Vector2Pt** - перетащите компонент **Vector2Pt** на холст|![IMAGE](images/2-1-5/2-1-5_027_Vector-2pt.png)|
|05.| Зайдите в **Params/Input/Number Slider** - перетащите компонент **Number Slider** на холст и установите следующие значения: <ul>Rounding: Float<br>Lower Limit:0<br>Upper Limit: 2.000</ul>||
|06.| Зайдите в **Maths/Operator/Multiplication** - перетащите компонент **Multiplication** на холст|![IMAGE](images/2-1-5/2-1-5_028_Multiplication.png)|
|07.| Зайдите в **Maths/Operators/Addition** - перетащите два компонента **Addition** на холст|![IMAGE](images/2-1-5/2-1-5_029_Addition.png)|
|08.| Зайдите в **Curve/Primitive/Polyline** - перетащите компонент **Polyline** на холст|![IMAGE](images/2-1-5/2-1-5_030_Polyline.png)|
|09.| Зайдите в **Curve/Primitive/Polyline** - перетащите компонент **Polyline** на холст|![IMAGE](images/2-1-5/2-1-5_031_Polyline.png)||

![IMAGE](images/2-1-5/2-1-5_032_Definition.png)
---
||||
|--|--|--|
|10.| Зайдите в **Params/Input/Number Slider** - перетащите компонент **Number Slider** на холст и установите следующие значения: <ul>Rounding: Float<br>Lower Limit:0<br>Upper Limit: 1.000</ul>||
|11,12.| Зайдите в **Element\*/Transform/Mesh Frame** - перетащите компонент **Element* Mesh Frame** на холст.|![IMAGE](images/2-1-5/2-1-5_033_Mesh-Frame.png)|
|11b,12b.| Соедините выход Polyline (Pl) компонента **Polyline** с входом Geometry (G) компонента **Mesh Frame** <br><blockquote>Заметьте, что компонент **Mesh Frame** может принимать в качестве входа как mesh, так и список закрытых полилиний кривых</blockquote>||
|11c,12c.| Подключите **Number Slider (10)** к входу Factor (F) компонента **Mesh Frame**||
|13,14.| Зайдите в **Element\*/Subdivide/Catmull Clark Subdivision** - перетащите компонент **Catmull Clark Subdivision** на холст <br><blockquote> Мы установим значение входа Iterations (I) на 1, также как и значение входа **Edge Condition** (E) на 1. Опции входа edge condition следующие 0 = Общая фиксация, 1 == Сглаживание, 2 == Фиксация Углов.  </blockquote>|![IMAGE](images/2-1-5/2-1-5_034_Catmull-Clark.png)|
|15.| Зайдите в **Sets/Tree/Merge** - вытащите два компонента **Merge** на холст|![IMAGE](images/2-1-5/2-1-5_035_Merge.png)|
|15b.| Right click the Result (R) output of the **Merge** component and click "Flatten". ||
|16.| Зайдите в **Element\*/Utility/Mesh Combine and Clean** - перетащите компонент **Element* Mesh Combine and Clean** на холст|![IMAGE](images/2-1-5/2-1-5_036_Combine-and-Clean.png)||

>У компонентов имеются подробные замечания и предупреждения, информирующие пользователя о текущих или возможных проблемах, которые могут возникнуть после итерации с другими компонентами. В некоторых случаях вы можете использовать компонент Element* Combine and Clean чтобы объединить одинаковые вершины на mesh, что может привести к неоднородным ребрам, если в дальнейшем mesh будет утолщена. Компонент Element* Combine and Clean проинформирует вас об этом моменте и о том, что он вернет список обратно. У вас есть возможность установить Combine Type на значение 1, которое объединит mesh в список, но не объединит идентичные вершины.

![IMAGE](images/2-1-5/2-1-5_037_Definition.png)
---
![IMAGE](images/2-1-5/2-1-5_038_Definition.png)

||||
|--|--|--|
|17.| Зайдите в **Element\*/Utility/Mesh Edges** - перетащите компонент **Element* Mesh Edges** на холст|![IMAGE](images/2-1-5/2-1-5_039_Mesh-Edges.png) |
|17b| Соедините выход Mesh (M) компонента **Element* Mesh Combine and Clean** (16) с входом Mesh (M) компонента **Element* Mesh Edges** ||
|18.| Зайдите в **Params/Input/Number Slider** - перетащите компонент **Number Slider** на холст и установите следующие значения: <ul>Rounding: Float<br>Lower Limit:0<br>Upper Limit: 1.000</ul>||
|19.| Зайдите в **Element\*/Transform/Mesh Frame** - перетащите компонент **Element* Mesh Frame** на холст.|![IMAGE](images/2-1-5/2-1-5_040_Mesh-Frame.png)|
|19b| Соедините выход Face Polylines (FP) компонента **Element* Mesh Edges** с входом Mesh (M) компонента **Element* Mesh Frame** ||
|19c| Подключите **Number Slider** к входу Float (f) компонента **Element* Mesh Frame** ||
|20.| Зайдите в **Element\*/Utility/Mesh Combine and Clean** - перетащите компонент **Element* Mesh Combine and Clean** на холст|![IMAGE](images/2-1-5/2-1-5_041_Combine-and-Clean.png)|
|21.| Кликните правой клавишей мыши по входу Mesh (M) компонента **Element* Mesh Combine and Clean** и выберите "Flatten". ||
|22.| Кликните правой клавишей мыши по входу Combine Type (CT) компонента **Element* Mesh Combine and Clean**, кликните по "Set Integer" и установите значение 1. <br><blockquote>Вход Combine Type имеет две опции (0, которая объединяет и очищает mesh) и (1, которая соединяет mesh в список, но не совмещает вершины). В этом примере мы хотим соединить несколько mesh  </blockquote>||
|23.| Зайдите в **Params/Input/Colour Swatch** - перетащите компонент **Colour Swatch** на холст||
|24.| Зайдите в **Display/Preview/Custom Preview** - перетащите компонент **Custom Preview** на холст||
|25.| Зайдите в **Element\*/Utility/Mesh Status** - перетащите компонент **Element* Mesh Status** на холст|![IMAGE](images/2-1-5/2-1-5_042_Mesh-Status.png) |
|25b| Соедините выходы Info (I) и Status (S) компонента **Element* Mesh Status** с компонентом **Params/Input/Panel** <br><blockquote>Выход mesh **Info** содержит информацию о правильности mesh, закрытом или открытом типе и о количестве компонентов mesh (вершины, полигоны, нормали). **Status** mesh информирует пользователя о том, в "хорошем" ли состоянии Mesh, а также передает данные о неоднородных ребрах, количестве неиспользованных вершин, количестве неправильных полигонов, количестве naked ребер и количестве необъединенных mesh. </blockquote>|||


![IMAGE](images/2-1-5/2-1-5_043_Diagram.png)
---
![IMAGE](images/2-1-5/2-1-5_044_Definition.png)
