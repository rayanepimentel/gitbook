# Tipos de dados

* _**string** é_ uma sequência de zero ou mais caracteres escritos entre aspas simples `' '` ou dupla `" "`

```
let issoAquiE = "Uma string";

let issoAquiTambem = "13";
```

* _**number**_ variável tipada com número e sem "aspas".

```
let idade = 13;
let pesoDaBanana = 1.250
```

Em javascript _number_ pode ser inteiro `int` ou flutuante `float`.

```
let idade = 13; //int
let pesoDaBanana = 1.250 //float
```

* _**booleans**_ retorna se o valor é verdadeiro `true` ou falso `false`. Exemplo:

```
let valorUm = 10
let valorDois = 9

let maiorOuMenor = valorUm > valorDois 

console.log(maiorOuMenor)//true

let valorIgual = valorDois == 20

console.log(valorIgual)//false
```

* _**undefined**_ é quando declaramos uma variável sem valor.

```
let myStr;

console.log(typeof(myStr));//undefined
```

* _**array**_ com array podemos armazenar vários valores em uma única variável, como se fosse uma lista, ao invés de declarar item por item, você declara todos em uma única variável.

```
let semana = ["Domingo", "Segunda", "Terça", "Quarta", "Quinta", "Sexta", "Sábado"];
```

* _**object**_ é uma associação de propriedades com nome (chave) e valor. Exemplo. quando declaramos um carro ou uma pessoa.

```
const person = {firstName: "Olivia", lastName: "Benson", age:57};

//chave seria firstName, lastName e age
//valor seria: "Olivia", "Benson" e 57

const car = {type:"Fiat", model:"500", color:"white"};
```

Para saber o tipo da variável, utilizamos o operador **typeof**

```
let tipo = "o tipo é";
typeof tipo
//'string'
```

{% hint style="info" %}
Não se preocupe, este primeiro momento pode ser que fique confuso, mas depois abordaremos mais sobre os tipos de dados e como podemos trabalhar com eles.
{% endhint %}

