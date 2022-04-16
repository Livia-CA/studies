# Funções :computer: :books: 



### Objetivos :checkered_flag:

- Mostrar como declarar funções 
- Como manipular parâmetros
- Apresentar loops e outras declarações
- Apresentar o argumento "*this*"



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