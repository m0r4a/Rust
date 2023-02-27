# v1-Bison

Va adentro de la función `fn main(){}`.

Para printear algo se utiliza `println!()`.

# v2-VariablesYConstantes

## Declarando variables

Se declara una variable con:

```rust
let x = 3;
```

## Imprimiendo variables

Se imprime una variable poniendo {} en el print y después de las "" se le pone ,variable, se van poniendo en el orden que tu las anotes, ejemplo:

```rust
let x = 3;

let y = 9;

println!("Las variables x y y son: {} y {}", x, y)

Output:

Las variables y y y son: 3 y 9
```

## Cambiar el valor de variables ya creadas (o hacerlas mutables)

Para hacer una variable mutable la tenemos que declaras de la siguiente forma:

```rust
let mut x = 5;
```

## Mutar variables

Para mutar una variable ya **NO** es necesario escribir el `let`, `let` es solamente para declararla.

```rust
let mut x = 5;

println!("{}", x)

x = 10;

println!("{}", x)

Output:

5
10
```

## Definir constantes

Para definir una constante se hace de esta forma:

[const] [nombreDeLaConstante]: [tipoDeDato] = [valor];

Ejemplo:

```rust
const PI: f32 = 3.1416;
```

## Diferencias entre `constantes` y `variables`

| Constantes | Variables|
|:-:         |:-:       |
| Se pueden mutar con mut | No hay forma de mutarlas |
| El compilador puede asumir su tipo de dato | Tienes que siempre especificar qué tipo de dato es |
| ? | Se puede declarar en cualquier ámbito, incluso global |
| Puede almacenar valores de un cálculo | Solamente puede almacenar un valor |
| Tienen que ir escritas en snake case | Van escitas en mayúsculas separadas por guíones bajos (_) |

## Redefiniendo variables (shadowing)

Se puede volver a crear una misma variable, para darle  un nuevo valor incluso de tipo distinto.

Ejemplo:

```rust
let x = 7;

let x = "a";
```

# v3-TiposDeDatos

## Tipos escalares

Representa un valor único. Rust tiene cuatro tipos escalares principales:

- Enteros
- Números de coma flotante (decimales)
- Booleanos
- Caracteres

## Tipos enteros 

Es un número sin componente decimal

| Longitud | Con signo | Sin signo |
|:-:       |:-:        |:-:        |
| 8-bit | i8 | u8 |
| 16-bit | i16 | u16 |
| 32-bit | i32 | u32 |
| 64-bit | i64 | u64 |
| 128-bit | i128 | u128 |
| Se comprenden dependiendo de la plataforma, si es de 32 o 64 bits | isize | usize |

_Nota: Con signo admite positivo y negativo, sin signo admite el 0 y números positivos._ 



### Especificar el tipo de una variable

Para especificar el tipo de una variable se hace de la siguiente forma:

let [nombreDeLaVariable]:[tipoDeLaVariable] = valor;

Ejemplo:

```rust
	let x:i32 = 300;
```

## Tipos en coma flotante (decimales)

Rust también tiene tipos primitivos para números de punto flotante. Los tipos de punto flotante son: f32 y f64.


## Operaciones básicas con números

Se pueden hacer operaciones matemáticas básicas, como en la mayoría de lenguaejes:

- Suma
- Resta
- Multiplicación
- División 
- Módulo (el residuo de la división)

Ejemplo:

```rust
	let suma = 50 + 50;

	let resta = 150.50 - 50.50;
	
	let multiplicación = 100 * 38;

	let división = 3800 / 38;

	let módulo = 1300 % 200;
```

## Tipo booleano 

Son variables que pueden tener de valor True ó False. Se declar con la palabra reservada bool.

Ejemplo:

```rust
	let verdadero:bool = true;

	let falso:bool = false;
```

## Tipo carácter

Rust admite el tipo char, se almacena en commillas simples '', a diferencia de las cadenas que se almacenan en comillas dobles "".

El tipo char en Rust tiene un tamaño de cuatro bytes y representa un valor Unicode, significa que podemos representar mucho más que con ASCII: letras acentuadas, caracteres de otros idiomas o emojis.

Ejemplo:

```rust
	let a = 'a';

	let emoji = '❤️';
```

## Tipos compuestos

Los tipos compuestos pueden tener varios valores en unsolo tipo. Rust tiene dos tipos de compuestos primitivos: tuplas y arrays.

### Tipo tupla

- Las tuplas son una forma general de agrupar varios valores, los cuales pueden ser de diferentes tipos, en un tipo compuesto.

- Las tuplas tienen una longitud fija, ya declaradas no pueden encogerse ni crecer.

- Se crean escribiendo una lista de valores entre paréntesis y separados por comas.

- Cada posición en la tupla tiene un tipo, y los tipos de los diferentes valores en la tupla no tienen que ser iguales.

Ejemplo:

```rust
	let tupla = (100.50, 10, -50);
```

- También le puedes asignar manualmente los tipos de datos que quieres que tenga, de esta forma:

let [nombreDeLaTupla];[(tipo1,tipo2,tipoN)] = [(valor1,valor2)]

Ejemplo:

``` rust
	let tupla:(f32,u8,i8) = (100.50, 10, -50);
```

#### También podemos asignar variables a los valores de la tupla

A esto se le llama _desestructuración_

Ejemplo:

```rust

	let tupla = (100.50, 10, -50);

	let (x,y,z) = tupla;

	println!("{} {} {}", x, z)

Output:

100.50 -50
```

#### Podemos acceder a un elemento específico de la tupla

Esto se hace declarando una variable que sea igual a el elemento que esté en cierta posición de la tupla.

Ejemplo:

```rust

	let tupla = (100.50, 10, -50);

	let segundo = tupla.1;

	println!("{}", segundo);

Output:

10
```

### Tipo array

- Permiten almacenar valores múltiples.

- Todos los elementos de la matriz deben ser del mismo tipo.

- En Rust, son de longitud fija, como las tuplas.

- Los valores del array se escriben como una lista entre corchetes y separada por comas.

Ejemplo:

``` rust
	let matriz = [10, 20, 40, 70]
```

#### Especificando el tipo de dato del array 

Se puede especificar el tipo de dato del array de la siguiente forma:

let [nombreDelArray]:[[tipo;longitud]] = [[valoresx,valoresy]]

```rust
	let array:[i8;5] = [10, 40, 100, 250]
```

#### Accediendo a un valor dentro del arreglo 

A diferencia de las tuplas, aquí se accede a los valores con corchetes, de la siguiente forma:

let [variable] = [array[pocisión]];

Ejemplo:

```rust
	let array = [10 , 20, 40, 70]

	let x = array[3];
``` 

##### Tip 

Un tip para los arreglos es que podemos hacer esto:

```rust
	let array = [3; 5];
```

Que es lo mismo que haber hecho esto:

```rust
	let array = [3, 3, 3, 3, 3]
```