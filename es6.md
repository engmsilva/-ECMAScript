# ECMAScript 6 (ES6/ES2015)

## Arrow Functions:
```javascript
// Antes do ES6
function soma(a, b) {
  return a + b;
}

// Com Arrow Function
const soma = (a, b) => a + b;
```

## Classes:
```javascript
class Animal {
  constructor(nome) {
    this.nome = nome;
  }

  falar() {
    console.log(`${this.nome} faz barulho.`);
  }
}

const gato = new Animal('Gato');
gato.falar(); // Isso imprimirá "Gato faz barulho."
```

## Let e Const:
```javascript
// Com var (escopo global ou de função)
var x = 10;
if (true) {
  var x = 20;
}
console.log(x); // Isso imprimirá 20

// Com let (escopo de bloco)
let y = 10;
if (true) {
  let y = 20;
}
console.log(y); // Isso imprimirá 10 (não afeta a variável externa)
```

## Template Literals:
```javascript
const nome = 'Alice';
console.log(`Olá, ${nome}!`); // Isso imprimirá "Olá, Alice!"
```

## Módulos:
```javascript
// Exportando um módulo
// arquivo modulo.js
export const soma = (a, b) => a + b;

// Importando um módulo
// arquivo principal.js
import { soma } from './modulo';
console.log(soma(2, 3)); // Isso imprimirá 5
```

## Promises:
```javascript
function esperar(segundos) {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      resolve(`Esperei ${segundos} segundos.`);
    }, segundos * 1000);
  });
}

esperar(2)
  .then(resultado => {
    console.log(resultado); // Isso imprimirá "Esperei 2 segundos."
  })
  .catch(erro => {
    console.error(erro);
  });
```

## Destructuring Assignment (Atribuição por Desestruturação):
```javascript
const pessoa = { nome: 'Alice', idade: 30 };
const { nome, idade } = pessoa;
console.log(nome); // Isso imprimirá "Alice"
console.log(idade); // Isso imprimirá 30
```

## Default Parameters (Parâmetros Padrão):
```javascript
function saudacao(nome = 'Visitante') {
  console.log(`Olá, ${nome}!`);
}

saudacao(); // Isso imprimirá "Olá, Visitante!"
saudacao('João'); // Isso imprimirá "Olá, João!"
```

## Rest Parameters (Parâmetros Rest):
```javascript
function soma(...numeros) {
  return numeros.reduce((total, numero) => total + numero, 0);
}

console.log(soma(1, 2, 3, 4)); // Isso imprimirá 10
```

## Spread Operator (Operador Spread):
```javascript
const numeros = [1, 2, 3];
const maisNumeros = [...numeros, 4, 5];

console.log(maisNumeros); // Isso imprimirá [1, 2, 3, 4, 5]
```

## Métodos de Array (como map, filter, reduce):
```javascript
const numeros = [1, 2, 3, 4, 5];

const quadrados = numeros.map(numero => numero ** 2);
console.log(quadrados); // Isso imprimirá [1, 4, 9, 16, 25]

const pares = numeros.filter(numero => numero % 2 === 0);
console.log(pares); // Isso imprimirá [2, 4]

const soma = numeros.reduce((total, numero) => total + numero, 0);
console.log(soma); // Isso imprimirá 15
```

## Object.entries() e Object.values():
```javascript
const objeto = { a: 1, b: 2, c: 3 };

// Object.entries() retorna uma matriz de pares chave-valor
const pares = Object.entries(objeto);
console.log(pares); // Isso imprimirá [["a", 1], ["b", 2], ["c", 3]]

// Object.values() retorna um array com os valores do objeto
const valores = Object.values(objeto);
console.log(valores); // Isso imprimirá [1, 2, 3]

// Object.keys() retorna um array com todas as chaves de um objeto
const objeto = { a: 1, b: 2, c: 3 };
const chaves = Object.keys(objeto);
console.log(chaves); // Isso imprimirá ["a", "b", "c"]
```

## Generator Function (função geradora):
```javascript
function* contador() {
  let i = 0;
  while (true) {
    yield i++;
  }
}

const gen = contador();

console.log(gen.next().value); // 0
console.log(gen.next().value); // 1
console.log(gen.next().value); // 2
```

