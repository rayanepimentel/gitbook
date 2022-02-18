# If else

Definição Developer Mozila:

> "A condicional if é uma estrutura condicional que executa a afirmação, dentro do bloco, se determinada condição for verdadeira. Se for falsa, executa as afirmações dentro de else."\
>

Sintaxe

```javascript
if (condição) afirmação1 [else afirmação2]
```

Exemplo:

```javascript
let tempoFrio = true;

if(tempoFrio == true) {
 return "Preciso de casaco";
}else{
 return "Preciso de roupas leves";
}
// o retorno será "Preciso de casaco", mas se o tempoFrio for false, o retorno será "preciso de roupas leves"
```

Agora vamos fazer o exemplo do curso que utilizmos lá em `"Booleano > Operadores lógicos`"\
Temos outra canditada, a Helena que tem 30 anos e mora em Salvador.\
Lembrando que para participar do curso precisa ter >= 18 **ou** morar em São Paulo.\


```javascript
if(idade >= 18 || cidade == "São Paulo"){
  return "Maravilha, você pode participar";
}else{
  return "Infelizmente você não tem todos os critérios :(";
}
//"Maravilha, você pode participar"
```

### If / else / if

É quando temos mais de duas condições:

```javascript
let horario = "manhã"

for(horario == "manhã") {
  return "Bom dia"
}else if(horario == "tarde") {
  return "Boa tarde"
}else{
  return "Boa noite"
}
```

### Com operadores lógicos

Usando o exemplo do curso.

> Abrimos as inscrições para participar de curso X. E temos alguns critérios: para participar é preciso ter 18 anos ou mais e(&&) morar em SP.

```javascript
if(idade >= 18 && cidade == "São Paulo"){
  retorna "Maravilha, você pode participar";
}else{
  retorna "Infelizmente você não tem todos os critérios :(";
}
```

Com mais de uma condição:

Digamos que temos um restaurante que dás 08h até 12h só é servido café da manhã, a tarde até 17h é servido café da tarde e almoço e se tiver chovendo(tempo frio) teremos sopa, depois 18h somente pizza.

```javascript
let horario = 16;
let tempo = "frio";

if (horario >= 8 && horario <= 12) {
    return "Café da manhã";
} else if (horario <= 17 && tempo == "frio") {
    return "Almoço, café da tarde e sopa";
} else if (horario <= 17) {
    return "Almoço e café da tarde";
} else {
    return "Pizza";
}
```
