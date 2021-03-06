# Outros métodos

### sort()

O método `sort()` ordena os elementos do próprio array e retorna o array.

```javascript
let frutas = ["Banana", "Uva", "Caju", "Abacaxi", "Abacate"];
let ordenacao = frutas.sort();
console.log(ordenacao);
//[ "Abacate", "Abacaxi", "Banana", "Caju", "Uva" ]
```

\-> O sort() diferencia maiúscula e minúscula.

```javascript
let frutas = ["banana", "Uva", "Caju", "abacaxi", "Abacate"];
let ordenacao = frutas.sort()
console.log(ordenacao)
//[ "Abacate", "Caju", "Uva", "abacaxi", "banana" ]
```

Primeiro ordenação maiúscula e depois ordenação minúscula.

### map()

Utilizamos `map()`para percorrer array e para fazer alguma alteração.

```javascript
let frutas = ["banana", "uva", "caju", "abacaxi", "abacate"];
let quantidade = frutas.map(qntFruta => `Quantidade: duas frutas de ${qntFruta}`);

console.log(quantidade);
//[ 
    "Quantidade: duas frutas de banana",
    "Quantidade: duas frutas de uva", 
    "Quantidade: duas frutas de caju", 
    "Quantidade: duas frutas de abacaxi", 
    "Quantidade: duas frutas de abacate" 
    ]
```

### filter()

`filter()` cria uma nova array com elementos que se enquadram em um determinado critério a partir de uma array existente.

Exemplo, quero que retorne todas as frutas que começam **\[0]** com a letra **A**.

```javascript
let frutas = ["Banana", "Uva", "Caju", "Abacaxi", "Abacate"];
let filtrar = frutas.filter(fruta => fruta[0] === "A");
console.log(filtrar);
//[ "Abacate", "Abacaxi" ]
```

### join()

O `join()`permite concatenar todos os elementos de uma array e retorna uma string.

```javascript
let frutas = ["Banana", "Uva", "Caju", "Abacaxi", "Abacate"];

let exemploEspaco = frutas.join(" ");
console.log(exemploEspaco);
//Banana Uva Caju Abacaxi Abacate

let exemploBarra = frutas.join("/");
console.log(exemploBarra);
//Banana/Uva/Caju/Abacaxi/Abacate

let exemploVirgula = frutas.join(",");
console.log(exemploVirgula);
//Banana,Uva,Caju,Abacaxi,Abacate

let exemploVirgulaEspaco = frutas.join(", ");
console.log(exemploVirgulaEspaco);
//Banana, Uva, Caju, Abacaxi, Abacate
```
