# Práctica 6

# Parámetros

1.  - Un **_parámetro_** es una variable que se utiliza para pasar información a una función o procedimiento. Los parámetros se ubican por lo general dentro de un paréntesis situado al lado del nombre del procedimiento o función.
    - Un **_parámetro real_** es el valor real que se le pasa a la función o parámetro cuando se la llama y que se corresponde con el parámetro formal.
    - Un **_parámetro formal_** es el nombre que se utiliza en la definición de una función o método para representar al parámetro que se espera se pase como argumento.
    - La **_ligadura posicional_** se corresponde con la posición que ocupan en la lista.
    - La **_ligadura por palabra clave o nombre_** se corresponden con el nombre por lo tanto pueden estar colocados indistintamente en la lista.
2.  El modo IN indica que el parámetro formal recibe el dato desde el real. Puede ser por valor (se “copia” el valor en el parámetro real) o por valor constante (en caso de que no se envíe o tome el parámetro real, el formal tiene un valor por default).

    El modo OUT indica que el parámetro real le envía el dato al parámetro formal. Puede ser por resultado (se devuelve el valor mediante el parámetro) o resultado de funciones (funciones)

    En el modo IN/OUT el parámetro formal recibe el dato del parámetro real y el parámetro formal le envía el dato al parámetro real. Puede ser por valor/resultado (el parámetro real obtiene el dato una vez finalizada la tarea), referencia (están ligadas al mismo espacio de memoria) o por nombre.

    ![Untitled](/img/tp6-2.png)

3.  1.  | Tipo de pasaje de parámetros                                                            | Lenguaje |
        | --------------------------------------------------------------------------------------- | -------- |
        | Por valor, referencia, valor/resultado y por nombre.                                    | ADA      |
        | Por valor y por referencia (usando punteros).                                           | C        |
        | Por referencia y por valor (clonando el objeto).                                        | Ruby     |
        | Por valor y por referencia (cuando se pasan objetos).                                   | Java     |
        | Por referencia, sin embargo los enteros y las cadenas de caracteres se pasan por valor. | Python   |
    2.  ADA es considerado más seguro en cuanto al pasaje de parámetros en las funciones debido a que ADA proporciona un sistema de tipos más riguroso y una mayor flexibilidad en la forma en que los parámetros se pasan y manipulan en las funciones. En Ada, es posible especificar el modo de pasaje de cada parámetro en la definición de la función, lo que permite controlar exactamente cómo se manejan los datos pasados a la función. Además, Ada ofrece la posibilidad de utilizar tipos abstractos y tipos protegidos, que permiten una mayor encapsulación y protección de los datos. Por otro lado, en Pascal, el pasaje de parámetros se hace principalmente por valor, y aunque también es posible pasar parámetros por referencia mediante el uso de punteros, esto puede aumentar el riesgo de errores de programación y corrupción de datos si no se manejan adecuadamente.
    3.  En ADA el manejo de los parámetros in-out depende del tipo de dato de los mismos. Para tipos simples se utiliza **`in out`**, mientras que para tipos complejos se utilizan punteros y para tipos de datos protegidos se utiliza la referencia del dato junto a **`in out`**.

4.  1.  ![Untitled](/img/tp6-4-1.png)

        | Main   | Recibe     | Dos        |
        | ------ | ---------- | ---------- |
        | PR     | PR, LE, LD | PR, LE, LD |
        | j      | x          | m          |
        | m      | y          |            |
        | i      | VR         | VR         |
        | Recibe |            |            |
        | Dos    |            |            |
        | VR     |            |            |

    2.  Pilas:

        1. Referencia:

           ![Untitled](/img/tp6-4-2.png)

        2. Valor:

           ![Untitled](/img/tp6-4-3.png)

        3. Valor resultado:

           ![Untitled](/img/tp6-4-4.png)

        4. Nombre:

           ![Untitled](/img/tp6-4-5.png)

        5. Resultado: No se puede realizar. Lo explico abajo.

    3.  Si, cuando el tipo de parámetro es resultado. Esta ejecución va a tener error puesto que cuando quiero realizar la operación `m:=m + 1 + y` el procedimiento Recibe no inicializa en ningún momento `y` por lo tanto tendrá un error.
    4.  Si se refiere a todas las pilas de ejecución: varían los valores según si es estática o dinámica en la mayoría de los casos. Si se refiere al último caso, en ambas situaciones ocurrirá error.

