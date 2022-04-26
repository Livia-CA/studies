# Funções :computer: :books: 



### Objetivos :checkered_flag:

- Mostrar como declarar funções 
- Como manipular parâmetros
- Apresentar loops e outras declarações
- Apresentar o argumento "*this*"



[TOC]



## Tipos de função

### Estrutura

*Definição comum de uma função*

```javascript
function nome(parametros){
    //instruções
    return; //valor de retorno
}
```

+ Variáveis criadas dentro de uma função apenas podem ser utilizadas dentro dela. 
+ Quando invocamos o "return", a função para de ser executada.



### Função Anônima

*Funções que representam expressões*

```js
const soma = function (a,b) {
    return a + b;
}

soma(1, 2) // 3
soma(5, 4) // 9
```

- Uma variável pode armazenar uma função



### Função autoinvocável

*IIF (Immediately Invoked Function Expression)*

```js
(
    function() {
        let name = "name"
        return name;
    }
)();

// name
```

- Uma função anônima entre parênteses, seguida por outro par de parênteses, que representa sua chamada.

```javascript
const soma = (
	function() {
        return a + b; 
    }
)(1,2);

console.log(soma) //3
```

- Também pode ser utilizada com parâmetros ou armazenada em uma variável.



### Callbacks

*Uma função passada como argumento para outra*

```js
const calc = function(operacao, num1, num2){
    return operacao(num1, num2);
}

const soma = function(num1, num2){
    return num1 + num2;
}

const sob = function(num1, num2){
    return num1 - num2;
}

const resultSoma = calc(soma, 1, 2);
const resultSob = calc(sub, 1, 2);

console.log(resultSoma); // 3
console.log(resultSob); // 1

```

- Utilizando callbacks, você tem maior controle da ordem de chamadas.



## Parâmetros

### Valores padrão

```javascript
function nome (parametro1, parametro2 = 2){
    //instruções
}
```

- Se o valor do parametro2 não existir, ele vai ser por padrão igual a 2, conforme foi definido. 



### Objeto "arguments"

```javascript
function showArgs() {
    return arguments;
}

showArgs(1, 2, [2, 3, 4], "string");

// [1, 2, [2, 3, 4], "string"]
```

- Consiste em uma coleção com todos os parâmetros passados quando a função foi invocada. Como ele possui índices e a propriedade *length*, por exemplo, este pode ser manipulado como um *Array*.



### Arrays

***Spread**: uma forma de lidar separadamente com elementos*

```javascript
function sum(x, y, z) {
	return x + y + z;
}

const numbers = [1, 2, 31;

console.log(sum(...numbers));
```

*  O que era parte de um array se torna um elemento independente.



***Rest**: combina os argumentos em um array*

```javascript
function confereTamanho(...args) {
	console.log(args.length)
}

confereTamanho() // @

confereTamanho(1,2) // 2	

confereTamanho (3, 4, 5) // 3
```

*  O que era um elemento independente se torna parte de um array.



### Objetos

*Object Destructuring*

```javascript
const user = {
	id: 42,
	displayName: jdoe",
	fullName: {
		firstName: 'John',
		lastName: 'Doe'
	}
};

function userId({id}) {
	return id;
}

function getFullName({fullName: {firstName: first, lastName: last}}) {
	return `${first} ${last}`;
}

userId(user);
//42

getFullName(user)
//John Doe
```

*  Entre chaves {}, podemos filtrar apenas os dados que nos interessam em um objeto.



## Loops

### If/else

```javascript
function numeroPositivo (num) { // Condição
	let resultado;
	if(num < 0) { //  Ocorre caso a condição seja verdadeira
		resultado = false;
	} else { //  Ocorre caso a condição seja falsa
	resultado = true;
	}
	return resultado;
}

numeroPositivo(2);
// true

numeroPositivo(-9);
// false
```



### Switch

```javascript
function getAnimal ( id ) {
	switch ( id ) {
    	case 1 :
      		return " cão " ;
    	case 2 :
      		return " gato " ;
    	case 3 :
      		return " pássaro " ;
    	default :
      		return " peixe " ;
  	}
}

getAnimal ( 1 ) // cão
getAnimal ( 4 ) // peixe
getAnimal ( " 1 " ) // peixe
```

- Equivale a uma comparação de tipo e valor (===);
- Sempre precisa de um valor "default";
-  Ideal para quando se precisa comparar muitos valores.



### For

*Loop dentro de elementos iteráveis (arrays, strings).*

