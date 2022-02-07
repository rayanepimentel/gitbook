# Tipo array

Com array podemos armazenar vários valores em uma única variável, como se fosse uma lista, ao invés de declarar item por item, você declara todos em uma única variável.

```
let semana = ["Domingo", "Segunda", "Terça", "Quarta", "Quinta", "Sexta", "Sábado"];
```

O primeiro índice do array é 0, e quissessimos retornar apenas o domingo da nossa lista chamariamos a nossa variável e dentro \[], informaria o índice.&#x20;

`variavel[i]`

```
let semana = ["Domingo", "Segunda", "Terça", "Quarta", "Quinta", "Sexta", "Sábado"];
console.log(semana[0]);
```

### Adicionar um novo item

```
let frutas = ["Banana", "Uva"];
```

#### Add no final do array

Para add um novo item no final do array, utilizamos `push`

```
frutas.push("Melancia");
console.log(frutas);
//[ "Banana", "Uva", "Melancia" ]
```

#### Add no íncio do array

Para add um novo item no ínicio do array, utilizamos `unshift`

```
frutas.unshift("Manga");
console.log(frutas);
//[ "Manga", "Banana", "Uva", "Melancia" ]
```

### Removendo um item

#### Removendo no final do array

Utilizamos `pop()`

```
frutas = [ "Manga", "Banana", "Uva", "Melancia" ];
frutas.pop();
console.log(frutas);
//[ "Manga", "Banana", "Uva" ]
```

#### Removendo no íncio do array

Utilizamos `shift()`

```
frutas = [ "Manga", "Banana", "Uva" ];
frutas.shift();
console.log(frutas);
//[ "Banana", "Uva" ]
```





{% hint style="info" %}
No exemplo `que utilizamos` todos itens era uma `string`, mas você pode armazenar vários tipos em uma mesma array.\
Exemplo, uma array pode ter string, number, boolean...\


```
let sequence = [1, 1, 2, 3, 5, 8, 13];
let  random = ['tree', 795, [0, 1, 2]];
```
{% endhint %}
