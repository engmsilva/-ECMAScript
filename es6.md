# ECMAScript 6 (ES6/ES2015)

## Let e Const:
**Descrição:** `let` e `const` para declarar variáveis
```javascript
// Com var (escopo global ou de função)
var x = 10;
if (true) {
  var x = 20;
}
console.log(x); // Isso imprimirá *20*

// Com let (escopo de bloco)
let y = 10;
if (true) {
  let y = 20;
}
console.log(y); // Isso imprimirá *10* (não afeta a variável externa)
```

## Arrow Functions:
**Descrição:** Arrow functions (`() => {}`) para funções mais concisas
```javascript
// Antes do ES6
function soma(a, b) {
  return a + b;
}

// Com Arrow Function
const soma = (a, b) => a + b;
```

## Spread Operator (Operador Spread):
**Descrição:**  Espalha os elementos de um array em outro array
```javascript
const numeros = [1, 2, 3];
const maisNumeros = [...numeros, 4, 5];

console.log(maisNumeros); // Isso imprimirá *[1, 2, 3, 4, 5]*
```

## For/of:
**Descrição:**  Uma maneira simplificada de iterar em elementos de uma coleção, como um array
```javascript
const arr = ['a', 'b', 'c'];
for (const [index, elem] of arr.entries()) {
    console.log(index+'. '+elem);
}
```

## Map Object:
**Descrição:** Uma coleção de pares chave-valor onde as chaves podem ser objetos
```javascript
// Cria um Map para representar um carrinho de compras
const cart = new Map();

// Função para adicionar um item ao carrinho
function addToCart(item, quantity) {
  if (cart.has(item)) {
    cart.set(item, cart.get(item) + quantity); // Se o item já estiver no carrinho, atualiza a quantidade
  } else {
    cart.set(item, quantity); // Adiciona o item ao carrinho com a quantidade especificada
  }
}

// Função para listar os itens no carrinho
function listCart() {
  console.log('Carrinho de compras:');
  cart.forEach((quantity, item) => {
    console.log(`${item}: ${quantity}`);
  });
}

// Exemplos de uso
addToCart('Camiseta', 2);
addToCart('Calça', 1);
addToCart('Camiseta', 3); // Atualiza a quantidade de camisetas

listCart();

// Saída esperada
// Carrinho de compras:
// *Camiseta: 5*
// *Calça: 1*
```

## Set Object:
**Descrição:** Uma coleção de valores únicos
```javascript
const set = new Set([1, 2, 3]);
```

## Classes:
**Descrição:** Uma maneira de criar objetos e definir métodos em um formato mais orientado a objetos.
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
gato.falar(); // Isso imprimirá *Gato faz barulho.*
```

## Promises:
**Descrição:** Lida com código assíncrono de forma mais eficiente.
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
    console.log(resultado); // Isso imprimirá *Esperei 2 segundos.*
  })
  .catch(erro => {
    console.error(erro);
  });
```

## Symbol:
**Descrição:** Um tipo de dado primitivo que é usado para criar identificadores únicos
```javascript
const user = {
  name: 'Alice',
};
const metadata = Symbol('metadata');
user[metadata] = { age: 30, email: 'alice@example.com' };
console.log(user); // Isso imprimirá *{name: 'Alice', Symbol(metadata): {…}}*
console.log(user[metadata]); // Isso imprimirá *{age: 30, email: 'alice@example.com'}*
```

## Default Parameters (Parâmetros Padrão):
**Descrição:** Permite definir valores padrão para parâmetros de função
```javascript
// Defini valores padrão para os argumentos da função
function saudacao(nome = 'Visitante') {
  console.log(`Olá, ${nome}!`);
}
saudacao(); // Isso imprimirá *Olá, Visitante!*
saudacao('João'); // Isso imprimirá *Olá, João!*
```

## Function Rest Parameter (Parâmetros de Função Rest):
**Descrição:**  Permite passar um número variável de argumentos para uma função
```javascript
function soma(...numeros) {
  return numeros.reduce((total, numero) => total + numero, 0);
}

console.log(soma(1, 2, 3, 4)); // Isso imprimirá *10*
```

## String.includes():
**Descrição:** Verifica se uma string contém outra string
```javascript
const message = 'Hello, world!';
const hasHello = message.includes('Hello');
console.log(hasHello); Isso imprimirá *true*
```

## Object.entries(), Object.values() e Object.keys():
**Descrição:**  Métodos que retornam pares chave-valor de objetos
```javascript
const objeto = { a: 1, b: 2, c: 3 };

// Object.entries() retorna uma matriz de pares chave-valor
const pares = Object.entries(objeto);
console.log(pares); // Isso imprimirá *[["a", 1], ["b", 2], ["c", 3]]*

// Object.values() retorna um array com os valores do objeto
const valores = Object.values(objeto);
console.log(valores); // Isso imprimirá *[1, 2, 3]*

// Object.keys() retorna um array com todas as chaves de um objeto
const objeto = { a: 1, b: 2, c: 3 };
const chaves = Object.keys(objeto);
console.log(chaves); // Isso imprimirá *["a", "b", "c"]*
```

## JavaScript Modules:
**Descrição:**  Permite dividir o código em módulos separados para melhor organização e reutilização.
```javascript
// Exportando um módulo
// arquivo modulo.js
export const soma = (a, b) => a + b;

// Importando um módulo
// arquivo principal.js
import { soma } from './modulo';
console.log(soma(2, 3)); // Isso imprimirá *5*
```

## Destructuring Assignment (Atribuição por Desestruturação):
**Descrição:** Desestruturação para extrair valores de objetos e arrays.
```javascript
// Desestruturação de Objeto
const pessoa = { nome: 'Alice', idade: 30 };
const { nome, idade } = pessoa;
console.log(nome); // Isso imprimirá "Alice"
console.log(idade); // Isso imprimirá *30*

// Desestruturação de Array
const iterable = ['a', 'b'];
const [x, y] = iterable;
console.log(x, y); // x = *a*; y = *b*
```

## Template Literals:
**Descrição:** Permite a incorporação de expressões JavaScript dentro de strings usando a sintaxe `${expressão}`.
```javascript
// Citações dentro de strings
let text = `Ele é frequentemente chamado de "Mestre"`;

// Strings multilinhas
let text =
`O Rato
roeu a roupa
do rei
de Roma`;

// Interpolação de strings
const nome = 'Alice';
console.log(`Olá, ${nome}!`); // Isso imprimirá "Olá, Alice!"

// Substituição de expressão
let price = 10;
let VAT = 0.25;
let total = `Total: ${(price * (1 + VAT)).toFixed(2)}`;

// Modelos HTML
let header = "Templates Literals";
let tags = ["template literals", "javascript", "es6"];
let html = `<h2>${header}</h2><ul>`;
for (const x of tags) {
  html += `<li>${x}</li>`;
}
html += `</ul>`;
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

console.log(gen.next().value); // *0*
console.log(gen.next().value); // *1*
console.log(gen.next().value); // *2*
```

