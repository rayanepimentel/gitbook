# Outros métodos

### sort()

O método sort() ordena os elementos do próprio array e retorna o array.

```
let frutas = ["Banana", "Uva", "Caju", "Abacaxi", "Abacate"];
let ordenacao = frutas.sort();
console.log(ordenacao);
//[ "Abacate", "Abacaxi", "Banana", "Caju", "Uva" ]
```

\-> O sort() diferencia maiúscula e minúscula.

```
let frutas = ["banana", "Uva", "Caju", "abacaxi", "Abacate"];
let ordenacao = frutas.sort()
console.log(ordenacao)
//[ "Abacate", "Caju", "Uva", "abacaxi", "banana" ]
```

Primeiro ordenação maiúscula e depois ordenação minúscula.

### map()

Utilizamos map() para percorrer array e para fazer alguma alteração.

```
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
