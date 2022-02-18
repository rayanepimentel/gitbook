# Float ou Int

### Quando usar float ou int ?

Exemplo: Temos um programa que pergunta a idade da pessoa\


```javascript
let age = "Informe a sua idade, por favor?"; //18
console.log(age) // "18"
```

Se não colocarmos o **parseInt** ou **parseFloat,** será retornado uma string.\
Como precisamos que _**age**_ seja um **number**, precisamos passar uns dos dois(int/float), nesse caso queremos a idade fechada, sem os meses.\
Ou seja, será **int**.

```javascript
let age = parseInt("Informe a sua idade, por favor?"); //18.6
console.log(age) // 18
```

Agora digamos que estamos em uma loja e precisamos saber o valor de um produto.\


```javascript
let price = "Olá, quanto custa esse chocolate? "; // 4.50
```

Como o **preço pode ter decimais**, nesse caso usariamos o **float**.

Para converter a variável para tipo number float, utilizamos o **parseFloat()**;

```javascript
let price = parseFloat("Olá, quanto custa esse chocolate? "); //4.50
console.log(price) //4.50
```

Mais exemplos:

![](../.gitbook/assets/numeros-int-float.png)

### Resumo

| Number    | Exemplo             | Converter       | Exemplo                                            |
| --------- | ------------------- | --------------- | -------------------------------------------------- |
| **Int**   | let num = **13**    | **parsInt()**   | let idade = **parseInt**("Informe a sua idade");   |
| **Float** | let num = **10.11** | **parsFloat()** | let idade = **parseFloat**("Informe a sua idade"); |