5.  1. `(4,6,7),(4,6,7), 2, 2`: todos por referencia
    2. `(3,5,6),(4,6,7), 2, 2`: **vec** por valor y **a** por referencia
    3. `(3,5,6),(5,5,6), 0, -1`: todos por valor
6.  - Valor entero: Se comporta exactamente igual que el pasaje por referencia. En este ejemplo se imprime 1.
      ```c
      Program main
      var i:integer;
      Procedura A(nombre a:integer)
      Begin
        a++;
      end;
      Begin
      	i=0;
      	Print(i);
      End.
      ```
    - Constante: Es equivalente al tipo por \***\*\*\*\*\***valor\***\*\*\*\*\***. El main imprimirá 5.
      ```c
      Program main
      const int i = 5;
      Procedura A(nombre a:integer)
      Begin
      	a = a + 6 * 7;
      end;
      Begin
      	A(i);
      	Print(i);
      End.
      ```
    - Elemento de un arreglo: Puede cambiar el suscripto entre las distintas referencias. En este ejemplo se imprimirá 2.
      ```c
      Program main
      var i:integer;
      Procedura A(nombre a:integer)
      var vec[1..3] of integer;
      Begin
        vec[1]=0;
      	a=a-1;
      	vec[i]=a;
      	vec[a+1]=1;
      end;
      Begin
      	i=3;
      	A(i);
      	Print(i);
      End.
      ```
    - Expresión: Se evalúa cada vez.
7.  1. Cuando es por nombre tengo que tomar SIEMPRE los valores del contexto de la variable original, de su ambiente.
       ![Untitled](/img/tp6-7.png)

    2. Creo que la dinámica es igual así que ni ganas de hacerla.

8.  Deep busca por los parámetros de la cadena estática y shallow por dinámica.

    ![Untitled](/img/tp6%20-%208%20-%20S.png)

    ![Untitled](/img/tp6%20-%208%20-%20D.png)

9.  1. Si se pasa por `nombre` los valores impresos serían: `[3,2,0,1,1]`. En este tipo de pasaje de parámetros, el parámetro formal es sustituido textualmente por el parámetro real, se hace siempre alusión al parámetro real y todo su contexto.

       Si se pasa por `referencia` los valores serían: `[1,1,3,1,1]`. En este tipo de pasaje de parámetros, se pasa la referencia o dirección de memoria de un objeto o variable en lugar de su valor. Los cambios realizados en la función a los parámetros pasados por referencia afectarán el objeto o variable original fuera de la función.

       Si se pasa por `valor resultado` los valores serían: `[1,1,4,1,1]`. En este tipo de pasaje de parámetros, se pasa el valor de un parámetro a la función y la función devuelve un valor resultante al finalizar. Los cambios realizados en la función no afectarán el valor original fuera de la función, a menos que se asigne explícitamente el valor de retorno.

    2. Si se agrega la declaración de `x` dentro de Uno los valores serían:
       - Por nombre: `[1,1,3,1,1]`.
       - Por referencia: `[1,1,3,1,1]`.
       - Por valor resultado: `[1,1,4,1,1]`.

10. 1. En este punto consideré si era por link estático y por link dinámico, pero tengo que corregirlo porque capaz está mal pensado.

       | Variable                    | Valores LE | Valores LD |
       | --------------------------- | ---------- | ---------- |
       | x (Uno)                     | 8, 19      | 8          |
       | x (Tres, apunta a x de Uno) | 8, 13, 19  | 8, 13, 24  |
       | Dos                         | 9          | 14         |

    2. 😴🥱
