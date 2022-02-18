# Operadores Lógicos



O javascript suporta 3 operadores lógicos, que são aplicadas ao valores booleanos.\
São: `&&` `||` `!` ou AND, OR ou NOT (e, ou, não)\


### And - &&

Operado **&&** o valor é true, se ambos os dados passado para ele forem true;

Exemplo:&#x20;

Abrimos as inscrições para participar de curso X. E temos alguns critérios: para participar é preciso ter 18 anos ou mais e(&&) morar em SP.

```javascript
se idade >= 18 && cidade == "São Paulo"
  retorna "Maravilha, você pode participar";
Senão
  retorna "Infelizmente você não tem todos os critérios :(";
```

Digamos que Ana, tem 20 anos e mora em São Paulo, nesse caso o retorno será: Maravilha, você pode participar.\
Já que Ana possui os dois critérios.

| Idade                                  | Cidade                                 | Idade && Cidade                                   |
| -------------------------------------- | -------------------------------------- | ------------------------------------------------- |
| <mark style="color:green;">true</mark> | <mark style="color:green;">true</mark> | <mark style="background-color:green;">true</mark> |
| <mark style="color:green;">true</mark> | <mark style="color:red;">false</mark>  | <mark style="background-color:red;">false</mark>  |
| <mark style="color:red;">false</mark>  | <mark style="color:green;">true</mark> | <mark style="background-color:red;">false</mark>  |
| <mark style="color:red;">false</mark>  | <mark style="color:red;">false</mark>  | <mark style="background-color:red;">false</mark>  |

Ou seja, para poder se candidatar ao nosso curso é preciso que a **idade** e a **cidade** sejam `true`

### OR - ||

Operado **OR** o valor é true, se uns dos dados fornecido for true;

Utilizando o mesmo exemplo para participar do curso Y precisa ter 18 anos ou mais ou(||) morar em São Paulo.

```javascript
se idade >= 18 || cidade == "São Paulo"
  retorna "Maravilha, você pode participar";
Senão
  retorna "Infelizmente você não tem todos os critérios :(";
```

Nossa outra candidata, Teresa tem 35 anos e mora em São Luiz do Maranhão.\
Nesse caso o retorno será true, já que ela tem uns dos critérios (+18 anos).

| Idade                                  | Cidade                                 | Idade && Cidade                                   |
| -------------------------------------- | -------------------------------------- | ------------------------------------------------- |
| <mark style="color:green;">true</mark> | <mark style="color:green;">true</mark> | <mark style="background-color:green;">true</mark> |
| <mark style="color:green;">true</mark> | <mark style="color:red;">false</mark>  | <mark style="background-color:green;">true</mark> |
| <mark style="color:red;">false</mark>  | <mark style="color:green;">true</mark> | <mark style="background-color:green;">true</mark> |
| <mark style="color:red;">false</mark>  | <mark style="color:red;">false</mark>  | <mark style="background-color:red;">false</mark>  |

Ou seja, para poder se candidatar ao nosso curso é preciso que a **idade** ou **cidade** seja `true`

### NOT - !

Operador **!** inverte o valor.

!true retorna false e !false retorna true.

```javascript
let tempo = "calor"
let tempoAgora = "calor";
let comparando = tempo == tempoAgora;
console.log(comparando); // true
console.log(!comparando); // false
```

| Tempo                                  | !Tempo                                            |
| -------------------------------------- | ------------------------------------------------- |
| <mark style="color:green;">true</mark> | <mark style="background-color:red;">false</mark>  |
| <mark style="color:red;">false</mark>  | <mark style="background-color:green;">true</mark> |

