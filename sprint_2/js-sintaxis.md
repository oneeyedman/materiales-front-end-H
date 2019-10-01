# Sintaxis de JS: resumen del módulo 2

Resumen de la sintaxis de JavaScript del módulo 2.

## Constantes y variables

```javascript
const name = 'Maricarmen'; // constante de texto
const age = 18; // constante de número
const isLogged = true; // constante de boolean: verdadera
const isSignUp = false; // constante de boolean: falsa
const color = null; // constante definida como nulo

let email = 'info@adalab.es'; // variable inicializada o definida
let password; // variable no inicializada o indefinida, su valor es undefined
```

## Condicionales

### Tipos de condicionales

```javascript
const age = 20;
if (age > 18) {
  // mayor que
}
if (age >= 18) {
  // mayor o igual que
}
if (age < 18) {
  // menor que
}
if (age <= 18) {
  // menor o igual que
}
if (age === 18) {
  // igual que
}
if (age !== 18) {
  // diferente de
}
```

### Varios condicionales en un if

```javascript
const age = 20;
const name = 'Maricarmen';
const email = 'info@adalab.es';
if (age > 18 && name === 'Lucía') {
  console.log('La edad es mayor de 18 y el nombre es Lucía');
}
if (age > 18 || name === 'Lucía') {
  console.log('La edad es mayor de 18 o el nombre es Lucía');
}
if ((age > 18 || name === 'Lucía') && email === 'contact@adalab.es') {
  console.log('(La edad es mayor de 18 o el nombre es Lucía) y el email es contact@adalab.es');
}
```

### if

```javascript
const age = 20;
if (age > 18) {
  console.log('Eres mayor de edad');
}
```

### if / else

```javascript
const age = 20;
if (age > 18) {
  console.log('Eres mayor de edad');
} else {
  console.log('No eres mayor de edad');
}
```

### if / else if / else

```javascript
const age = 20;
if (age < 3) {
  console.log('Eres un bebé');
} else if (age < 12) {
  console.log('Eres una niña');
} else if (age < 17) {
  console.log('Eres una adolescente');
} else if (age < 30) {
  console.log('Eres una joven');
} else if (age < 65) {
  console.log('Eres una persona adulta');
} else {
  console.log('Eres una persona mayor');
}
```

## Funciones

### Tipos de funciones

```javascript
// función normal
function add(a, b) {
  const result = a + b;
  return result;
}
const resultValue = add(1, 2);
console.log(resultValue);
```

```javascript
// función anónima
const add = function(a, b) {
  const result = a + b;
  return result;
};
const resultValue = add(1, 2);
console.log(resultValue);
```

```javascript
// función arrow
const add = (a, b) => {
  const result = a + b;
  return result;
};
const resultValue = add(1, 2);
console.log(resultValue);
```

### Tipos de funciones por los parámetros que reciben

```javascript
// función anónima que recibe 0 parametros
const showWarning = function() {
  const paragraph = document.querySelector('body');
  paragraph.innerHTML = 'Aviso!!!';
};
showWarning();
```

```javascript
// función anónima que recibe 2 parametros
const add = function(a, b) {
  const result = a + b;
  return result;
};
const resultValue = add(1, 2);
console.log(resultValue);
```

### Tipos de funciones por su retorno

```javascript
// función sin retorno, es decir retorna undefined
const showWarning = function() {
  const paragraph = document.querySelector('body');
  paragraph.innerHTML = 'Aviso!!!';
};
showWarning();
```

```javascript
// función con retorno
const add = function(a, b) {
  const result = a + b;
  return result;
};
const resultValue = add(1, 2);
console.log(resultValue);
```

### Funciones arrow con/sin retorno implícito

```javascript
// función arrow que recibe 2 parametros sin retorno implícito
const add = (a, b) => {
  const result = a + b;
  return result;
};
const resultValue = add(1, 2);
console.log(resultValue);
```

```javascript
// función arrow que recibe 2 parametros con retorno implícito
const add = (a, b) => a + b;
const resultValue = add(1, 2);
console.log(resultValue);
```

### Funciones arrow con 0, 1 o más argumentos

