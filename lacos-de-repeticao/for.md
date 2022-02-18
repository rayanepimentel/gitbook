# For

Laço de repetição **for**, funciona quando precisamos executar algo mais de uma vez.

Sintaxe

```javascript
for ([inicialização]; [condição]; [expressão final])
   declaração
```

Exemplo:

Digamos que precisamos andar 3 passos para chegarmos na praia.

```javascript
let passo;
for(passo = 1; passo <= 3; passo++){
  console.log("Dei "+ passo + "passos");
}
console.log("Chegamos!!!");
```

* passo = 1 é o passo inicial
* e iriá repetir a mensagem até passo <=3, é a nossa condição
* passo++ é aumentada cada vez que o código é executado

![](<../.gitbook/assets/image (7) (1).png>)



Agora vamos imprimir os números de 5 - 10

```javascript
for (let i = 5; i <= 10; i++) {
    console.log(i);
}
```

Como precisamos imprimir de 5 - 10, o `let i` tem que ser `igual a 5` e a nossa condição `<= 10`

``![](<../.gitbook/assets/image (7).png>)``
