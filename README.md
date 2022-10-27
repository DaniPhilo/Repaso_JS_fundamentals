# Repaso_JS_fundamentals

## Ejercicio 1
Escribe un función que acepte un array de números y devuelva la suma de los números impares.

## Ejercicio 2
Escribe una función que acepte un array e imprima por consola cada elemento del array, pero empezando por el final.

## Ejercicio 3
Escribe una función que acepte un array y un número. La función debe imprimir por consola un elemento cada n posiciones. Ejemplo:
```javascript
const array = ["apple", "orange", "banana", "mango", "watermelon", "grape", "peach"];

getEachElement(array, 2) // "orange" "mango" "grape"
getEachElement(array, 3) // "banana", "grape"
```

## Ejercicio 4
Escribe una función que acepte dos argumentos: el primero será un objeto, el segundo una **key**. Si el objeto tiene dicha **key**, deberás borrarla y devolver `true`; si no, deberás devolver `false`.
Ejemplo: 
```javascript
const myObject = {
	name: "Paco",
	age: 28
}

deleteProp(myObject, "name") // true
console.log(myObject) // { age: 28 }

deleteProp(myObject, "city") // false
console.log(myObject) // { name: "Paco", age: 28 }
```

## Ejercicio 5
Escribe una función que acepte un array bidimensional e imprima por consola cada elemento presente en los arrays internos:
```javascript
const arr = [[1, 2], [3, 4, 5, 6], [7, 8, 9], [0]];

printElements(arr) // 1 2 3 4 5 6 7 8 9 0 
```

## Ejercicio 6
Tienes el siguiente array: 
```javascript
const drinks = [
	{
		name: "Cerveza",
		price: "3.50",
		ingredients: ["cebada", "lúpulo"]
	},
	{
		name: "Coca Cola",
		price: "3.00",
		ingredients: ["desconocido"]
	},
	{
		name: "Vino",
		price: "5.50",
		ingredients: ["uvas", "taninos"]
	},
	{
		name: "Vodka",
		price: "7.00",
		ingredients: ["patata", "agua", "etanol"]
	},
	{
		name: "Whiskey",
		price: "7.00",
		ingredients: ["trigo", "agua", "etanol"]
	},
	{
		name: "Zumo de naranja sin azúcar",
		price: "4.75",
		ingredients: ["naranjas", "aspartamo", "maltitol", "xilitol"]
	},
]
```

Escribe una función que itere por el array y, para cada elemento, imprima en consola el siguiente mensaje:
```javascript
"La bebida <bebida> tiene un precio de <precio> y los siguientes ingredientes: <ingrediente>, <ingrediente>, <ingrediente> (etc.)"
```

## Ejercicio 7
Escribe una función que reciba un array. Este array contendrá, a su vez, varias arrays con dos valores cada una:
```javascript
[ ["name", "Pedro"], ["job", "Megateacher"], ["age", 35], ["city", "Melilla"], ["isMarried", false] ]
```
La función debe devolver un objeto que tenga como **key** el primer elemento de cada array, y como **value**, el segundo:
```javascript
{
	"name": "Pedro",
	"job": "Megateacher",
	"age": 35,
	"city": "Melilla",
	"isMarried": false
}
```

## Ejercicio 8
Escribe una función que acepte un array de strings y devuelva otro array con los elementos del primer array que tengan menos de 6 letras:
```javascript
const arr = ["casa", "reloj", "carótida", "coco", "elemento", "GammaTech", "dado"];

getSmallWords(arr) // ["casa", "reloj", "coco", "dado"]
```

## Ejercicio 9
Escribe una función que reciba un objeto y convierta cada par **key** / **value** en un array bidimensional:
```javascript
const myObj = {
	name: "Pedro",
	age: 35
}

getProps(myObj) // [ ["name", "Pedro"], ["age", 35] ]
```

## Ejercicio 10
Tienes el siguiente objeto:
```javascript
const megaTeacher = {
	name: "Pablo",
	lastname: "Quintana",
	age: 27,
	vegan: false,
	address: {
		street: "Gran Vía",
		number: 73,
		floor: 4
	},
	hobbies: ["basketball", "coding", "music", "reading"],
	height: 1.98
}
```

