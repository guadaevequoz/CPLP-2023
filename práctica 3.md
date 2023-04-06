# Práctica 3

# Semántica

1.  La semántica es el significado de símbolos, frases y palabras de un programa. Se pasa a esta etapa una vez que no hay errores sintácticos. En otras palabras, le da significado al código. Existen dos tipos de semánticas: estática y dinámica. La semántica estática que define los errores antes de la ejecución, está relacionado con las formas válidas. La semántica dinámica evalúa errores durante la ejecución, describe el significado de ejecutar las diferentes construcciones del lenguaje de programación, influye en la interacción con el usuario y errores de programación.
2.  .

    a. Compilar un programa significa transformar el código fuente escrito en un lenguaje de programación de alto nivel en un lenguaje de bajo nivel que la computadora pueda entender y ejecutar. El resultado final de la compilación es un archivo ejecutable que puede ser cargado y ejecutado por la computadora. La compilación es un paso importante en el desarrollo de software ya que garantiza que el código esté libre de errores y que pueda ser ejecutado en diferentes plataformas y sistemas operativos.

    b. El proceso de compilación implica varios pasos:

    - Análisis léxico: se utiliza el programa scanner y hace el analisis a nivel de palabra/lexema. Divide el programa en elementos para evaluar la validez de cada uno. Detecta errores si la entrada no coincide con ninguna categoría léxica. El resultado es el descubrimientos de items léxicos y tokens.
    - Análisis sintáctico: se utiliza el programa Parser y se realiza el análisis a nivel sentencia. Se identifican esructuras ayudandose con tokens. Este analisis está entre el léxico y el semántico. Se utilizan técnicas de gramáticas formales y se realizan árboles sintácticos.
    - Análisis semántico: es la semántica estática. Se procesan las estructuras del analizados sintáctico. Se agrega információn implicita como las variables no declaradas. Se evaluan tipos, se agregan descriptores, se realizan comprobaciones de códigos duplicados, problemas de tipos, de nombres, etc.
    - Generación de código intermedio: Realiza la transformación del código fuente a una representación de código intermedio para una máquina abstracta. Pasa todo el código a secuencia de proposiciones de la forma `x:=y op z`.
    - Optimización del código: es optativo y son herramientas que se utilizan para depurar errores en el código.

    c. La semántica aparece en la etapa de análisis y es una de las partes más importantes ya que es la previa a la generación de código intermedio. Encuentra los últimos errores que pueden haber arrastrado el análisis léxico y sintáctico. Se enfoca en encontrar el significado de las sentencias.

3.  No es lo mismo compilar un programa que interpretarlo puesto que son dos formas diferentes de traducir y ejecutar el código de un programa. Un compilador produce un archivo ejecutable a partir del código fuente y lo ejecuta directamente en la computadora, mientras que un interprete traduce el código fuente en tiempo real y lo ejecuta sin generar un ejecutable previamente.
4.  Un error sintáctico es un error en la estructura o gramática del lenguaje que impide que el código se compile o se ejecute correctamente. Por otro lado, un error semántico se produce cuando el código se ejecuta pero no realiza la acción deseada o produce resultados incorrectos debido a una mala interpretación del significado de las instrucciones.
    Por ejemplo, un error sintáctico común en Python es no poner los dos puntos al final de la declaración del bucle for:

    ```python
        for i in range(10)
            print(i)
    ```

    Este código genera un error de sintaxis porque falta “:” después de la declaración del bucle for. En cambio el siguiente error presenta un error semántico:

    ```python
        x = 5
        y = 7
        suma = x - y
        print("el resultado de la suma es:", suma)
    ```

    Puesto que suma calcula una resta con el operador “-” y no con el operador “+”. El programa se ejecutará sin problemas pero produce resultados incorrectos.

