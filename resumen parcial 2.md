# Resumen parcial 2

# Parámetros

Los parámetros pueden ser formales o reales. Los parámetros **reales** son los valores reales que se le pasan al parámetro cuando se lo llama. Los parámetros **formales** son los nombres que toman los parámetros y se esperan que se pasen a la función o procedimiento, es el identificador.

La ligadura puede ser **posicional** (corresponde a la posición en la lista de parámetros) o por **nombre** (se corresponden con el nombre).

Existen tres modos:

- **IN**: el parámetro formal recibe el dato desde el parámetro real
  - **_Valor_**: se copia el valor cuando se aloca en memoria
  - **_Valor constante_**:
- **OUT**: el parámetro formal envía el dato al parámetro real
  - **_Resultado_**: se copia el valor del parámetro al TERMINAR el procedimiento, es decir, desalocar el registro de memoria.
  - **_Resultado de funciones_**: se copia el valor del resultado de la función en el campo VR del registro llamador
- **IN/OUT**: el parámetro formal recibe el dato del parámetro real y el parámetro formal le envía el dato al real
  - **_Nombre_**: el parámetro formal es sustituido textualmente por el parámetro real. Se busca el dato en la unidad donde pertenece el parámetro real. Si el dato es:
    - Único valor: es lo mismo que el por referencia
    - Constante: es lo mismo que el por valor
    - Elemento de un arreglo: puede cambiar entre las distintas referencias
    - Expresión: se evalúa cada vez.
  - **_Valor resultado_**: se copia al alocar el registro y se modifica el parámetro real al finalizar la ejecución de la rutina.
  - **_Referencia_**: se trabaja directamente sobre la variable que se referencia, cuando paso un parámetro por referencia apunto a la dirección en memoria del parámetro enviado.

El ambiente puede determinarse si la ligadura es:

- **Deep**: El ambiente es el del _subprograma_ donde esta **declarado** el subprograma usado como **parámetro real**. Se utiliza en los lenguajes con alcance estático y estructura de bloque. Es símil a la cadena estática.
- **Shallow**: El ambiente de referencia es el del subprograma que tiene el **parámetro formal** subprograma. Es símil a la cadena dinámica.

# Sistema de tipos

Un sistema de tipos es un conjunto de reglas para clasificar y manipular los datos de un programa.

Un sistema de tipos es **fuerte** cuando existen restricciones y conversiones acerca de los tipos de datos. En este sistema, se garantiza que las operaciones se realicen únicamente entre tipos compatibles y se previenen las conversiones automáticas o implícitas entre tipos que no sean directamente compatibles. Por ejemplo, hay que castear.

Un sistema de tipos es **débil** cuando se permiten conversiones explícitas y automáticas entre diferentes tipos de datos, incluso si no son compatibles.

El tipado es **estático** si realiza verificaciones en tiempo de compilación y **dinámico** si lo hace en ejecución. Estático ofrece seguridad y dinámico flexibilidad.

# Tipos de datos

Un tipo de dato es una clasificación que define la naturaleza y comportamiento de un valor en un lenguaje de programación.

Existen los datos predefinidos que son aquellos que viene con el programa.

Los datos definidos por el usuario son usualmente un conjunto de datos predefinidos y se logra mediante constructores. Separan la especificación (******\*\*\*******crear******\*\*\*******) de la implementación (****\*\*\*\*****usar****\*\*\*\*****).

Los tipos compuestos son construcciones a partir de los predefinidos:

- **Producto cartesiano**: relación 1 a muchos. Son elementos construidos a partir de un conjunto de elementos.
- **Union**: permite combinar tipos de datos en uno solo. En una unión, un valor puede pertenecer a uno de los tipos dentro de la unión. Esto se puede utilizar para representar alternativas o opciones donde un valor puede ser de diferentes tipos.
- **Recursión**: un tipo puede contener instancias de sí mismo como parte de su estructura
- **Correspondencia finita**: relación 1 a 1 entre dos conjuntos. Cada elemento de un conjunto se corresponde con uno de otro conjunto.

La **mutabilidad** tiene que ver con la capacidad de poder cambiar durante la ejecución. La **inmutabilidad** se refiere a la incapacidad de un dato de ser modificado después de su creación. Python ofrece varios tipos de datos inmutables, y Ruby proporciona el método **`freeze`** para hacer que los objetos sean inmutables.

Los punteros son mecanismos muy potentes para generar estructuras recursivas. Por acceder bajo nivel pueden hacer inseguros a los programas que los usan. Las inseguridades del los punteros son: violación de tipos, referencias sueltas, punteros no inicializados, alias, liberación de memoria.

Un tipo abstracto de datos es un conjunto de valores y de operaciones definidos mediante una especificación independiente de cualquier representación. Un TAD debe cumplir con: abstracción, encapsulamiento, modularidad, independencia de implementación y tener su propia identidad y operaciones definidos.

# Excepciones

Una excepción es una situación anomala que ocurre en la ejecución del programa y se espera que no pase.

Para que un lenguaje trate excepciones debe tener un modo de definirlas, de invocarlas, de manejarlas y criterio de continuación.

Existen dos modelos de manejo de excepciones:

- Terminación: cuando ocurre una excepción se corta la ejecución de esa unidad.
- Reasunción: cuando ocurre una excepción se maneja y continua desde donde se quedo después de que salte la excepción. ES MENOS SEGURO, ya que no se garantiza que la excepción se haya resuelto.

La propagación dinámica indica que una vez que se lanza la excepción, si no la trata la unidad que las genero, se propagan dinámicamente. Si un método puede generar excepciones pero decide no manejarlas localmente, debe enunciarlas en su encabezado con throw.