1. Escribe una función que acepte un hobbie y lo añada a la lista de hobbies de nuestro megaTeacher.
2. Escribe un método `introduceMySelf` dentro del objeto que devuelva el siguiente string: `"Hola, me llamo <name> <lastname>, tengo [age] años y vivo en la calle <street>, <number>. Mis hobbies son: <hobbie>, <hobbie>, <hobbie> (etc.)"`.
3. Modifica la primera función: debe aceptar un array de nuevos hobbies, y se lo añadirá a los hobbies del objeto hasta que éstos últimos sean 8, no más. Ejemplo:
```javascrip
addHobbies(["dancing", "movies", "traveling", "eating", "exercise", "museums"])
console.log(megaTeacher.hobbies) // ["basketball", "coding", "music", "reading", "dancing", "movies", "traveling", "eating"] (al llegar a 8, deja de introducir elementos)
```

## Ejercicio 11
Escribe una función que acepte un número y un substractor (otro número). Mientras que el número sea mayor que `0`, debes restarle el substractor. Debes devolver el número tal y como ha quedado despues de las restas. **No puedes usar un bucle for**:
```javascript
substract(10, 3) // -2
substract(5, 1) // 0
```
  
### Ejercicio 1

Teniendo dos arrays con valores individuales, escriba un programa de JavaScript para calcular la suma de cada valor de cada índice individual de los arrays dados.

Ejemplo de arrays :   
```js
array1 = [1,0,2,3,4];  
array2 = [3,5,6,7,8,13];
```

Output :  
```js
[4, 5, 8, 10, 12, 13]
```
<summary></summary>

<details><summary>Respuesta - ¡Haz Click!</summary>


```js

function Arrays_sum(array1, array2) 
{
  var result = [];
  var ctr = 0;
  var x=0;

  if (array1.length === 0) 
   return "array1 is empty";
  if (array2.length === 0) 
   return "array2 is empty";   

 while (ctr < array1.length && ctr < array2.length) 
  {
    result.push(array1[ctr] + array2[ctr]);
    ctr++;
  }

 if (ctr === array1.length) 
 {
    for (x = ctr; x < array2.length; x++)   {
      result.push(array2[x]);
    }
  } 
  else
  {
  for (x = ctr; x < array1.length; x++) 
    {
      result.push(array1[x]);
    }
  }
  return result;
}

console.log(Arrays_sum([1,0,2,3,4], [3,5,6,7,8,13]));

//[4,5,8,10,12,13]
```


Versión ES6
```js

function Arrays_sum(array1, array2) 
{
  const result = [];
  let ctr = 0;
  let x=0;

  if (array1.length === 0) 
   return "array1 is empty";
  if (array2.length === 0) 
   return "array2 is empty";   

 while (ctr < array1.length && ctr < array2.length) 
  {
    result.push(array1[ctr] + array2[ctr]);
    ctr++;
  }

 if (ctr === array1.length) 
 {
    for (x = ctr; x < array2.length; x++)   {
      result.push(array2[x]);
    }
  } 
  else
  {
  for (x = ctr; x < array1.length; x++) 
    {
      result.push(array1[x]);
    }
  }
  return result;
}

console.log(Arrays_sum([1,0,2,3,4], [3,5,6,7,8,13]));

```
</details>


### Ejercicio 2

Escribe un programa en JavaScript para calcular la unión de dos arrays

Ejemplo:  

```js
console.log(union([1, 2, 3], [100, 2, 1, 10]));  
```

Output:
```js
 [1, 2, 3, 10, 100]
```

<details><summary>Respuesta - ¡Haz Click!</summary>


```js
function union(arra1, arra2) {
  
  if ((arra1 == null) || (arra2==null)) 
    return void 0;
  
  var obj = {};
 
  for (var i = arra1.length-1; i >= 0; -- i)
     obj[arra1[i]] = arra1[i];
 
  for (var i = arra2.length-1; i >= 0; -- i)
     obj[arra2[i]] = arra2[i];
 
  var res = [];
 
  for (var n in obj)
  {
  
    if (obj.hasOwnProperty(n)) 
      res.push(obj[n]);
  }
 
  return res;
}
console.log(union([1, 2, 3], [100, 2, 1, 10]));

// [1,2,3,10,100]
```
</details>


### Ejercicio 3

Escribe una función de JavaScript para encontrar las diferencia entre dos arrays.

Ejemplo: 
```js
console.log(difference([1, 2, 3], [100, 2, 1, 10]));   
// ["3", "10", "100"]  
console.log(difference([1, 2, 3, 4, 5], [1, [2], [3, [[4]]],[5,6]]));   
// ["6"]  
console.log(difference([1, 2, 3], [100, 2, 1, 10]));  
// ["3", "10", "100"]

```

