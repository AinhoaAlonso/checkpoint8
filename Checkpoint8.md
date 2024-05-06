# ¿Qué tipo de bucles hay en JS?
En ocasiones nos interesa que determinados bloques de código se ejecuten varias veces mientras se cumpla una condición. 
Son estructuras que nos van a permitir no repetir código. En programación, un bucle es un proceso en el se toma una colección de datos y luego se revisa iterativamente cada uno de los elementos.

Antes de comenzar a aprender como funcionan los diferentes tipos de bucles que existen, es necesario conocer algunos conceptos básicos relacionados con los bucles.

![](https://lenguajejs.com/fundamentos/estructuras-de-control/flujo-de-ejecucion/bucles-flujo-repeticion.png)
      
##### Condición
En los bucles se va a evaluar una condición para saber si se debe seguir repetiendo el bucle o se debe finalizar. Las condiciones típicamente devuelven **true** (verdadero) o **false** (falso) al ser evaluados. El bucle continuará ejecutándose hasta que la condición devuelva  **false**.
##### Iteración
Otro concepto que usaremos mucho dentro de un bucle es el concepto de Iteración. Esto se refiere a cada una de las repeticiones de un bucle. En programación se suele empezar a contar en 0, por lo que esa es la primera iteración. Si el bucle va desde 0 a 3, hay 4 iteraciones.
##### Contador
Muchas veces, los bucles que creamos incorporan un contador, que no es más que algo que irá guardando un número para contar el número de repeticiones realizadas, y así finalizar cuando se llegue a otro número concreto. Dicho contador hay que inicializarlo (crearlo y darle un valor) antes de comenzar el bucle.
##### Incremento
Al igual que tenemos un contador en un bucle, también debemos tener una parte donde hagamos un incremento (o un decremento) de dicho contador. Si no lo tuvieramos, el contador no cambiaría y la condición siempre sería veradera, por lo que sería imposible salir del bucle.

A continuación vamos a ver varios tipos de bucles:

- #### Bucles for: 
    - __Bucle for__: Un ciclo for se repite hasta que una condición especificada se evalúe como false. 
        ###### Sintaxis: 
        ```
        for ([expresiónInicial]; [expresiónCondicional]; [expresiónDeActualización]){
            instrucción
        }
        ```
        Vamos a ver un ejemplo de este tipo de bucles:
        ```
        let members = [
            'Ainhoa',
            'Julen',
            'Alaia',
            'Adei'
        ]
        for (let i= 0 ; i < members.length; i++){
            console.log (members[i]);  //"Ainhoa" "Julen" "Alaia" "Adei"
        }
        ```
        **Ejemplo:** en este ejemplo el bucle itera sobre el array members, tenemos **i = 0** como variable de control, y la condición para que se cumpla el es que esa variable sea menor que la logitud del array, cada vuelta le sumamos 1 a la variable. Nos va imprimiendo en la consola el elemento que pertenece al indice que corresponda el valor de la variable de control. Cuando ya no se cumple la condición se se para el bucle.
    
    - __Bucle for...in:__ itera una variable especificada sobre todas las propiedades enumerables de un objeto, en orden arbitrario. Para cada propiedad distinta, se pueden ejecutar sentencias.
        ###### Sintaxis:
            for (variable in objeto){
                instrucción
            }
        Vamos a ver un ejemplo de este tipo de bucles:
        ```
        let members = [
            'Ainhoa',
            'Julen',
            'Alaia',
            'Adei'
        ]
        for (member in members){
            console.log(member); // Muestra el indice de cada elemento "0" "1" "2" "3"
            console.log(members[member]); // "Ainhoa" "Julen" "Alaia" "Adei"
        }
        ```
        **Ejemplo:** este bucle se ejecutará tantas veces como el número de elementos que se encuentren dentro de la colección.
    
    - __Bucle for...of:__ crea un bucle que se repite sobre objetos iterables, invocando un bucle de iteración personalizado con declaraciones que se ejecutarán para el valor de cada distinta propiedad.
    Mientras que ***for...in*** itera sobre los nombres de propiedad, ***for...of*** itera sobre los valores de propiedad:
        ```
        let members = [
            'Ainhoa',
            'Julen',
            'Alaia',
            'Adei'
        ]
        for (member of members){
            console.log(member); // "Ainhoa" "Julen" "Alaia" "Adei"
        }
        ```
    - __Bucle forEach:__ se utiliza para iterar sobre los elementos de un array y ejecutar una función de retorno de llamada (callback) una vez por cada elemento.
        ###### Sintaxis:
            array.forEach(function(element){
                instrucción
            });
        Vamos a ver un ejemplo:
        ```
        let members = [
            'Ainhoa',
            'Julen',
            'Alaia',
            'Adei'
        ]
        members.forEach(function(element{
            console.log(element); //"Ainhoa" "Julen" "Alaia" "Adei"
        })
        ```
- #### Bucles while
    - __Bucle while:__ el bloque de código dentro del while se ejecutará mientras se cumpla la condición, se evalúe como **true**.
    En este tipo de bucles la variable de control siempre se declara fuera. Si la condición devuelve true, se ejecuta la expresión y la condición se prueba de nuevo. Si la condición devuelve false, la ejecución se detiene.
    **NOTA:** hay que asegurarse de que la condición en un bucle eventualmente se convierta en false; de lo contrario, el bucle nunca terminará (bucle infinito).
        ```
        let members = [
            'Ainhoa',
            'Julen',
            'Alaia',
            'Adei'
        ]
        let i = 0;
        while (i<members.length){
            console.log(members[i]);  // "Ainhoa" "Julen" "Alaia" "Adei"
            i++;   //Importante aumentar el contador para que la condición deje de cumplirse 
                    y no se convierta en un bucle infinito.
        }
        ```
        **Ejemplo:** primera vuelta: entra en el while porque cumple la condición, **i=0 y members.length(4)**, mostramos el elemento al que corresponde el indice de **i ("Ainhoa")** subimos el contador.
        Segunda vuelta: **i=1 y members.length(4)**, entra en el bucle, mostramos el elemento al que corresponde el indice de **i ("Julen")** subimos el contador.
        Tercera vuelta: **i=2 y members.length(4)**, entra en el bucle, mostramos el elemento al que corresponde el indice de **i ("Alaia")** subimos el contador.
        Cuarta vuelta: **i=3 y members.length(4)**, entra en el bucle, mostramos el elemento al que corresponde el indice de **i ("Adei")** subimos el contador.
        Quinta vuelta: **i=4 y members.length(4)**, no cumple la condición, se para el bucle.

    - __Bucle do/while__: con el bucle do/while nos aseguramos que el bucle siempre se ejecute al menos una vez, primero entra en el **do** y ejecuta el código y luego comprueba la condición del **while.**

        ```
        let members = [
            'Ainhoa',
            'Julen',
            'Alaia',
            'Adei'
        ]
        let i=0;
        do {
            console.log(members[i]);  // "Ainhoa" "Julen" "Alaia" "Adei"
            i++;
        } while (i<members.length);
        ```
##### Para ampliar conocimientos
Dejo aqui enlaces de interés para que puedas ampliar la información sobre los bucles y como utilizarlos.
<https://es.javascript.info/while-for>
<https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Statements/for...in>
<https://developer.mozilla.org/es/docs/Web/JavaScript/Guide/Loops_and_iteration#declaraci%C3%B3n_while>

# ¿Cuáles son las diferencias entre const, let y var?
Antes de la llegada de ES6, en JavaScript, solíamos utilizar la palabra clave **var** para declarar variables. Sin embargo, esto resultaba problemático por varias razones. Con la introducción de ES6, surgieron nuevas y más eficientes formas de declaración de variables: **let** y **const**.

Aquí están las diferencias entre estos tres:
- **VAR:** 
    - Var tiene un ámbito de aplicación que puede ser global o local. Las variables var declaradas fuera de una función tienen un ámbito global, lo que significa que están disponibles en todo el programa. Por otro lado, las variables declaradas dentro de una función tienen un ámbito local, y solo están disponibles dentro de esa función. 
        ```
        Ejemplo:
        var saludar = "hey, hola"; //Ámbito global
        function nuevaFuncion() {
            var hola = "hola";  //Ámbito local
        }
        console.log(hola); // error: hola is not defined 
            no podemos acceder a hola porque no está disponible fuera de la función.
        ```
    - Las variables con var se pueden volver a declarar y modificar, esto significa que podemos hacer esto dentro del mismo ámbito y no obtendremos un error, eso es un problema porque podemos modificar una variable que se utilice en otras partes del código, lo que puede llevar a errores difíciles de rastrear.
        ```
        var saludar = "hey, hola";
        var saludar = "dice Hola tambien";
        ```
    - Además, var se ve afectado por el hoisting, lo que significa que las declaraciones de variables var son elevadas al inicio de su ámbito, lo que puede resultar en comportamientos inesperados.
        ```
        Si hacemos esto:
            console.log (saludar);
            var saludar = "dice hola"
        Se interpreta así:
            var saludar;
            console.log(saludar); // saludar is undefined
            saludar = "dice hola"
        ```
- **LET:**
    - Let tiene un ámbito de bloque, lo que significa que una variable let declarada dentro de un bloque (por ejemplo, un bucle for o un bloque if, delimitado por {}) solo estará disponible dentro de ese bloque.
        ```
        let saludar = "dice Hola";
        let tiempos = 4;

        if (tiempos > 3) {
            let hola = "dice Hola tambien";
            console.log(hola);// "dice Hola tambien"
        }
        console.log(hola) // hola is not defined
        
        El uso de "hola" fuera de su bloque devuelve un error. Las variables let tienen un alcance de bloque.
        ```
    - Let puede modificarse pero no volver a declararse. Al igual que var,  una variable declarada con let puede ser actualizada dentro de su ámbito. A diferencia de var, una variable let no puede ser re-declarada dentro de su ámbito.
        ```
        Así que mientras esto funciona:
            let saludar = "dice Hola";
            saludar = "dice Hola tambien";
        Esto devolverá un error:
            let saludar = "dice Hola";
            let saludar = "dice Hola tambien"; 
                            // error: Identifier 'saludar' has already been declared
        ```
        Sin embargo, si la misma variable se define en diferentes ámbitos, no habrá ningún error:
        ```
        let saludar = "dice Hola";
        if (true) {
            let saludar = "dice Hola tambien";
            console.log(saludar); // "dice Hola tambien"
        }
        console.log(saludar); // "dice Hola"
        
        Esto se debe a que ambas instancias son tratadas como variables diferentes, ya que tienen ámbitos diferentes.
        ```
        Este hecho hace que let sea una mejor opción que var. Cuando se utiliza let, no hay que preocuparse de sí se ha utilizado un nombre para una variable antes, puesto que una variable solo existe dentro de su ámbito.
        Además, como una variable no puede ser declarada más de una vez dentro de un ámbito, entonces el problema discutido anteriormente que ocurre con var no sucede.

    - Hoisting de let: al igual que  var, las declaraciones let se elevan a la parte superior. A diferencia de var que se inicializa como undefined, la palabra clave let no se inicializa. Sí que si intentas usar una variable let antes de declararla, obtendrás un Reference Error.

- **CONST:**
    - Las declaraciones const tienen un ámbito de bloque: Al igual que las declaraciones let, solamente se puede acceder a las declaraciones const dentro del bloque en el que fueron declaradas.
    - Las variables declaradas con const mantienen valores constantes, no pueden modificarse ni volver a declararse, es una de las maneras favoritas de declarar variables por defecto, NO queremos tener siempre la capacidad de redefinir nuestras variables.
        ```
        No podemos hacer esto:
            const saludar = "dice Hola";
            saludar = "dice Hola tambien";// error: Assignment to constant variable. 
        Ni esto:
            const saludar = "dice Hola";
            const saludar = "dice Hola tambien";  //error: Identifier 'saludar' has         already been declared
        ```
        Por lo tanto, toda declaración const, debe ser inicializada en el momento de la declaración.

        Este comportamiento es algo diferente cuando se trata de objetos declarados con const. Mientras que un objeto const no se puede actualizar, las propiedades de este objeto sí se pueden actualizar.
        ```
        const saludar = {
            mensaje: "dice Hola",
            tiempos: 4
        }
        Mientras que no podemos hacer esto:
            saludar = {
                palabras: "Hola",
                numero: "cinco"
            } // error:  Assignment to constant variable.
        Podemos hacer esto:
            saludar.mensaje = "dice Hola tambien";
        
        Esto actualizará el valor de saludar.mensaje sin devolver errores.

    - Hoisting de const: al igual que let, const las declaraciones const se elevan a la parte superior, pero no se inicializan.

En resumen, mientras que var tiene un ámbito de función o global y permite la redeclaración y reasignación, let y const tienen un ámbito de bloque y no permiten la redeclaración. Además, const no permite la reasignación después de la inicialización. Estas diferencias hacen que let y const sean opciones más seguras y predecibles para la declaración de variables en comparación con var.


![](https://static.platzi.com/media/user_upload/const%20let%20var-799816fd-4671-4563-a8dc-a638dfe8c547.jpg)

# ¿Qué es una función de flecha?
Es una alternativa compacta a una expresión de función tradicional, pero es limitada y no se puede utilizar en todas las situaciones.
Es importante notar que las funciones flecha son anónimas, lo que significa que no tienen nombre.
Este anonimato crea algunos problemas:

- Más difíciles de depurar: cuando obtengas un error, no serás capaz de rastrear el nombre de la función o el número de línea exacto donde ocurrió.

- Sin autorreferencia:si tu función necesita tener autorreferencia en algún punto (por ejemplo, recursión, controlador de evento que necesita desvincularse), no funcionará.

![](https://edteam-media.s3.amazonaws.com/blogs/original/d7917c74-9eb9-495e-bd1f-2f9a2a6a3895.png)

- ##### Sintaxis básica
    - Con un parámetro no necesita paréntesis ni el return.
        - let func = param => expression;
    - Con varios parámetros el paréntesis es obligatorio y no necesita el return porque va ímplicito en la función flecha.
        - let func = (arg1, arg2, ..., argN) => expression;
        Veamos un ejemplo concreto:
            ```
            let sum = (a, b) => a + b;
        
            /* Esta función de flecha es una forma más corta de:
            let sum = function(a, b) {
                return a + b;
            };*/
            alert( sum(1, 2) ); // 3
    
            Como puedes ver, (a, b) => a + b significa una función que acepta dos argumentos llamados a y b. Tras la ejecución, evalúa la expresión a + b y devuelve el resultado.
            ```
    - Si la función no tiene argumentos, se utilizan paréntesis vacíos
        - let func = () => expression;
    - Con un array
        ````
        // Función tradicional: un array y que nos devuelva cuáles son los pares
        
        const array1 = [1,2,3,4,5,6,7,8,9,10];
        const pares = array1.filter(function(numero){
            return numero % 2 == 0;
        });
        console.log(pares);  // [object Array] (5) [2,4,6,8,10]
        
        // Función flecha
        const arrayPares = array1.filter((numero) =>{
            return numero % 2 == 0;
        });
        //Función flecha más reducida, una sola línea.
        const arrayPares = array1.filter((numero) => numero % 2 == 0);
        
        console.log(arrayPares);  // [object Array] (5) [2,4,6,8,10]
        
        ````
- 
    ##### Sintaxis Avanzada
    
    A veces necesitamos una función más compleja, con múltiples expresiones o sentencias. En ese caso debemos encerrarlos entre llaves **{}**. La diferencia principal es que las llaves necesitan usar un **return** para devolver un valor.
 
    ```
    let sum = (a, b) => {  // la llave abre una función multilínea
        let result = a + b;
        return result; // si usamos llaves, entonces necesitamos un "return" explícito
    };
    alert( sum(1, 2) ); // 3
    ```
#### Errores más comunes
- Uso del **return**: tenemos que acordarnos que siempre que hagamos una función flecha con **{}**, es necesario poner el return, si la hacemos en una sola línea y no tiene las {} no es necesario ponerlo.
- A la hora de devolver un objeto de forma literal en una sola línea hay que poner los **()**, esto se ve mejor con un ejemplo:
    ````
    // Función flecha
    const objetoLiteral = () => {
        return {foo:'a'};
    }
    console.log(objetoLiteral); // {foo:'a'}

    // Función flecha en una línea, si no ponemos los '()', lo trata como una etiqueta y no como una propiedad, nos devuelve 'undefined'.
    
    objetoLiteral2 = () => ({foo2:'b'});
    console.log(objetoLiteral2); // {foo2:'b'}
    ````
#### Funciones flecha y el "this"

Antes de explicar el **this** en las funciones flecha vamos a explicar un poco la palabra clave **this** porque es una de las características de JavaScript qué más confusión genera.

La palabra clave **this** siempre se refiere a un objeto, lo que pasa es que el objeto al que se refiere variará dependiendo de cómo y dónde se llame this. This no es una variable, es una palabra clave por lo que su valor no se puede cambiar ni reasignar.
***This*** es una referencia que se crea cuando una función es invocada, no declarada. El valor de esa referencia depende al 100% del lugar en la que esa invocación se realice, llamado call-site. 
Ese lugar de llamada es la invocación en sí a la función.
- **this en el contexto global**
Fuera de cualquier función, es decir, en el ámbito global, ***this siempre hace referencia al objeto global window***:
    ````
    // Estamos en el contexto de ejecución global
    console.log(this === window); // true
    ````
- **this en invocaciones de funciones**
Dentro de una función, el valor de this está determinado por el lugar en el que esa función es invocada.
En una sencilla función declarada, ***this hace referencia al objeto global window***:
    ````
    function funcion() {
        console.log(this);
    }
    funcion(); // window
    ````
- **this en invocaciones de construcción**
A través del operador new se crea un nuevo objeto, se asigna su prototipo a la función constructora y lo que es más importante: dentro de la función que hace de constructor, el valor de ***this hace referencia a ese nuevo objeto*** que se está creando.
    ````
    function Gato(raza, color) {
        this.raza = raza;
        this.color = color;
        console.log(this);  // Gato {raza: "europeo", color: "negro"}
    }
    const guizmo = new Gato('europeo', 'negro');
    ````
- **this en llamadas a métodos**
Cuando una función es llamada como un método de un objeto, su contexto de ***this se asocia al objeto que contiene el método***.
    ````
    const rouco = {
        nombre: 'Rouco',
        especie: 'gato',
        saludar() {
            console.log('Miauuuuu (Hola me llamo ${this.nombre})');
            console.log(this === rouco); // true
        }
    };
    rouco.saludar(); // Miauuuuu (Hola me llamo Rouco) 
    ````
    Sin embargo,  es relativamente sencillo perder el contexto de this si por ejemplo guardamos el método en una función declarada para ejecutarla como tal y no como un método (con su referencia al objeto):
    ````
    const rouco = {
        nombre: 'Rouco',
        especie: 'gato',
        saludar() {
            console.log('Miauuuuu (Hola me llamo ${this.nombre})');
            console.log(this === rouco); // false
    };
    let saludar = rouco.saludar;
    saludar(); // <— Este es el "call-site"  // Miauuuuu (Hola me llamo undefined) 
    ````
    Fíjate que aunque nos estamos refiriendo al método de un objeto, la llamada (call-site) ocurre bajo la forma de una función declarada en el ámbito global.
    
Uno de los aspectos más importantes de las funciones flecha es la utilización de la palabra clave **'this'**.
Creo que la mejor forma de entenderla es con ejemplos y explicando esos ejemplos.

### Ejemplo1
Muestra cómo se comportan las funciones de temporización (setTimeout) dentro de objetos y cómo el contexto (this) puede cambiar en diferentes situaciones. Lo vamos a ir desglosando para entender a que hace referencia el **this**.

**PRIMERO:** tenemos un objeto **obj1** con una **propiedad value** inicializada a 10 y un **método getValue**. El método getValue, **this se refiere al objeto obj(10)**.
También tenemos un **obj2** con una **propiedad value** inicializada a 15 y un **método getValue2**. En este caso, en getValue2, **this se refiere al contexto global (undefined)** o al objeto que contiene obj2, dependiendo del entorno. 
>**IMPORTANTE** 
En JavaScript, las funciones de flecha (() => {}) tienen un comportamiento diferente con respecto a **this** en comparación con las funciones regulares (function() {}). Las funciones de flecha no tienen su propio this; en su lugar, utilizan el this del contexto circundante en el que fueron definidas.En este caso, está dentro de un objeto, no se creó dentro de una función.
````
const obj  ={
  value: 10,
  getValue : function(){
    console.log(this.value); // 10
  }
};
obj.getValue();

const obj2 = {
  value:15,
  getValue2: (() =>{
    console.log(this.value); // Undefined
  })
};
obj2.getValue2();
````
**SEGUNDO:** vamos a agregar una función de temporizador al **obj1** que nos imprime el value despues de 1s.  Dentro de **getValue**, dentro de la función **setTimeout**, hay un **problema** aquí: dentro de la función de temporización, el contexto de **this no se refiere al objeto obj, sino al ámbito global o a undefined**, dependiendo del modo de uso de JavaScript.
Se está ejecutando una función anónima tradicional (no se asigna a ninguna variable), **this no se refiere al objeto obj, sino al contexto de ejecución de setTimeout, que es el objeto global (en el navegador, sería window).**
````
const obj  ={
  value: 10,
  getValue : function(){
    console.log(this.value); //10
    setTimeout(function() {
      console.log(this.value);// undefined
    }, 1000);
  }
};
obj.getValue();
````
Para arreglar esto y que apunte al objeto es cuando utilizamos las funciones flecha, ya que las **funciones de flecha mantienen el contexto de this del entorno en el que se definen**. Está creada dentro de un método o función.
````
const obj  ={
  value: 10,
  getValue : function(){
    console.log(this.value); //10
    setTimeout(() => {
      console.log(this.value);// 10
    }, 1000);
  }
};
obj.getValue();
````
##### Para ampliar conocimientos
las funciones flecha y la palabra clave 'this' son conceptos un poco confusos de entender, os dejo algunas referencias que revisar.
https://www.youtube.com/watch?v=m9PsxIAPFzM
https://www.youtube.com/watch?v=qvAQOwIg46Y
https://wmedia.es/aprender-usar-this-javascript/#:~:text=%C2%BFQue%20es%20this%3F,en%20s%C3%AD%20a%20la%20funci%C3%B3n.

# ¿Qué es la deconstrucción de variables?
También conocida como "destructuring" en inglés, es una característica de JavaScript que permite descomponer un objeto o un array en un conjunto más pequeño de variables, lo que facilita el acceso a sus elementos.
La mejor forma de entender la desestructuración es verlo con ejemplos.
##### Ejemplo de objeto
Si queremos obtener el valor de las propiedades **name** y **age** del objeto **user**, podemos hacer esto:
```
const user = { 
    'name': 'Alex',
    'address': '15th Park Avenue',
    'age': 43
}
let name = user.name;
let age = user.age;
console.log(name, age);
```
Tenemos que mencionar explícitamente la propiedad **name** y **age** con el objeto **user** en notación de punto (.), luego declarar las variables en consecuencia y asignarlas.
Podemos simplificar este proceso utilizando la deconstrucción de objetos.
```
const user = { 
    'name': 'Alex',
    'address': '15th Park Avenue',
    'age': 43
}
// La expresión para extraer el valor de name y de age de la propiedad mediante la desestructuración de objetos.
const { name, age } = user; 
console.log(name); // Alex 43
```
##### Ejemplo de array
Si queremos deconstruir un array.
```
const colores = ['rojo', 'verde', 'azul'];

// Deconstrucción de array
const [color1, color2, color3] = colores;

console.log(color1); // rojo
console.log(color2); // verde
console.log(color3); // azul
```
##### Agregar una nueva variable y valor predeterminado
Podemos agregar una nueva variable mientras desestructuramos y agregarle un valor predeterminado.     
```
const user = { 
    'name': 'Alex',
    'address': '15th Park Avenue',
    'age': 43
}
const { name, age, salary=123455 } = user;
console.log(name, age, salary); // Alex 43 123455

En el siguiente ejemplo, la variable salary no existe en el objeto user. Pero podemos agregarla en la expresión desestructuradora y agregarle un valor predeterminado.
```
La flexibilidad de agregar una variable con un valor predeterminado tiene una ventaja considerable. El valor predeterminado de esta nueva variable no necesariamente será siempre un valor constante. Podemos calcular su valor a partir de otros valores de propiedad desestructurados.
Tomemos un objeto **user** con dos propiedades **first_name** y **last_name**. Ahora podemos calcular el valor de un inexistente **full_name** usando estas dos propiedades.
```
const user = { 
    'first_name': 'Alex',
    'last_name': 'Brandos',
}
const { first_name, last_name, full_name=`${first_name} ${last_name}` } = user;
console.log(full_name); // Alex Brandos
```
##### Intercambio de valores de variables
En este ejemplo tenemos un juego con 2 jugadores y queremos intercambiar sus roles.
```
let playerOne = 'Ainhoa';
let playerTwo = 'Julen';

// Son necesarios los [], sin ellos no funciona el intercambio.

[playerOne, playerTwo] =[playerTwo, playerOne];
console.log('Player One : ${playerOne}, Player Two : ${playerTwo}');
// "Player One: Julen" "Player Two: Ainhoa"
```

##### Desestructuración de objetos anidados
Tenemos el siguiente objeto **user**.
```
const user = { 
    'name': 'Alex',
    'address': '15th Park Avenue',
    'age': 43,
    'department':{
        'name': 'Sales',
        'Shift': 'Morning',
        'address': {
            'city': 'Bangalore',
            'street': '7th Residency Rd',
            'zip': 560001
        }
    }
}
```
¿Cómo extraemos el valor de la propiedad **department**? 
```
const { department } = user;
```
**Resultado**
````
console.log(department);
````
![](https://www.freecodecamp.org/news/content/images/2021/02/image-30.png)

¿Cómo extraemos el valor de la propiedad **address** del **department**?. Vamos a aplicar los mismos principios de desestructuración de objetos.
```
const { department: { address } } = user;
```
**Resultado**
````
console.log(address);
````
![](https://www.freecodecamp.org/news/content/images/2021/02/image-31.png)
En este caso, **department** es la clave en la que nos centramos y desestructuramos el valor **address** a partir de ella. Observe {} alrededor de las teclas que desea desestructurar.

¿Cómo extraemos el valor de **city** de **address** de **departament**?. Seguimos utilizando el mismo principio.
````
const { department: { address: { city } } } = user; 
````
**Resultado**
````
console.log(city); //"Bangalore"
````
> La regla general es comenzar con el nivel superior y descender en la jerarquía hasta alcanzar el valor que desea extraer.

##### Pasar objetos como argumentos de función aprovechando la desestructuración
Vamos a ver como podemos combinar objetos y funciones, y hacer que la desestructuración los conecte por nosotros.

````
const user = { 
    'first_name': 'Alex',
    'last_name': 'Brandos',
}
const renderUser = ({ first_name, last_name}) => {
    console.log(`${first_name} ${last_name}`);
}

// Pasamos el objeto completo en lugar de pasar "user.first_name" o "user.last_name".
renderUser(user); // Alex Brandos
````

# ¿Qué hace el operador de extensión en JS?
El **Spread operator**, también conocido como los tres puntos (…), es una característica introducida en ES6 que se utiliza para expandir una expresión iterable (arrays, objetos) en múltiples elementos.
Vamos a ver un ejemplo de como funciona.
**Ejemplo:** tenemos un array que al imprimirlo se ve así.
````
let array = [1,2,3,4,5,6];
console.log(array);  // [object Array] (6)
                        [1,2,3,4,5,6]
````
Si aplicamos el Spread Operador al imprimir, obtendremos cada valor por separado.
````
let array = [1,2,3,4,5,6];
console.log(...array);   // 1 2 3 4 5 6
````

Puede utilizarse en varias situaciones:
- **Combinar arrays**
    Hay varias formas de combinar:
    ````
    let array1 = [1,2,3,4,5];
    let array2 = [6,7,8,9,10];
    
    array1.push(...array2);
    console.log(array1); //[1,2,3,4,5,6,7,8,9,10]

    **CUIDADO** si hago esto:
    array1.push(array2); // [1,2,3,4,5,[6,7,8,9,10]] Los ha unido pero no los ha combinado, por eso hay que utilizar el spread operator.
    ````
    ````
    let array1 = [1,2,3,4,5];
    let array2 = [6,7,8,9,10];
    
    const newArray = [...array1, ...array2];
    console.log(newArray); // [1,2,3,4,5,6,7,8,9,10]
    ````
    Aquí lo estamos descomponiendo y combinando.
    ````
    let array2 = [6,7,8,9,10];
    let array1 = [1,2,3,4,5,...array2];
    console.log(array1); // [1,2,3,4,5,6,7,8,9,10]
    ````
- **Copiar arrays:** la convención común es NO cambiar el array inicial, sino que crearíamos uno nuevo dónde copiaríamos el array inicial.
    ````
    const array = [1,2,3,4,5,6,7,8,9,10];
    const arrayCopiado = [...array];
    arrayCopiado.push(11);
    console.log(arrayCopiado); // [1,2,3,4,5,6,7,8,9,10,11]
    console.log(array); // [1,2,3,4,5,6,7,8,9,10] No modifica el original
    ````
- **Para pasar argumentos a funciones**
    - Queremos que nos muestre el número más alto una colección.
        Si nosotros utilizamo el método Math.max y le pasamos varios argumentos.
        ````
        console.log(Math.max(1,3,5,10,15,2)); // 15 Lo hace bien
        ````
        Si hacemos lo mismo pero dentro de un array.
        ````
        const array = [1,3,5,10,15,2];
        console.log(Math.max(array)); // NaN
        
        Lo que ocurre en este caso es que JS solo vé que le has pasado un argumento y ni siquiera es un número, No sabe lo que hacer con él.
        ````
        Lo arreglamos añadiendo el spread operator (...), ahora JS toma todo lo que hay dentro de la colección, lo expande y lo convierte en su propio conjunto de elementos.
         ````
        const array = [1,3,5,10,15,2];
        console.log(Math.max(...array)); // 15
        ````
    - Pasamos múltiples argumentos a una función que espera una cantidad variable de argumentos.
        ````
        const valores = [1, 2, 3];
            function suma(a, b, c) {
            return a + b + c;
        }
        console.log(suma(...valores)); // 6
        ````
- **También funciona con objetos**
    ````
    const datos = {
        nombre: "Edgar",
        edad:18,
        sexo: "M"
    }
    const direc = {
        pais: "Colombia",
        nacionalidad: "Peruana"
    }
    const persona = {...datos, ...direc};
    console.log(persona);      // [object Object] {
                                "nombre": "Edgar",
                                "edad": 18,
                                "sexo": "M",
                                "pais": "Colombia",
                                "nacionalidad": "Peruana"
                                }
    ````
    
##### Para ampliar conocimientos
Te dejo aquí un enlace a un vídeo que te puede resultar de utilidad para entender mejor el spread operator.
<https://www.youtube.com/watch?v=_5V6siSlP2k>
# ¿Qué es la programación orientada a objetos?
Las versiones anterios de JS no tenían los componentes de clases y creación de instancias de programación orientada a objetos (POO).
A partir de ES6, JavaScript, a pesar de ser un lenguaje más conocido por su estilo de programación orientado a eventos y funciones de primera clase, también se puede utilizar la POO.
JavaScript permite la creación de clases y objetos utilizando la sintaxis de prototipos o utilizando la sintaxis de la palabra clave **class**. 
- **Paso 1:** una **class** es simplemente una lista de definiciones que dicen exactamente como debe comportarse la clase, se enumerarán los atributos para que pueda describir lo que supone que hace la clase y el comportamiento que va a tener.
    - Imagina una clase de usuario , cada vez que un usuario ingresa al sitio y se registra, el programa va a mirar en la clase de usuario y va a ver como debe comportarse ese usuario.
- **Paso 2:** creación de instancias.
    - Estamos tomando la clase y estamos creando un objeto del mundo real con él, va a ser el objeto con el que vamos a trabajar en realidad.

En **resumen** una clase por si sola NO hace nada, simplemente nos dá un conjunto de reglas y pautas para construir objetos, y la forma de hacerlo es con la CREACIÓN DE INSTANCIAS, una palabra clave muy importante para recordar cuando se trata de este proceso.
    
Vamos a ver esto con ejemplos que es como mejor se entiende:

![](https://lenguajejs.com/javascript/oop/clases/clases-objetos.png)
- En primer lugar tenemos la **clase**. La clase es el concepto abstracto de un objeto: Animal, Vehículo, Forma
    - En la 1ª clase **Animal** tenemos dos **objetos:** pato y ratón. Tanto pato como ratón tienen las características que estarán definidas en la clase Animal: color, sonido que emiten, nombre, etc...
    - En la 2ª clase **Vehículo** tenemos dos **objetos:** seat y opel. Cada uno tendrá las características de su clase: color del vehículo, número de ruedas, marca, modelo, etc..
    - En la 3ª clase **Forma** tenemos dos **objetos:** cuadrado y c2. Tendrán sus propias características, como por ejemplo el tamaño de sus lados.
- Al siguiente paso se le llama **instanciar una clase**, crear un objeto o crear una instancia a la acción de crear un nuevo objeto basado en una clase particular. Esta acción la realizamos a través de la **palabra clave new**, seguida del nombre de la clase.
    ````
    // Declaración de una clase (de momento, vacía)
    class Animal {}

    // Crear (instanciar) un objeto basada en una clase
    const pato = new Animal();
    ````
    Estamos creando una variable ("pato" el nombre elegido debería hacer referencia a la información que va a contener dicha clase) donde hacemos un new Animal(). Objeto pato que es de tipo Animal, y que contendrá todas las características definidas dentro de la clase Animal.

Una clase tiene diferentes características que la forman, se dividen en dos grupos:
- Las ***propiedades***: variables dentro de clases
- Los ***métodos***: funciones dentro de clases

````
class Animal {
  // Propiedades
    constructor ({ name, type}){
        this.name = name;
        this.type = type;
    }
  // Métodos
    hablar(frase) {
        return `${this.name} dice ${frase}.`;
    }
}
let gato = new Animal ({name:"Garfield",type:"cat"});
console.log(gato.hablar("odio los lunes"));  // "Garfield dice odio los lunes."
````
Vamos a entender lo que hacemos en este **ejemplo**:
1º Definimos la **clase Animal**.
2º Agregamos un **constructor** que es un método especial que se llama automáticamente cuando se crea una nueva instancia (objeto) de la clase. En este caso, el constructor toma un objeto como argumento (usando la desestructuración de objetos) que tiene las propiedades name y type, y asigna esas propiedades a la instancia actual (this). Esto significa que cuando creas un nuevo objeto Animal, debes proporcionar un objeto con las propiedades name y type.
3º Definimos un método en la **clase Animal**. Este método toma un parámetro frase y devuelve una cadena que contiene el nombre del animal (this.name) seguido de la palabra "dice" y la frase proporcionada como argumento.
4º Creamos una nueva **instancia(objeto)** de la **clase Animal** con el nombre **gato**. Se pasa un objeto con las propiedades name y type ({ name: "Garfield", type: "cat" }) al constructor de Animal.
5º Llamamos al método **hablar()** en el objeto gato creado anteriormente, pasando la frase "odio los lunes" como argumento. 

La programación orientada a objetos puede ser un poco complicada de entender, aconsejo ver este vídeo para comprender mejor determinados conceptos.
https://www.youtube.com/watch?v=N_t1A39IB_8
# ¿Qué es una promesa en JS?
Una promesa es un objeto que sirve para reservar el resultado de un operación futura, es algo que, en principio pensamos que se cumplirá, pero en el futuro pueden ocurrir varias cosas:
- La promesa se cumple (promesa resuelta/resolve)
- La promesa no se cumple (promesa rechazada/reject)
- La promesa se queda en un estado incierto indefinidamente (promesa pendiente)

![](https://lenguajejs.com/javascript/asincronia/promesas/promises.png)
Este resultado llega a través de una operación asíncrona, que son operaciones no instantáneas, que requieren de un tiempo, aunque sea pequeño, para ejecutarse y finalizar. Gracias a su naturaleza asíncrona, se puede elegir que elementos se cargarán de inmediato y cuáles pueden tardar un poco más.
Una de las formas más comunes de utilizar promesas es para comunicarnos con API's externas, con bases de datos,..

Las promesas cumplen varias funciones clave:
- **Manejo del flujo asíncrono óptimo**
Te permiten escribir un código más limpio y comprensible al evitar el anidamiento excesivo de callbacks. En lugar de anidar múltiples callbacks, puedes encadenar métodos **.then()** de manera más legible.
- **Gestión de errores**
Brindan un mecanismo más efectivo para manejar errores en operaciones asíncronas. Puedes usar el método **.catch()** para capturar errores que ocurren en cualquier parte de la cadena de promesas.
- **Encadenamiento de operaciones**
Permiten encadenar múltiples operaciones asíncronas de una manera más intuitiva. El resultado de una promesa puede ser pasado como entrada a la siguiente promesa en la cadena utilizando el método **.then()**.
- **Manejo de paralelismo**
Puedes utilizar constructores como **Promise.all()** y **Promise.race()** para manejar múltiples promesas al mismo tiempo. El primero espera a que todas las promesas se cumplan antes de continuar, mientras que el segundo se resuelve tan pronto como una de las promesas se cumple.
- **Legibilidad y mantenibilidad**
Las promesas hacen que el código asíncrono sea más fácil de leer y mantener, ya que proporcionan una estructura clara para manejar resultados exitosos y errores, en lugar de tener que rastrear flujos de control complejos en callbacks anidados.
- **Compatibilidad con async/await**
Asimismo, forman la base de las funciones async y await, una característica introducida en versiones más recientes de JavaScript. async/await simplifica aún más el manejo de código asíncrono al hacer que parezca código síncrono, mejorando la legibilidad.
##### Sintaxis
La sintaxis básica para crear una promesa es:
````
let promise = new Promise(function(resolve, reject) {
    // Realiza una operación asíncrona
    // Si la operación tiene éxito, llama a resolve con el resultado
    // Si la operación falla, llama a reject con un motivo de error
});
````
Luego, puedes encadenar métodos .then() y .catch() para manejar el resultado de la promesa:

El método **.then()** se ejecuta cuando la promesa se resuelve exitosamente y recibe el resultado como argumento.
El método **.catch()** se ejecuta cuando la promesa es rechazada y recibe el motivo del error como argumento. Está relacionado directamente con el reject, es el anzuelo para que atrape el error.

Vamos a ver un ejemplo básico de promesa:
````
let sleepyGreeting = new Promise ((resolve, reject)) => {
    setTimeOut(() => {
        resolve('Hello...')
    }, 2000);
    setTimeout(() => {
        reject (Error ('Too sleepy....'))
    },2000);
});
// Utilizamos las promesas

sleepyGreeting.then(data) => {
    console.log(data);
});
sleepyGreeting.catch(err) => {
    console.error(err);
});
````
Explicamos el **ejemplo:**
1º Creamos una promesa con la función flecha. La promesa recibe dos parámetros: **resolve** y **reject**, que son funciones proporcionadas por JavaScript para manejar el éxito y el fracaso de la promesa.
2º Utilizamos el **setTimeout** para simular una operación que tarda 2s en ejecutarse, el primero está dentro de la función que se ejecuta si la promesa tiene éxito y el segundo dentro de la función si la promesa NO tiene éxito.
3º Se utilizan los métodos **.then()** y **.catch()** para manejar el resultado de la promesa. .then() se ejecuta cuando la promesa se resuelve correctamente, mientras que .catch() se ejecuta cuando la promesa es rechazada.

#### Función fetch()
El equipo de desarrollo de JavaScript creó fetch(). La función **fetch()** se utiliza para hacer solicitudes de red, típicamente para obtener recursos de un servidor web. Es una función nativa del navegador que devuelve una promesa que resuelve la respuesta a la solicitud de red y se utiliza comúnmente en aplicaciones web para interactuar con servicios web y APIs.

**Ejemplo:**
````
const usersPromise = fetch('https://randomapi.com/api/6de6abfedb24f889e0b5f675edc50deb?fmt=raw&sole');
usersPromise
  .then(data => data.json())
  .then(data => {
    data.forEach((item) =>{
      console.log(item.first);
    })
  })
  .catch((err) => {
    console.log(err);
  });
````
Explicamos el **ejemplo:**
1º Se utiliza la función fetch() para hacer una solicitud HTTP GET a la URL https://randomapi.com/api/6de6abfedb24f889e0b5f675edc50deb?fmt=raw&sole. Esta función devuelve una promesa que se resolverá con la respuesta a la solicitud.
2º Se encadena un **.then()** para manejar la respuesta de la solicitud. Dentro de este .then(), utilizamos **data.json()** para convertir la respuesta en formato JSON.
3º Se encadena otro **.then()** para trabajar con los datos obtenidos del **data.json()** y dentro se recorre el ***array data*** utilizando un bucle **forEach()** y para cada elemento, imprimimos el valor de la propiedad **first** en la consola.
4º Finalmente, se utiliza **.catch()** para manejar cualquier error que pueda ocurrir durante la solicitud o el procesamiento de los datos. Si ocurre un error, se imprime en la consola.


##### Para ampliar conocimientos
Las promesas son un poco complejas de entender por eso te animo al leer tutoriales de como hacerlas e incluso ver videos dónde se explican de forma clara.
https://www.arsys.es/blog/promesas-javascript
https://platzi.com/blog/que-es-y-como-funcionan-las-promesas-en-javascript/
https://www.youtube.com/watch?v=ZTC0Gfhdzfc

# ¿Qué hacen async y await por nosotros?
Lo que hacen **async** y **await** en JavaScript es añadir transparencia en la forma en la que se ejecuta el código de cara al usuario.

¿Qué sucede cuando, por ejemplo, nuestro código necesita recibir algunos datos de una API? Si bien es necesario esperar la solicitud y respuesta de la API, no podemos bloquear el funcionamiento de todo nuestro programa. Es para este tipo de situaciones, que se **requiere un procesamiento asíncrono**.

Se pueden utilizar las promesas como vimos en la guía anterior o usar **Async/Await**, que son una sintaxis que **simplifica la programación asíncrona**, facilitando el flujo de escritura y lectura de código; por lo que es posible escribir código que funcione de forma asíncrona, pero que **se lea y estructure de forma síncrona**. Async/await funciona con **código basado en Promises**, pero oculta las promesas para que la lectura sea más fluida y sencilla de entender.
- **Async**: Se utiliza para definir funciones asíncronas, indicando que la función puede ser suspendida y luego reanudada en cualquier punto donde haya una llamada a una operación asíncrona.
- **Await**: Se utiliza dentro de funciones asíncronas para esperar el resultado de una operación asíncrona. Cuando se encuentra la palabra clave await, el intérprete sabe que puede pausar la ejecución de la función hasta que la operación asíncrona haya terminado, permitiendo que otros fragmentos de código se ejecuten mientras tanto. Solo puede usar await en funciones declaradas con la palabra-clave async.

Vamos a ver varios ejemplos que nos ayudarán a entender mejor estos procesos.
**EJEMPLO BÁSICO:** queremos que cuando un usuario inicie sesión y despúes se actualice su cuenta.
````
const login =() =>{
    return new Promise ((resolve, reject) => {
        setTimeout (() => {
            resolve ('User logged in ...');
        },2000);
    });
}
const updateAccount =() =>{
    return new Promise ((resolve, reject) => {
        setTimeout (() => {
            resolve ('Updating last login... ...');
        },2000);
    });
}
async function loginActivities(){
    const returnedLogin = await login();
    console.log (returnedLogin);
    const returnedUpdateAccount = await updateAccount();
    console.log (returnedUpdateAccount);
}
loginActivities(); // 1º "User logged in ..."
                      2º  2 segundos después "Updating last login... ..."
````
**Explicamos el ejemplo:** este código define dos funciones, **login y updateAccount**, que devuelven promesas que se resuelven después de un retraso de 2 segundos. Luego, la función **loginActivities** utiliza **async/await** para crear un flujo de trabajo con el orden correcto, lo que ocurre al llamar a la función es que 1º se produce el inicio de sesión (no queremos que ocurra nada más hasta que este proceso se haya completado) y 2s después la actualización de la cuenta.



**EJEMPLO:** vamos a usar async/await para comunicarnos con 2 Api's externas.
````
async function queryApis(){
    const pokePromise =fetch('https://pokeapi.co/api/v2/pokemon/ditto');
    const poke = await pokePromise.then (res=>res.json());
    console.log(poke);
    
    const reposPromise =fetch('https://api.github.com/users/ainhoaalonso/repos');
    const repos = await reposPromise.then (res=>res.json());
    console.log(repos);
}
queryApis();
````
Vamos a explicar el ejemplo:
1º Se define una función asíncrona llamada **queryApis()**.
2º Dentro de esta función, se hace una solicitud **fetch()** a la pokeapi, que de vuelve una promesa **pokePromise**.
3º Se utiliza el **await** para esperar que la promesa se resuelva y si lo hace, se convierte en formato **json()** y se almacena en la variable **poke**.
4º Se imprime por consola la información obtenida en la apipoke.
5º Hacemos otra solicitud **fetch()** a al apigithub para obtener los repositorios de un usuario específico, devuelve también una promesa **reposPromise**.
6º Se utiliza el **await** para esperar que la promesa se resuelva y si lo hace, se convierte en formato **json()** y se almacena en la variable **repos**.
7º Se imprime por consola la información obtenida en la apigithub.
8º Finalmente, se llama a la función queryApis() para iniciar el proceso de consulta de las APIs

Esto que hemos visto es suponiendo que estas APIS funcionarán al 100% todo el tiempo. Sin embargo, esto rara vez es así, por esto es muy importante poder configurar un proceso para lo que desea que suceda cuando falla una API.

Una opción para detectar errores con múltiples promesas es utilizar **try** y **catch**.

**EJEMPLO:** Vamos a modificar el ejemplo anterior.
````
async function queryApis(){
  try{
    const pokePromise = fetch('https://pokeapi.co/api/v2/pokemon/ditto');
    const poke = await pokePromise.then(res =>res.json());
    console.log(poke);
  } catch(err){
      console.log(err);
      console.log('Hay un error en a API de poke');
    }
  try{
    const reposPromise = fetch('https://api.github.com/users/ainhoaalonso/repos');
    const repos = await reposPromise.then(res =>res.json());
    console.log(repos);
  } catch(err){
      console.log(err);
      console.log('Hay un error en a API de Github');
    }
}
queryApis();
````
En este ejemplo lo que hacemos es envolver las promesas en un bloque **try** y si hay un error pasa al bloque **catch**.
Al poner bloques **catch** lo estamos haciendo más específico y decimos dónde está el error.
**NOTA** si deseamos que se detenga el proceso cuando se produce el error y no continuar, porque tengo promesas conectadas, lo colocamos todo dentro del **try**.
**IMPORTANTE:** este tipo de procesos son necesarios porque no podríamos realizar las siguientes llamadas a las APIs si la primera no se hubiese realizado ya, por eso **async y await**, se han vuelto tan populares en la comunidad de JavaScript, porque pueden controlar esto.