5.  .

    a. Los errores son:

    1.  Sintáctico. Una variable no puede comenzar con un dígito.
    2.  Sintáctico. Una asignación se hace con el símbolo “:=”.
    3.  Semántico. La variable “i” no se declara en el for.
    4.  Semántico. Se trata de sumar a la variable “a” del tipo char un número.
    5.  Semántica. ‘a’ no está inicializada.

    ```pascal
                Program P
                var 5: integer; (1)
                var a: char; (5)
                Begin
                	for i:=5 to 10 do begin (3)
                		write(a);
                		a=a+1; (2) (4)
                		end;
                End.
    ```

    b. Los errores son:

    6.  Semántico. La variable i se esta decrementando en vez de incrementando en el bucle.
    7.  Semántico. La función debe devolver un String y devuelve true que es boolean.
    8.  Semántico. La asignación de valores a la lista en la línea (8) no tiene sentido lógico. Se está asignando un valor booleano que indica si el número es mayor que el índice del bucle. Esto no tiene relación con la generación de la tabla de multiplicar y, además, la asignación es incorrecta. Debería ser listado.set(i-1, numero > i).
    9.  Sintáctico. Se utiliza el casteo (BOOLEAN) y deberia ser en minusculas.
    10. Sintáctico. Trata de acumular en result y result es string.
    11. Sintáctico. La variable “i” no está declarada del for.
    12. Sintáctico. No se puede asignar un valor a un objeto obtenido mediante un get a un array list. Tiene que ser con un set.
    13. Lógico. La variable "result" se inicializa con el valor null y se concatena con una cadena en cada iteración del bucle. Esto provocará un error NullPointerException cuando se intente concatenar una cadena con un valor nulo. La variable debería inicializarse con una cadena vacía ("") en lugar de null.

    ```java
            public String tabla(int numero, arrayList<Boolean> listado)
            {
            	String result = null;
            	for(i = 1; i < 11; i--) {
            		result += numero + "x" + i + "=" + (i*numero) + "\n";
            		listado.get(listado.size()-1)=(BOOLEAN) numero>i; (8)
            	}
            	return true;
            }
    ```

    c. 14. Sintáctico. No está definida con un tipo la variable “encabezado”. 15. Sintáctico. El comentario cuando llama a la funcion “final()” no está correctamente inicializado con los caracteres “/\*” 16. Semántico. Como no se abren llaves “{}” ni se identó la función “cuadrado(indice)” nunca se ejecutará la función, de esta manera no cumple con el objetivo. 17. Semántico. La función “final()” no está definida. 18. Semántico. Está mal definida la función “cuadrado” puesto que no se la llama con el int adelante. 19. Semántico. No se crea la funcion cuadrado y tampoco la funcion numero puesto que tiene un ; en vez de (). 20. Semántico. En número_cuadrado utiliza == y esto es un símbolo de comparación, no de asignación. 21. Semántico. El parametro número no tiene definido el tipo.

    ```c
            # include <stdio.h>
            int suma; /* Esta es una variable global */
            int main()
            {
            	int indice;
            	encabezado; (1)
            	for (indice = 1 ; indice <= 7 ; indice ++)
            	cuadrado (indice);
            	final(); Llama a la función final */
            	return 0;
            }
            cuadrado (numero)
            int numero;
            { int numero_cuadrado;
            	numero_cuadrado == numero * numero;
            	suma += numero_cuadrado;
            	printf("El cuadrado de %d es %d\n",
            	numero, numero_cuadrado);
            }
    ```

    d. 22. Sintáctico. Le faltan los paréntesis a todos los print print. 23. Sintáctico. No existe el MOD en python. 24. Sintáctico. Le faltan los paréntesis a las condiciones del if. 25. Semántico. “r = True” está mal puesto que se utiliza un símbolo de asignación en vez de uno de comparación 26. Semántico. N es del tipo string y no permite hacer una comparacion de string y numero de ese tipo. Pasa lo mismo con r al final cuando se pregunta si continua la ejecución o no. 27. Semántico. El simbolo ^ no es para hacer raíz, es para comparar bytes. Para elevar es \*\*.

    ```python
                #!/usr/bin/python
                print "\nDEFINICION DE NUMEROS PRIMOS"
                r = 1
                while r = True:
                	N = input("\nDame el numero a analizar: ")
                	i = 3
                	fact = 0
                	if (N mod 2 == 0) and (N != 2):
                		print "\nEl numero %d NO es primo\n" % N
                	else:
                		while i <= (N^0.5):
                			if (N % i) == 0:
                				mensaje="\nEl numero ingresado NO es primo\n" % N
                				msg = mensaje[4:6]
                				print msg
                				fact = 1
                			i+=2
                		if fact == 0:
                			print "\nEl numero %d SI es primo\n" % N
                	r = input("Consultar otro número? SI (1) o NO (0)--->> ")
    ```

    e. 😴🥱

6.  En Ruby, las variables self y nil tienen diferentes significados y usos en el lenguaje:

    - self: Es una variable predefinida que hace referencia al objeto actual. En otras palabras, self se refiere al objeto que está siendo ejecutado en ese momento. Se usa principalmente para acceder a los métodos y propiedades de ese objeto.
    - nil: Es un valor especial que representa la ausencia de un valor o una referencia nula. En otras palabras, nil se utiliza para indicar que una variable no tiene un valor asignado. Se puede pensar en nil como una especie de "nada" en Ruby. También se utiliza como un valor de retorno por defecto para los métodos que no devuelven nada.

    En resumen, la variable self se utiliza para acceder al objeto actual y sus métodos/propiedades, mientras que nil se utiliza para indicar la ausencia de un valor o una referencia nula. Ambas variables son predefinidas en Ruby y son útiles en diferentes situaciones en el lenguaje.

