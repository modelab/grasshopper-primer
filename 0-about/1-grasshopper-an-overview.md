## Grasshopper - Los Orígenes

#####Grasshopper es un editor de programación visual desarrollado por David Rutten en Robert McNeel & Associates. Como un plug-in para Rhino3D, Grasshopper está embebido en el robusto y versátil entorno de modelación utilizado por profesionales de diversas y variadas industrias creativas, tales como arquitectura, ingeniería, diseño de producto y otras más. En conjunto, Grasshopper y Rhino nos ofrecen la oportunidad de definir control paramétrico preciso sobre nuestros modelos, la capacidad de explorar workflows de diseño generativo, así como una plataforma para desarrollar una lógica de programación de alto nivel - ¡Todo a través una interfaz gráfica e intuitiva!

Los orígenes de Grasshopper pueden ser atribuidos a la funcionalidad del botón
"Record History" contenida en la versión 4 de Rhino3d. Esta característica
permitía a los usuarios guardar implícitamente las operaciones de modelado mientras 
trabajabas. Si le hacías "Loft" a cuatro curvas teniendo el botón de"Record History"
encendido, y después editabas los puntos de control de alguna de estas curvas, la 
superficie se actualizaría automáticamente. En 2008, David planteó la pregunta: 
"¿qué tal si pudiéramos tener explícitamente más control sobre esta historia?", 
y así el precursor de Grasshopper, Explicit History, nació. Éste consiguió exponer 
la cronología de operaciones y abrió la posibilidad de editarlas a detalle, 
empoderando al usuario para desarrollar secuencias lógicas más allá de las 
capacidades básicas de Rhino3d. 

Seis años después, Grasshopper es ahora un robusto editor de programación visual 
que puede ser extendido por suites o por add-ons externos. Más aún, éste ha 
fundamentalmente alterado los workflows de profesionales a lo largo de múltiples 
industrias y ha fomentado una comunidad global activa de usuarios.

Este Primer se enfoca en Los Básicos, ofreciéndote el conocimiento esencial 
que necesitas para surcar hacia el uso regular de Grasshopper, así como 
posibilidades de cómo ir más allá con tu propio quehacer creativo. Antes de continuar 
con las descripciones, diagramas y ejemplos provistos de aquí en adelante, discutamos 
qué es programación visual, los básicos de la interfaz de Grasshopper y la 
terminología adecuada; tal como las características "en tiempo real" de 
retroalimentación del viewport, y la experiencia del usuario.

El Visual Programming, o programación visual, es un paradigma de la programación dentro del que el usuario manipula elementos lógicos gráficamente en vez de textualmente. Algunos de los más conocidos lenguajes de programación textual tales como C#, Visual Basic, Processing - y los más cercanos a Rhino - Python y Rhinoscript, requieren de nosotros escribir código que se atiene a una sintaxis muy específica del lenguaje. En cambio, la programación visual nos permite conectar bloques funcionales a una sequencia de acciones donde la única "sintaxis" requerida es que los inputs de los bloques reciban datos del tipo adecuado, e idealmente, que esté organizada de acuerdo al resultado deseado - después ahondaremos al respecto en las secciones de Data Stream Matching y Diseñando con Data Trees; ¡no os preocupeis! Esta característica de la programación visual evita la barrera de acceso comunmente hallada al tratar de aprender un nuevo lenguaje, incluso uno hablado, y previsualiza la interfaz, lo cual para los diseñadores ubica a Grasshopper dentro de un territorio más familiarizado.

![IMAGE](images/python-and-gh-sine.png)
>Esta imagen compara el proceso para dibujar una curva sinoidal en Python y en Grasshopper.

Para accesar Grasshopper y su funcionalidad de programación visual, necesitamos descargar e instalar el programa desde el sitio de Grasshopper3d.com. Una vez instalado, podemos abrir el plug-in escribiendo "Grasshopper" en la Command Line de Rhino. La primera vez que lo hacemos en una nueva sesión de Rhino, se nos presentará la pantallita de que Grasshopper está cargando, seguida de la ventana principal de Grasshopper. Ahora podremos agregar bloques funcionales llamados "componentes" al "canvas", conectarlos con "cables", y guardar la "definición" completa en el formato .ghx.

![IMAGE](images/gh-definition.png)
>Una definición de Grasshopper en el canvas, hecha de componentes conectados con cables.

Una vez que hayamos comenzado a desarrollar una definición en Grasshopper y hayamos creado "sliders" dentro de nuestro canvas para controlar geometría, quizá naturalmente intuyamos la conexión que hemos hecho entre éstos y lo que vemos en los viewports de Rhino. Esta conexión es esencialmente en tiempo real - si ajustamos el grip del slider, veremos las consecuencias de ello: Dentro de nuestra definición un input ha cambiado en alguna parte y el programa debe ser resuelto nuevamente para recalcular la solución y mostrar la versión más actualizada. Para nuestro beneficio cuando comenzamos con Grasshopper, la geometría que vemos es una ligera representación de la solución y se actualiza automáticamente. Es importante tomar nota de esta conexión en este momento, ya que cuando tus definiciones se vuelvan más complejas, manejar inteligentemente el flujo de datos, el estado del "solver", y lo que se visualiza en el viewport de Rhino, prevendrá muchos dolores de cabeza inesperados. 

![IMAGE](images/flow.png)
>Flujo del programa: de izquierda a derecha.

####PARA RECORDAR
* Grasshopper es un editor gráfico de algoritmos que se integrá con las herramientas de modelado de Rhino3D.
* Los algoritmos son procedimientos paso a paso diseñados con el fin de desempeñar una operación específica.
* Grasshopper es utilizado para diseñar algoritmos que posteriormente automatizan tareas en Rhino3D.
* Una manera fácil de comenzar si no tienes claro como realizar una operación en Grasshopper sería tratar manual e incrementalmente creando un algoritmo usando commandos de Rhino.

Mientras comienzas a explorar Grasshopper o tratas de mejorar tus habilidades con el software, te has unido a la comunidad global de Grasshopper, una que está llena de miembros activos de áreas diversas y con distintos grados de experiencia. El foro en Grasshopper3D.com es un recurso útil para plantear preguntas, compartir descubrimientos, y adquirir conocimiento. Esta es una comunidad que hemos encontrado entrañable a lo largo del tiempo en el que que hemos escrito este primer y hemos observado a Grasshopper crecer con los años. ¡Bienvenidos!
