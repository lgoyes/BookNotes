# Código Limpio: Manual de estilo para el desarrollo ágil de software

**Author**: Robert Martin

**Language**: Español

**Start date**: Jan 21st, 2021.

**End date**: May 21st, 2021.

## Índice

1. [Código Limpio](#1-código-limpio)
2. [Nombres con Sentido](2-nombres-con-sentido)
3. [Funciones](#3-funciones)
4. [Comentarios](#4-comentarios)
4. [Formato](#4-formato)

## 1. Código Limpio

### Hágase el código

* El final del código está próximo. Que los programadores ya no serán necesarios porque los empresarios generarán programas a partir de las especificaciones.
* El código nunca desaparecerá, ya que reprsenta los detalles de los requisitos. En algún nivel, dichos detalles no se pueden ignorar ni abstraer; deberán especificarse.
* Las máquinas tendrían que entendernos de tal forma que puedan traducir necesidades ambiguas en programas perfectamente ejecutados que satisfagan dichas necesidades a la perfección.
* Unos requisitos bien especificados son tan formales como el código y pueden actuar como pruebas ejecutables de dicho código.

### Código Incorrecto

* El código correcto es relevante.
* Habían comercializado el producto antes de itmepo, con graves fallos en el código. Al añadir nuevas funciones, el código empeoró hasta que ya no pudieron controlarlo.
* El código incorrecto le ha supuesto un obstáculo. ¿Por qué lo escribió? ¿Tenía prisa? ¿Pazos de entrega?
* Un programa que funcione es mejor que nada.
* Ley de LeBlanc: Después es igual a nunca.

### El coste total de un desastre

* Cada cambio en el código afecta a dos o tres partes del mismo. Ningún cambio es trivial. Para ampliar o modificar el sistema es necesario comprender los detalles, efectos y consecuencias, para añadir más detalles, efectos y consecuencias.
* Al aumentar el desastre, la productividad del equipo odisminuye y acaba por desaparecer. Al reducirse la productividad, el director aumenta la plantilla con la esperanza de aumentar la producividad. Pero esa plantilla no conoce el diseño del sistema.

### El gran cambio de diseño

* El equipo se rebela. Informan que no pueden seguir trabajando con ese código.
* Se crea un nuevo equipo para rehacer un nuevo proyecto. El nuevo proyecto debe hacer lo que el antiguo no puede. Ademeas, debe asumir los cambios continuos al sistema antiguo. El sistema antiguo no se reemplazará, a menos que el nuevo sea capaz de hacer todo lo que hace el viejo.

### Actitud

* La culpa es nuestra. No somos profesionales.
* ¿Qué pasa con los requisitos? ¿Y los plazos de entrega? ¿Y los directivos incompetentes y los vendedores sin sentido?
    * Los directores y comerciales nos exigen la información que necesitan para realizar sus promesas y compromisos, e incluso cuando no recurren a nosotros, no debemos tener miedo a decirles lo que pensamos.
    * Seguro piense que si no lo hace, lo despedirán. Es improbable. Muchos jefes solo quieren la verdad, aunque lo disimulen. Muchos quieren código correcto, aunque estén obsesionados con los objetivos.

### El enigma

* No se cumple un plazo de entrega cometiendo un error. De hecho, el error nos ralentiza de forma inmediata y hace que no lleguemos al plazo de entrega. La única forma de avanzar, es intentar que el código siempre sea limpio.

### ¿El arte del código limpio?

* Reconocer código limpio no significa que sepamos como crearlo.

### Concepto de código limpmio

#### Bjarne Stroustrup

* El código limpio es un placer a la hora de leerlo.
* Los ciclos malgastados no son elegantes, no son un placer.
* Un edificio con ventanas rotas parece abandonado, y hace que otros lo abandonen.
* El código limpio hace una cosa bien.
* El código limpio es concreto. Cada función, cada clase y cada módulo muestra una única actitud que se mantiene invariante y no se contamina por los detalles circundantes.

#### GRady Booch

* El código limpio se puede leer como un texto bien escrito.
* Nítida abstracción: El código debe ser específico, y no especulativo.

#### Dave Thomas

* El código limpio facilita las labores de mejora de otros.
* Existe una diferencia entre el código fácil de leer y el código fácil de cambiar.
* El código sin pruebas, no es limpio.

#### Michael Feathers

* Cómo dar importancia al código.
* Alguien se ha dedicado para que sea sencillo y ha prestado atención a los detalles. Se ha preocupado.

#### Ron Jeffries

* Ejecuta todas las pruebas
* No contiene duplicados
* Expresa todos los conceptos de diseño del sistema
* Minimiza el número de entidades como clases, métodos, funciones y similares.

#### Wward Canningham

* Trabajamos con código limpio cuando cada rutina que leemos resulta ser lo que esperábamos.
* Ward espera que al leer código limpio no le sorprenda. De hecho, ni siquiera tendrá que esforzarse. Lo leerá y prácticamente será lo que esperaba. Será evidente, sencillo y atractivo.
* No es el lenguaje el que hace que los programas parezcan sencillos, sino el programador que consigue que el lenguaje lo parezca.

### Escuelas de pensamiento

* Ninguna escuela tiene la razón absoluta, pero dentro de cada una actuamos como si las enseñanzas y técnicas fueran correctas.
* Las correcciones dentro de una escuela determinada, no anula las ensennanzas de otra diferente.
* No cometa el error de pensar que somos los únicos que tenemos la razón.

### Somos autores

* La próxima vez que escriba una línea de código, recuerde que es un autor y que escribe para que sus lectores juzguen sus esfuerzos.
* La proporción entre tiempo dedicado a leer frente a tiempo dedicado a escribir es más de 10:1. Al ser una proporción tan elevada, queremos hacer que la lectura sea sencilla, aunque eso complique su creación

### La regla del Boy Scout

* Si todos entregamos el código más limpio de lo que lo hemos recibido, no se corremperá. No hace falta que la limpieza sea masiva
    * Cambie el nombre de una variable, divida una función demasiada extensa, elimine elementos duplicados, simplifique un condicional.

## 2. Nombres con Sentido

### Introducción

* En el software, los nombres son omnipresentes. Aparecen en variables, funciones, argumentos, clases y paquetes. Usamos nombres constantemente. Por ello, debemos hacerlo bien.

### Usar nombres que revelen las intenciones.

* Los nombres deben revelar nuestras intenciones.
* Elegir nombres correctos lleva tiempo, pero también ahorra trabajo.
* Preste atención a los nombres y cámbielos cuando encuentre otros mejores.
* Debe indicar por qué existe, qué hace y cómo se usa. 
* El problema no es la simplicidad del código sino su carácter implícito: el grado en que el contexto no es explícito en el propio código.

### Evitar la desinformación

* Evite dejar pistas falsas que dificulten el significado del código.
* No haga referencia a un grupo de cuentas como `acountList` a menos que realmente sea una lista.
* Evite usar nombres con variaciones mínimas.
* El uso de ortografía incoherente es desinformación.
    * Es muy útil si los nombres de los elementos similares se ordenan alfabéticamente y si las diferencias son muy evidentes.

### Realizar distinciones con sentido

* Si los nombres tienen que se distintos, también deben tener un significado diferente.
* Los nombres de series numéricas (a1, a2, ..., aN) no ofrecen información.
* Las palabras adicionales son redundantes y no aportan información. ¿Cuál es la diferencia entre `ProductInfo` y `ProductData`? ¿Es mejor `NameString` que `Name`? La palabra `table` no debe incluirse en el nombre de una tabla.

### Usar nombres que se pueden pronunciar

* Cree nombres pronunciables. Si no lo puede pronunciar, no podrá explicarlo sin parecer tonto.

### Usar nombres que se pueden buscar

* Si una variable o constante se usa en varios puntos del código, debe asignarle un nombre que se pueda buscar.
* Se puede buscar `MAX_CLASSES_PER_STUDENT` pero no el número `7`.
* Es mucho más fácil buscar `WORK_DAYS_PER_WEEK`, que todas las instancias de `5`.

### Evitar codificaiones

* Los nombres codificados resultan impronunciables y suelen escribirse de forma incorrecta.

### Notación húngara.

* El compilador no comprobaba los tipos, de modo que los programadores tenían que recordarlos.
* El tipado es fuerte ey los entornos de edición han avanzado tanto que detectan un error de tipo antes de ejecutar la compilación.
* La notación húngara hace más complicado cambiar el nombre o tipo de una variable o clase. Dificultan la legibilidad del código y pueden hacer que el sistema de codificaci´øn confunda al lector.

### Prefijos de miembros

* Tampoco es necesario añadir `m_` como prefijo a los nombres de variables. Use un entorno de edición que resalte o coloree los miembros para distinguirlos.

### Interfaces e implementaciones

* ¿Qué nombres asigno a la interfaz y a la implementación? ¿`IShapeFactory` y `ShapeFactory`? Prefiero que las interfaces no tengan adornos. Es mejor usar `ShapeFactoryImpl`.

### Evitar asignaciones mentales

* Los lectores no tienen que traducir mentalmente sus nombres en otros que ya conocen. Ete problema suele aparecer al elegir entre no usar términos de dominio de problema o de soluciones.
* Si puede recordar que `r` es la versión en minúscula de una URL sin el host y el sistema, debe ser muy inteligente.
* Una diferencia entre un programador inteligente y uno profesional, es que este último sabe que la claridad es lo que importa.

### Nombre de clases

* Las clases y objetos deben tener nombres de sustantivos

### Nombres de métodos

* Los métodos deben tener nombres de verbos

### No se exceda con el atractivo

* Opte por la claridad antes que por el entretenimiento
* No use nombres divertidos. No recurra a bromas.

### Una palabra por concepto

* resulta confuso usar `fetch`, `retrieve` y `get` como métodos equivalentes de clases distintas. Elija una palabra por cada concepto abstracto y mantengala.

### No haga juegos de palabras

* Evite usar la misma palabra con dos fines distintos.
* Imagine que hay varias clases en las que `add` crea un nuevo valor sumando o concatenando dos valores existentes. Imagine ahora que crea una clase nueeva con un método que agrega un parámetro a una colección. Parece coherente usar `add`, pero en este caso hay una diferencia semántica, de modo que se debe usar nombres como `insert` o `append`.

### Usar nombres de dominios de soluciones

* El nombre `AccountVisitor` tiene mucho significado para un programador familiarizado con el patrón VISITOR. ¿Qué programador no sable lo que es `JobQueue`? Hay cientos de cosas técnicas que los programadores tienen que hacer y elegir nombres técnicos para dichas cosas suele ser lo más adecuado.

### Usar nombres de dominios de problemas

* Si usa nombres sde dominio de problemas, al menos el programador que mantenga el código podrá preguntar su significado a un experto en el dominio.

### Anadir contexto con sentido

* Algunos nombres tienen significado por sí mismos, pero la mayoría no. Para ello, debe incluirlos en un contexto, en clases y funciones con nombres adecuados.
* Puede añadir contexto por medio de prefijos, permitiendo al lector entender que las variables forman parte de una estructura mayor. Evidentemente, es mejor crear una clase.

### No añadir contextos innecesarios

* En la aplicación `Gas Station Delux`, no es aconsejable usar el prefijo `GSD` en todas las clases.
* Los nombres breves suelen ser más adecuados que los extensos, siempre que sean claros. No añada más contexto del necesario a un nombre.

## 3. Funciones

* ¿Entiende la función? Seguramente no. Pasan demasiadas cosas y hay demasiados niveles de abstracción diferentes. Hay cadenas extrañas e invocaciones de funciones mezcladas e instrucciones `if` doblemente anidadas, controladas por banderas.

### Tamaño Reducido

* La primera regla de las funciones es que deben ser de tamaño reducido.
* Las funciones deben tener una longitud aproximada de 20 líneas.
* Toda slas funciones deben ser obvias, contar una historia y cada una llevar a la siguiente en un orden atractivo.

### Bloques y Sangrado

* Los bloques en las instrucciones `if`, `else` y `while` deben tener una línea de longitud que, seguramente sea la invocación de una función.
* El nivel de sangrado de una función no debe ser mayor de uno o dos.

### Hacer una sola cosa

* Las funciones solo deben hacer una cosa, deben hacerlo bien y debe ser lo único que hagan.
* Si una función solo realiza los pasos situados un nivel por debajo del nombre de la función, entonces hace una cosa.
* Creamos funciones para descomponer conceptos más amplios en un conjunto de pasos en el siguiente nivel de abstracción.

### Secciones en funciones

* Las funciones que hacen una sola cosa no se pueden dividir en secciones.

### Niveles de abstracción por función

* Las instrucciones de una función deben esetar en el mismo nivel de abstracción.
* La mezcla de niveles de abstracción es conofusa. No se sabe si una determinada expresión es un concepto esencial o un detalle.

### Leer código de arriba a abajo: la regla descendente.

* Tras todas las funciones, deben aparecer las del siguiente nivel de abstracción, para poder leer el programa.

### Instrucciones Switch

* Es complicado hacer una instrucción switch hque haga una sola cosa.
* No siempre podemos evitar los switch, pero podemos incluirlos en un nivel inferior y no repetirlo. Para ello, recurrimos al polimorfismo.
* Las instrucciones switch se pueden tolerar si solo aparecen una vez, se usan para crear objetos polimórficos y se ocultan tras una relación de herencia para que el resto del sistema no pueda verlas.

### Usar nombres descriptivos

* Cuanto más reducida y concreta sea la función, más sencillo será elegir un nombre descriptivo.
* No tema los nombres extensos. Un nombre extenso descriptivo es mejor que uno breve y enigmático.
* La elección de nombres descriptivos clarifica el diseño de los módulos y le permite mejorarlos.

### Argumentos de funciones

* El número ideal de argumentos para una función es cero. Después uno y dos. Siempre que sea posible, evite la preesencia de tres argumentos, require una justificación especial.
* El argumento podría estar a un nivel distinto de abstracción que el nombre de la función y nos obliga a conocer un detalle de implementación que no es importante.
* Los argumentos son todavía más complicados desde un punto de vista de pruebas. Hay que hacer todos los casos de prueba para garantizar el funcionamiento de las distintas combinaciones de argumentos.

### Formas monádicas habituales

* Hay dos motivos principales para pasar un solo argumento a una función.
    1. Puede que realice una pregunta sobre el argumento
    2. Puede que procese el argumento, lo transforme en otra cosa, y lo devuelva.
* Otra forma de un argumento es un evento
    * El programa debe interpretar la invocación de la función como evento, y alterar el estado del sistema.

### Argumentos bandera (booleanos)

* Los argumentos bandera complican la firma del método e indica que la función hace más de una cosa. Tendría que dividir la función en dos.

### Funciones diádicas

* Puede convertir una función diádica en un miembro de uno de los argumentos para convertirla en monádica.

### Objeto de argumento

* Cuando una función parece necesitar dos o más argumentos, es probable que algunos de ellos se incluyan en una clase propia.

### Verbos y Palabras clave

* La selección de nombres correctos para una función mejora la explicación de su cometido así como el orden y el cometido de los argumentos.

### Sin efectos secundarios

* Los Los efectos secundarios son mentiras. Su función promete hacer una cosa, pero también hace otras cosas ocultas. En ocasiones realiza cambios inesperados en las variables de su propia clase.
* Los efectos secundarios general acomplamientos temporales. Es decir, solo se puede invocar la función en determinados momentos. Si no se invoca en orden, se pueden tener efectos inesperados.

### Argumentos de salida

* Por lo general, los argumentos de salida deben evitarse. Si su función tiene que cambiar el estado de un elemento, haga que cambie el estado de su objeto contenedor.

### Separación de consultas de comando

* Las funciones deben hacer algo, o responder a algo. No ambas cosas.
* La función debe cambiar algo del objeto, o devolver información del mismo, pero no ambas cosas.

### Mejor excepciones que devoler códigos de error

* Al devolver un código de error, el invocador debe procesar el error de forma inmediata. Esto genera estructuras anidadas.
* Si uso excepciones, el código de procesamiento se separa del código de ruta y se puede simplificar

### Extraer bloques try/catch

* Extraiga el cuerpo de los bloques try y catch en funciones individuales.

### El procesamiento de errores es una cosa

* Una función que procese errores no debe hacer nada más

### No repetirse

### Programación estructurada

* Si sus funciones son de tamaño reducido, una instrucción return, break o continue no harán daño y pueden resultar más expresiva que la regla de una entrada y una salida.

### Como crear este tipo de funciones

* Cuando se crean las funciones, se suele empezar con funciones extensas y complicadas, con abundancia de sagrados y bucles anidados. Con extensas listas de argumentos, nombres arbitrarios y código duplicado.
* Siempre y cuando se tenga una serie de pruebas unitarias que abarquen todas las líneas de código, siempre se puede refactorizar.

## 4. Comentarios

* No hay nada más útil que un comentario bien colocado. No hay nada que colapse más un módulo que comentarios dogmáticos innecesarios. no hay nada más dañino que un comentario antiguo que propague mentiras y desinformación.
* El uso correcto de comntarios permite compensar nuestra incapacidad para para expresarnos en el código.
* Los comentarios mienten. No siempre y no siempre intencionadamente, pero lo hacen. Cuando más antiguo es un comentario y más se aleja del código que describe, mayor es la probabilidad de que sea equivocado.
* Se prodría afirmar que los programadores deben ser lo bastante disciplinados como para mantener los comentarios actualizados, relevantes y precisos. De acuerdo, debería, pero esa energía debería invertirse en crear código claro y expresivo que no necesite comentario alguno.

### Los comentarios no compensar el código incorrecto.

* En lugar de comentar un módulo confuso y desorganizado, límpielo.
* El código claro y expresivo sin apenas comentarios es muy superior al código entrevesado y complejo con multitud de comentarios.

### Explicarse en el código

* En muchos casos, basta con crear una funcióno que diga lo mismo que el comentario que pensaba escribir.

### Comentarios de calidad

#### Comentarios legales

* Algunos estándares corporativos de creación de código nos obligan a crear determinados comentarios por motivos legales.

#### Comentarios informativos

* En ocasiones es útil proporcional información básica con un comentario.

#### Explicar la intención

* En ocasiones, un comentario es algo más que información útil sobre la implementación y proporciona la intención de una decisión.

#### Clarificación

* En ocasiones, basta con traducir el significado de un argumento o valor devuelto, en algo más legible.

#### Advertir de las consecuencias

#### Comentarios TODO

* TODO son tareas que el programador piensa que debería haber hecho, pero que no es así. Puede ser un recordatorio para eliminar una función obsoleta o una petición para resolver un problema.

#### Amplificación

* Se amplía la importancia de algo que, en caso contrario, parecería irrelevante.

#### Javadoc en API públicas.

### Comentarios incorrectos

* Excusas de código pobre o justificaciones de decisioines insuficientes

#### Balbucear

* Cualquier comentario que le obligue a buscar su significado en otro módulo, ha fallado en su intento de comunicación.

#### Comentarios redundantes

* ¿Para qué sirve este comentario? No es más informativo que el código. No lo justifica, ni transmite la intención, ni la lógica. No es más fácil de leer que el código. De hecho, es menos preciso y obliga al lector a aceptar la faclta de precisión en lugar de a entenderlo.
* Estos comentarios solo ensucian y oscurecen el código. No tienen función documental.

#### Comentarios confusos

* Un comentario confuso puede hacer que un programador invoque una función de forma equivocada.

#### Comentarios Obligatorios

* Los javadoc obligatorios para todas las funciones, crean abominaciones que no sirven de nada, complican el código y constituyen posibles engaños y desorientaciones.

#### Comentarios periódicos.

* Gracias a los sistemas de control de versiones, no se necesita llevar registro de las modificaciones al código.

#### Comentarios sobrantes

* Algunos comentarios restan importancia a lo evidente y no ofrecen información nueva
* En lugar de crear elementos sobrantes, debe limpiar su código

#### Comentarios sobrantes espeluznantes

* Si el autor de un comentario no presta atención al escribir sus comentarios (copiarlos y pegarlos), ¿Por qué se espera que sean de utilidad para los lectores?

#### No usar comentarios si se puede usar una función o una variable

#### Marcadores de posición

* Los maracores de posición son atractivos si no los usa demasiados. Por ello, úselos esporádicamente y solo cuando el beneficio sea significativo.

#### Comentarios en llave de cierre

* Aunque pueda tener sentido en funciones extensas con estructuras anidadas, únicamente estorba a las funciones encapsuladas y de pequeño tamaño.
* Si siente el deseo de marcar sus llaves de cierre, pruebe a reducir el tamaño de sus funciones.

#### Asignaciones y menciones

* Los sitemas de control de versiones recuerdan a la perfección quién ha añadido qué y cuando. No es necesario plagar el código con pequeñas menciones.

#### Código comentado

* Los lectores que vean código comentado no tendrán el valor de borrarlo. Pensarán que está ahí por algo y que es demasiado importante para borrarlo.
* Elimine el código comentado. El sistema de control de versiones recuerda el código fuente por nosotros.

#### Comentarios HTML

* Los comentarios no deberían estar adornados con etiquetas HTML. Eso dificulta la lectura d elos comentarios.

#### Información no local

* Describa el código que le rodea. No ofrezca ninguna información global del sistema en el contexto de un comentario local. El comentario debe describir la función y no una parte distinta del sistema.

#### Demasiada información

* No incluya en sus comentarios relfexiones históricas ni irrelevantes descripciones de detalles.

#### Conexiones no evidentes

* Se espera que el lector que vea el comentario entienda a qué se refiere.

#### Encabezados de función

* Un nombre bien elegido para una función que hace una sola cosa, suele ser mejor que un encabezado de comentario

#### Javados en código no público

* La formalidad de javadoc en código no dirigido a consumo público no es más que una distracción.

## 5. Formato

* Debe preocuparse por el formato de su código. Debe elegir una serie de reglas sencillas que controlen el formato del código y, después, aplicarlas de forma coherente.
* Si trabaja en equipo, debe acordar una serie de reglas que todos debem cumplir.

### La función del formato

* La funcionalidad que cree hoy es muy probable que cambie en la siguiente versión, pero la legibilidad del código establece los precedentes que afectan la capacidad de mantenimiento del mismo.

### Formato vertical

* Aparentemente se pueden crear sistemas a partir de archivos de unas 200 lineas de longitud con un límite máximo de 500.
* Los archivos pequeños se entienden mejor que los grandes.

#### La metáfora del periódico

* Un archivo de código odebe ser como un artículo de periódico. El nombre debe ser sencillo, pero claro. Los elementos superiores del archivo deben proporcionar conceptos y algoritmos de nivel superior. Los detalles deben aumentar según avanzamos.

#### Apertura vertical entre conceptos

* Cada grupo de líneas representa un pensamiento completo. Estos pensamientos deben separarse mediante líneas en blanco.

#### Densidad vertical

* Si la apertura separa los conceptos, la densidad vertical implica asociaciones. Por tanto, las líneas de código con una relación odirecta, deben aparecer verticalmente densas.

#### Distancia vertical

* Los conceptos relacionados entre sí deben mantenerse juntos verticalmente.
* No debe separar conceptos relacionados en archivos independientes, a menos que tenga un motivo de peso. Por esta razón, deben evitarse las variables protegidas.

#### Declaraciones de variables

* Las variables deben declararse de la forma más aproximada a su uso.

#### Variables de instancia

* Las variables de instancia deben declararse en la parte superior de la clase. Lo importante es declararlas en un punto conocido para que todos sepan dónde buscarlas
* La variable de instancia debería usarse en muchos, sino en todos, los métodos.

#### Funciones dependientes

* Si una función oinvoca otra, deben estar verticalmente próxiimas, y la función de invocación deben estar por encima de la invocada, siempre que sea posible.

#### Afinidad conceptual

* Cuanto mayor sea la afinidad entre dos conceptos, menor distancia vertical debe existir entre ellos.
* Hay afinidad cuando una función invoca otra. Pero también la hay cuando un grupo de funciones realiza una operación similar.

#### Orden vertical

* La función invocada debe situarse por debajo de la que realiza la invocación.

#### Formato horizontal

* No debería tener líneas de más de 120 caracteres.

#### Apertura y densidad horizontal

* Las instrucciones de asignación tienen dos elementos principales: el lado izquierdo y el derecho. Los espacios acentúan esta separación.
* No se incluyen espacios entre el nombre de la función y el paréntesis de aperttura, porque el nombre y los argumentos están estrechamente relacionados.

#### Alineación horizontal

* La alineaación horizontal no es útil.
* Si hay una lista extensa de declaraciones, se debe dividir la clase.

#### Sangrado

* Un archivo de código es una jerarquía. Cada nivel de la jerarquía es un ámbito en el que se pueden declarar nombres y en el que se interpretan declaraciones e instrucciones ejecutables.
* Las líneas a la izquierda se alinean para ver el ámbito al que pertenecen.
* Los programadores dependen de este sistema de sangrado.

#### Romper el sangrado

* En lugar de escribir todo en una línea, prefiero desplegar y sangrar los ámbitos.

#### Ámbitos ficticios

* Evitar instrucciones `while` y `for` con cuerpo ficticio

### Reglas de equipo

* Todo programador tiene sus reglas de formato preferidas, pero si forma parte de un equipo, el equipo manda.
* El estilo debe ser coherente y dinámico.

## 6.