7.  En JavaScript, null y undefined son dos valores que se utilizan para representar la ausencia de un valor o un valor indefinido. A pesar de que ambos valores se usan para denotar una ausencia de valor, tienen diferencias importantes en cuanto a su semántica y uso:

    - null: Es un valor primitivo que se utiliza para indicar la ausencia de cualquier objeto o valor. Se puede asignar a una variable como un valor explícito. Por ejemplo: `let variable = null;`. También se puede utilizar para inicializar una variable que se utilizará más adelante en el código: `let variable; variable = null;`. Se considera que null es un valor asignado por el programador, ya que se utiliza para indicar que se ha asignado un valor ausente de forma intencional.
    - undefined: Es un valor especial que se utiliza para indicar que una variable no tiene un valor asignado. Se considera que undefined es un valor asignado por el propio lenguaje, ya que se utiliza cuando una variable se declara sin un valor explícito o cuando se accede a una variable que no se ha inicializado. Por ejemplo:
      ```jsx
      let variable;
      console.log(variable); // Output: undefined
      ```
      En este ejemplo, la variable se declara pero no se asigna ningún valor, por lo que su valor es undefined.

    Es importante destacar que undefined es un valor primitivo y no un objeto, a diferencia de null, que es un objeto primitivo.

    En resumen, null y undefined se utilizan en JavaScript para representar valores ausentes o indefinidos, pero se diferencian en que null es un valor asignado por el programador para indicar la ausencia de valor, mientras que undefined es un valor asignado por el propio lenguaje para indicar que una variable no tiene un valor asignado.

8.  La sentencia break en C, PHP, JS y Ruby se utiliza para interrumpir la ejecución de un bucle o estructura de control.
    - C: La sentencia break se utiliza para interrumpir la ejecución de un bucle **for**, **while** o **do-while**. Debe estar dentro del cuerpo del bucle, y si se utiliza dentro de un bucle anidado, solo se interrumpe el bucle más cercano. Se utiliza comúnmente con una condición if para salir del bucle cuando se cumple una cierta condición.
    - PHP: La sentencia break se utiliza principalmente para interrumpir la ejecución de un bucle **foreach**. Al igual que en C, debe estar dentro del cuerpo del bucle y se utiliza comúnmente con una condición if para salir del bucle cuando se cumple una cierta condición.
    - JavaScript: La sentencia break se utiliza para interrumpir la ejecución de un bucle **for**, **while**, **do-while** o **switch**. Al igual que en C y PHP, debe estar dentro del cuerpo del bucle y se utiliza comúnmente con una condición if para salir del bucle cuando se cumple una cierta condición.
    - Ruby: La sentencia break se utiliza para interrumpir la ejecución de un bucle **for**, **while** o **until**. También se puede utilizar para salir de un bloque de código. En Ruby, la sentencia break puede devolver un valor, lo que la hace más versátil que en otros lenguajes. Debe estar dentro del cuerpo del bucle y se utiliza comúnmente con una condición if para salir del bucle cuando se cumple una cierta condición.
9.  La ligadura es el proceso de asociar un nombre de variable o función con su dirección de memoria correspondiente. La importancia de la ligadura en la semántica de un programa radica en que permite al compilador o intérprete conocer el tipo y la ubicación de las variables y funciones, lo que es esencial para el correcto funcionamiento del programa.

    Existen dos tipos de ligadura: la ligadura estática y la ligadura dinámica. La ligadura estática se produce en tiempo de compilación, donde los nombres de las variables y funciones se asocian con su ubicación en memoria antes de la ejecución del programa. En cambio, la ligadura dinámica se produce en tiempo de ejecución, donde los nombres se asocian con su ubicación en memoria a medida que se van necesitando durante la ejecución del programa.

    Un ejemplo de ligadura estática sería en el lenguaje C, donde la declaración de una variable debe preceder a su uso en el programa. Por ejemplo:

    ```c
    int main() {
    int x = 5;
    int y = x + 2;
    return 0;
    }
    ```

    En este caso, la variable "x" se declara antes de su uso en la expresión "y = x + 2", lo que permite al compilador asignar su dirección de memoria correspondiente en tiempo de compilación.

    Un ejemplo de ligadura dinámica sería en el lenguaje Python, donde una función puede recibir un argumento de cualquier tipo y su tipo puede cambiar durante la ejecución del programa. Por ejemplo:

    ```python
    def multiply(x, y):
    return x * y

    a = 5
    b = "hello"

    print(multiply(a, 2)) # output: 10
    print(multiply(b, 2)) # output: "hellohello"
    ```

    En este caso, la función "multiply" puede recibir argumentos de cualquier tipo y su tipo puede cambiar durante la ejecución del programa, lo que permite una mayor flexibilidad en el código.