- Java:
  - Modelo: por terminación.
  - Las excepciones son clases que extienden de la clase `Exception`.
  - Existen built-in excepcion y user defined exceptions.
  - Tiene propagación dinámica.
  - Posee bloques try y catch para manejar excepciones. Se pueden anidar.
  - Las excepciones se pueden lanzar con `throw`.
  - Puede haber tantos catch como excepciones maneje el método.
  - El bloque finally se ejecuta SIEMPRE.
  - Si se omite el bloque catch, pero hay un bloque finally, este último se ejecuta antes de propagar la excepción en forma dinámica.
- Python:
  - Modelo: por terminación:
  - Las excepciones derivan de `Exception`.
  - Existen built-in excepcion y user defined exceptions.
  - Bloques try y except. Los bloques try except se pueden anidar.
  - Tiene propagación dinámica y estática. Cuando la excepción ocurre dentro del bloque try, busca el manejador en los except siguientes. Si encuentra el manejador, lo ejecuta y prosigue su ejecución en el bloque de código siguiente al try. En caso de no encontrar el manejador, lo propaga dinámicamente. Si llega al programa principal sin encontrar el manejador, termina en error.
  - Las excepciones se lanzan con `raise`. Si sólo aparece la palabra clave raise, se levanta anónimamente, se vuelve a lanzar la última excepción que estaba activa en el entorno actual, si no hay ninguna se lanza `RuntimeError`.
  - Puede haber tantos except como excepciones se manejen en el código (en un mismo except se pueden manejar varias excepciones)
  - Puede haber un bloque else, que se ejecuta si no se levantó la excepción. También hay un bloque finally que se ejecuta siempre.
  -
- PL/1:
  - Modelo: por reasunción.
  - Las excepciones se declaran con `ON CONDITION nombreManejador` y dentro del begin y end el manejador.
  - Se levantan con la instrucción `SIGNAL CONDITION nombre`.
  - Los manejadores se apilan a medida que se encuentran. Cuando se levanta una excepción se busca el nombre de la misma desde el tope de la pila hacia abajo, el primer manejador que se encuentra es el que se ejecuta.
  - Excepciones con el mismo nombre se enmascaran entre sí.

# Estructuras de control

Una sentencia simple tiene una única acción. Una sentencia compuesta agrupa varias sentencias en un bloque delimitado por llaves o otro delimitador; estas sentencias se ejecutan en secuencia y se consideran como una sola unidad.

Las sentencias pueden ser: asignación, expresión, retorno o llamadas a funciones.

Un efecto lateral es cualquier cambio o acción que se produce además de la asignación del valor a la variable. Un ejemplo de efecto lateral en una expresión de asignación en C es el operador de incremento (**`++`**) o decremento (**`--`**).

Las sentencias de selección pueden ser por circuito corto donde se evalúa hasta encontrar un false o por circuito largo donde se evalúa la sentencia completa.

<aside>
🔥 La regla del ***else ambiguo*** la usa ADA y C y establece que el else se va a asociar con el if más cercano y no resuelvo.

</aside>

# Paradigmas

- **Funcional**: los programas se componen de funciones. El lugar donde se definen las funciones se conoce como contexto léxico o ámbito léxico. El contexto léxico es el entorno en el que una función es definida y determina las reglas de visibilidad y alcance de dicha función.
  Las variables son inmutables. En lugar de trabajar con variables mutables, se enfatiza el uso de expresiones y funciones puras que no tienen efectos secundarios y producen resultados basados únicamente en los valores de entrada.
  La forma de evaluar las expresiones es a través de un mecanismo de **reducción o simplificación.**
  - Orden aplicativo: Aunque no sea necesario, siempre evalúa todos los argumentos.
  - Orden normal (lazy evaluation): No calcula más de lo necesario. La expresión no es evaluada hasta que su valor lo necesite. Una expresión compartida no es evaluado más de una vez.
  - Diferida (Haskell): es una evolución del orden normal.
- **Orientado a objetos**: conjunto de objetos que interactúan entre sí enviándose mensajes para realizar tareas. Los objetos son instancias de clases que encapsulan datos y comportamientos relacionados. El programa se estructura en base a la modularidad y la reutilización de código a través de la creación y manipulación de objetos.
  Los componentes son: mensajes, métodos y clases.
  El primer nivel de abstracción es la de datos, definimos estructura, comportamientos y tenemos ocultamiento.
  El segundo nivel de abstracción es la herencia, permite crear nuevas clases basadas en clases existentes, heredando sus atributos y comportamientos. Existe la herencia simple y la múltiple.
- **Lógico**: una variable representa un símbolo que puede tomar diferentes valores. Las variables son inmutables. Las constantes, por otro lado, representan valores fijos y predefinidos en el sistema lógico.
  Un programa escrito en lenguaje lógico es una secuencia de “cláusulas” que pueden ser hechos o reglas.
  - _Hechos_: representan una relación entre objetos y se consideran verdaderos siempre
  - _Reglas_: tiene la forma de `conclusión .- (sí) condición`. Conclusión es siempre un predicado y condición es un conjunto de predicados separados por comas. Representan un AND lógico. Análogamente, es el if de un lenguaje imperativo/procedural.
- **Imperativo**: sentencias y secuencias de comandos.
- Scripts: Los lenguajes basados en scripts son aquellos diseñados para la escritura de scripts, que son programas pequeños y ágiles utilizados para automatizar tareas o realizar operaciones específicas.