```javascript
// función arrow que recibe 0 argumentos
const showWarning = () => {
  const paragraph = document.querySelector('body');
  paragraph.innerHTML = 'Aviso!!!';
};
showWarning();
```

```javascript
// función arrow que recibe 1 argumento, no hace falta poner el argumento paréntisis
const showWarning = text => {
  const paragraph = document.querySelector('body');
  paragraph.innerHTML = text;
};
showWarning('Aviso!!!');
```

```javascript
// función arrow que recibe más argumentos
const showWarning = (selector, text) => {
  const paragraph = document.querySelector(selector);
  paragraph.innerHTML = text;
};
showWarning('body', 'Aviso!!!');
```

## Eventos

```javascript
// escuchamos el evento click sobre el elemento con selector .js-element
const handleClick = function(ev) {
  console.log('Elemento que lanza el evento:', ev.target);
  console.log('Elemento que escucha el evento:', ev.currentTarget);
  console.log('Evento:', ev);
};
const element = document.querySelector('.js-element');
element.addEventListener('click', handleClick);
```

## Objetos

```javascript
// objeto inicializado con propiedades y métodos
const car = {
  positionX: 0,
  positionY: 0,
  move: function(x, y) {
    this.positionX = this.positionX + x;
    this.positionY = this.positionY + y;
  }
};
```

```javascript
// objeto inicializado vacío
const car = {};
// y le añadimos propiedades y métodos después
car.positionX = 0;
car.positionY = 0;
car.move = function(x, y) {
  this.positionX = this.positionX + x;
  this.positionY = this.positionY + y;
};
```

```javascript
// leer y modificar una propiedad
const car = {
  positionX: 0,
  positionY: 0
};
console.log(car.positionX);

// modificar una propiedad con 'dot notation'
car.positionX = 10;
console.log(car.positionX);

// modificar una propiedad con corchetes
car['positionX'] = 20;
console.log(car.positionX);

// modificar una propiedad con corchetes y una través de una variable o constante
const property = 'positionX';
car[property] = 30;
console.log(car.positionX);
```

## Arrays

```javascript
// array de strings
const fruits = ['apple', 'orange'];
console.log(fruits); // array completo
console.log(fruits[0]); // primer elemento del array
console.log(fruits[1]); // segundo elemento del array
console.log(fruits.length); // longitud del array
```

```javascript
// array de objetos
const fruits = [
  {
    name: 'apple',
    color: 'green'
  },
  {
    name: 'orange',
    color: 'orange'
  }
];
console.log(fruits); // array completo
console.log(fruits[0]); // primer elemento del array
console.log(fruits[1]); // segundo elemento del array
```

## Bucles

### for con índice

```javascript
// recorrer el array de forma ascendente
const fruits = ['apple', 'orange'];
// "i" coge el valor del índice en cada iteración
for (let i = 0; i < fruits.length; i = i + 1) {
  console.log(fruits[i]);
}
```

```javascript
// recorrer el array de forma ascendente
const fruits = ['apple', 'orange'];
for (let i = fruits.length - 1; i >= 0; i = i - 1) {
  console.log(fruits[i]);
}
```

> **Nota:** para incrementar el índice de uno en uno podemos usar estas tres formas que son equivalentes: `i = i + 1`, `i += 1` y `i++`.

### for ... of

```javascript
const fruits = ['apple', 'orange'];
// "fruit" coge el valor de la posición (o lo que es lo mismo, el índice) en cada iteración
for (const fruit of fruits) {
  console.log(fruit);
}
```

## querySelector y querySelectorAll

```javascript
// obtener el primer elemento dentro de toda la página que tenga el selector .js-element
const element = document.querySelector('.js-element'); // element es un elemento del DOM
```

```javascript
// obtener el primer elemento dentro de toda la página que tenga el selector .js-header
const header = document.querySelector('.js-header');
// obtener el primer elemento dentro del header que tenga el selector .js-element
const element = header.querySelector('.js-element');
```

```javascript
// obtener todos los elementos dentro de toda la página que tengan el selector .js-element
const elements = document.querySelectorAll('.js-element'); // elements es un array de elementos del DOM
```

## Debugger

```javascript
debugger;
```