<details><summary>Respuesta - ¡Haz Click!</summary>

```js
function differenceOf2Arrays (array1, array2) {
var temp = [];
array1 = array1.toString().split(',').map(Number);
array2 = array2.toString().split(',').map(Number);

for (var i in array1) {
if(array2.indexOf(array1[i]) === -1) temp.push(array1[i]);
}
for(i in array2) {
if(array1.indexOf(array2[i]) === -1) temp.push(array2[i]);
}
return temp.sort((a,b) => a-b);
}

console.log(differenceOf2Arrays([1, 2, 3], [100, 2, 1, 10]));
console.log(differenceOf2Arrays([1, 2, 3, 4, 5], [1, [2], [3, [[4]]],[5,6]]));

// [3,10,100]
// [6]

```
</details>


### Ejercicio 4

Escriba un programa de JavaScript para mostrar el estado de la lectura (es decir, mostrar el nombre del libro, el nombre del autor y el estado de la lectura) de los siguientes libros.
```js
let library = [ 
   {
       author: 'Bill Gates',
       title: 'The Road Ahead',
       readingStatus: true
   },
   {
       author: 'Steve Jobs',
       title: 'Walter Isaacson',
       readingStatus: true
   },
   {
       author: 'Suzanne Collins',
       title:  'Mockingjay: The Final Book of The Hunger Games', 
       readingStatus: false
   }];

```

<details><summary>Respuesta - ¡Haz Click!</summary>

```js
for (var i = 0; i &lt; library.length; i++) 
   {
    var book =` ' ${library[i].title}  '  by  ${library[i].author}  .`;
    if (library[i].readingStatus) {
      console.log(`Already read " ${book}`);
    } else
    {
     console.log(`You still need to read ${book}`);
    }
   }
// Already read 'Bill Gates' by The Road Ahead.
// Already read 'Steve Jobs' by Walter Isaacson.
// You still need to read 'Mockingjay: The Final Book of The Hunger Games' by Suzanne Collins.
```

</details>


### Ejercicio 5

Escriba una función JavaScript para comprobar si un "input" es un string o no.

Ejemplo: 

```js
console.log(is_string('w3resource'));   
true  
console.log(is_string([1, 2, 4, 0]));  
false
```

<details><summary>Respuesta - ¡Haz Click!</summary>

```js

is_string = function(input) {
  if (Object.prototype.toString.call(input) === '[object String]')
    return true;
  else
    return false;   
    };
console.log(is_string('w3resource')); // true
console.log(is_string([1, 2, 4, 0])); // false

```
</details>


### Ejercicio 6

Escribe una función de JavaScript que concatene un string dado n veces (por defecto es 1).

Ejemplo: 

```javascript
console.log(repeat('Ha!'));   
console.log(repeat('Ha!',2));   
console.log(repeat('Ha!',3));  
// "Ha!"   
// "Ha!Ha!"   
// "Ha!Ha!Ha!"
```

<details><summary>Respuesta - ¡Haz Click!</summary>

```js
repeat = function repeat(str, count) {
    if(typeof(count) == "undefined") {
    count =1;
  }
  return count &lt; 1 ? '' : new Array(count + 1).join(str);
    }
console.log(repeat('Ha!'));
console.log(repeat('Ha!',2));
console.log(repeat('Ha!',3));
```
</details>
  
  
# Bonus tracks

## Bonus 1
Escribe una función que acepte arrays bidimensionales y devuelva un nuevo array plano:
```javascript
const arr = [ [1, 2], [3, 4], [5, 6], [7] ];

flattenArray(arr) // [1, 2, 3, 4, 5, 6, 7]
```
Tienes que hacerlo de dos formas:
1. Usando el método de array `flat()`.
2. Usando `reduce()`.  

## Bonus 2
Tienes 3 arrays:
```javascript
const arr1 = ['b', 'd', 'e', 'a'];
const arr2 = ['b', 'c', 'e', 'd'];
const arr3 = ['a', 'b', 'e', 'c'];
```

Escribe una función que devuelva un nuevo array que contenga aquellos elementos que estén incluidos en TODOS los arrays:
```javascript
getCommonElements(arr1, arr2, arr3) // ['b', 'e']
```
