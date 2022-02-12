# Tipo string

String uma sequência de zero ou mais caracteres escritos entre aspas.

```js
let mensagem = "Olá mundo!";
```

Pode ser entre aspas simples 'Oi' ou duplas "Oi".

```
let mensagem = 'Olá mundo!';
```

{% hint style="info" %}
Importante: Se por exemplo na nossa string tenha uma palavra que use **'**, como **I'm** devemos usar aspas duplas.
{% endhint %}

```
let exemplo = 'I'm'; // erro
let outroExemplo = "I'm"; // sem erro
```

### Concatenação

Basicamente "colocar junto", é unir duas strings.

```
let name = "Teresa";
let message = "Oi, " + name + "! Tudo bem?";
//Oi, Teresa! Tudo bem?
```

`"mensagem"`` `**`+`**` ``variavel`

Existe outra maneira além do **+,** template string.

```
let name = "Teresa";
let message = `Oi ${name}! Tudo bem?`;
//Oi, Teresa! Tudo bem?
```

Toda a frase precisa estar entre **` `` `** e a variável dentro **`${}`**.

`` `mensagem ${variavel}` ``

Eu particularmente gosto mais de usar template string.
