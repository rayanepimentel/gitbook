# Caixas de diálogo

Em javascript temos algumas funções que podemos interagir com o usuário, `alert`, `prompt`e `confirm`.

### alert()

Mostra uma mensagem na tela em forma de pop up e espera que o usuário clique em ok.

```javascript
alert("Hello");
```

![](<../.gitbook/assets/image (12).png>)

### prompt()

Espera uma ação do usuário.&#x20;

Por exemplo, ao fazer uma pergunta esperamos que o usuário responda. E a resposta será o valor da variável.

```javascript
let age = prompt("Olá, qual é a sua idade?");
```

![](<../.gitbook/assets/image (13).png>)

No prompt também podemos passar um valor "pré-preenchido".&#x20;

```javascript
let age = prompt("Olá, qual é a sua idade?", 35);
```

![](<../.gitbook/assets/image (8).png>)

### Confirm()

Mostra uma mensagem e espera que o usuário pressione “OK” ou “Cancel”.&#x20;

O seu retorno será `true`para OK e `false`para Cancel/ Esc.

```javascript
let maiorDeIdade = confirm("Olá, você tem 18 anos ou mais? ");
```

![](<../.gitbook/assets/image (4).png>)