```javascript
function multiplicaPorDois (arr) {
	let multiplicados = [];
	for(let i = 0; i < arr.length; i++) {
		multiplicados.push(arr[i] * 2);
	}
	return multiplicados;
}

const meusNumeros = [2, 33, 456, 356, 40];

multiplicaPorDois (meusNumeros);
// [4, 66, 912, 712, 80]
```



### For...in

*Loop entre propriedades enumeráveis de um objeto.*

```javascript
function forInExemplo ( obj ) {
	for ( prop in obj ) {
    	console.log ( prop ) ;
}
    
const meu0bjeto = {
	nome : " João " ,
  	idade : " 20 " ,
 	cidade : " Salvador "
}

forInExemplo( meuObjeto ) ;
// nome
// idade
// cidade
```



### For...of

*Loop entre estruturas iteráveis (arrays, strings).*

```javascript
function logLetras ( palavra ) {
 	for ( letra of palavra ) {
    	console.log ( letra ) ;
 	}
}

const palavra = " abacaxi " ;
logLetras(palavra);
// a
// b
// a
// c
// a
// x
// i
```



### While

*Executa instruções até que a condição se torne falsa.*

```javascript
function exemploWhile ( ) {
  	let num = 0
 	while ( num < = 5 ) {
    	console.log ( num ) ;
    	num ++ ;
	 }
}
exemploWhile();
// 1
// 2
// 3
// 5
```



### Do while

*Executa instruções até que a condição se torne falsa . Porém a primeira execução sempre ocorre .*

```javascript
function exemploDoWhile ( ) {
	let num = 0 ;
  	do {
    	console.log ( num ) ;
   		num ++ ;
  	}while ( num < = 5 )
}	

exemploDoWhile ( )
// 0
// 1
// 2
// 3
// 4
// 5
```



## This

### O que é?

 *A palavra reservada this é uma referência de contexto.*

```js
const pessoa = {
	firstName: "André",
	lastName: "Soares",
	id: 1,
	fullName: function() {
		return this.firstName + " " + this.lastName;
	},
	getId: function() {
		return this.id;
	}
};

pessoa.fullName();
// "André Soares"
pessoa.getId();
// 1
```

* No exemplo, this refere-se ao objeto pessoa.



 *Seu valor pode mudar de acordo com o lugar no código onde foi chamada.*

| Contexto              | Referência                             |
| --------------------- | -------------------------------------- |
| Em um objeto (método) | Próprio objeto dono do método          |
| Sozinha               | Objeto global (em navegadores, window) |
| Função                | Objeto global                          |
| Evento                | Elemento que recebeu o evento          |



### Manipulando seu valor

#### Call

```js
const pessoa = {
	nome: 'Miguel',
};

const animal = {
	nome: 'Murphy',
};

function getSomething() {
	console.log(this.nome);
}

getSomething.call(pessoa);

//Miguel
```



*É possível passar parâmetros para essa função separando-os por vírgulas*

```js
const myObj = {
	num1: 2,
	num2: 4,
};

function soma(a, b) {
	console.log(this.num1 + this.num2 + a + b);
}

soma.call(myObj, 1, 5);
//12
```



#### Apply

```js
const pessoa = {
	nome: 'Miguel',
};

const animal = {
	nome: 'Godi',
};

function getSomething() {
	console.log(this.nome);
}

getSomething.apply(pessoa);
//Miguel
```



*É possível passar parâmetros para essa função dentro de um array.*

```js
const myObj = {
	num1: 2,
	num2: 4,
};

function soma(a, b) {
	console.log(this.numl + this.num2 + a + b);
}

soma.apply(myObj, [[1, 5]);
// 12
```



#### Bind

*Clona a estrutura da função onde é chamada e aplica o valor do objeto passado como parâmetro.*

```js
const retornaNomes = function () {
	return this.nome;
};

let bruno = retornaNomes.bind({ nome: 'Bruno'});

bruno();
// Bruno
```



## Arrow functions

### Sintaxe

```js
 const helloWorld = () => "Hello World";
```

 - Caso exista apenas uma linha, pode dispensar as chaves e o return.
- Caso exista apenas um parâmetro, pode dispensar os parênteses.

* Arrow function NÃO faz hoisting!



### Outras restrições

- "this" sempre será o objeto global. Métodos para modificar seu valor não irão funcionar;
- Não existe o objeto "arguments";
- O construtur (ex: new MeuObjeto()) também não pode ser utilizado.