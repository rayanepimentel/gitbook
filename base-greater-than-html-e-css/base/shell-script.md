# Shell Script

## 1. **Argumentos:**

Shell scripts podem receber argumentos na linha de comando. Esses argumentos são acessados usando `$1`, `$2`, `$3`, ..., `$9`, `${10}`, `${11}`, etc. `$0` representa o nome do script.

#### Variáveis Especiais de Argumentos:

* **`$0`**: Nome do script.
* **`$1`**, **`$2`**, ...: Primeiro, segundo, terceiro argumento, e assim por diante.
* **`${10}`**, **`${11}`**, ...: Argumentos além do nono (devem ser acessados com chaves **`{ }`**).
* **`$@`**: Todos os argumentos como itens separados (preserva espaços e aspas).
* **`$*`**: Todos os argumentos como uma única string.
* **`$#`**: Número total de argumentos fornecidos.

**Exemplos:**

```bash
#!/bin/bash

echo "Nome do script: $0"
echo "Primeiro argumento: $1"
echo "Segundo argumento: $2"
echo "Todos os argumentos: $@"
echo "Todos os argumentos: $*"
echo "Número de argumentos: $#"

# Exemplo com mais de 9 argumentos
echo "Décimo argumento: ${10}"
```

**Execução e Saída:**

Argumento será: **lista de compras arroz feijao leite macarrao carne ovos "azeite e creme de leite" fim**

```shell
$ ./meu_script.sh  lista de compras arroz feijao leite macarrao carne 
ovos "azeite e creme de leite" fim

// saída

Nome do script: ./meu_script.sh
Primeiro argumento: lista
Segundo argumento: de
Todos os argumentos: lista de compras arroz feijao leite macarrao carne ovos azeite e 
                     creme de leite fim

Todos os argumentos: lista de compras arroz feijao leite macarrao carne ovos azeite e 
                     creme de leite fim
Número de argumentos: 11
Décimo argumento: "azeite e creme de leite"
```

## 2. **Condicionais (`if`, `elif`, `else`):**

A estrutura condicional `if` permite executar blocos de código com base em uma **condição**.

#### **Estrutura Básica:**

```bash
if [ condição ]; then
  # Bloco executado se a condição for verdadeira
elif [ outra_condição ]; then
  # Bloco executado se a outra condição for verdadeira
else
  # Bloco executado se nenhuma condição for verdadeira
fi
```

**Exemplo: Verificar Idade**

```bash
#!/bin/bash

idade=$1

if [ "$idade" -ge 18 ]; then
  echo "Você pode tirar habilitação."
elif [ "$idade" -lt 0 ]; then
    echo "Idade inválida."
else
  echo "Você não pode tirar habilitação."
fi
```

**Operadores Relacionais:**

* `-eq`: Igual.
* `-ne`: Diferente.
* `-gt`: Maior que.
* `-lt`: Menor que.
* `-ge`: Maior ou igual que.
* `-le`: Menor ou igual que.

**Testando se um argumento foi fornecido:**

Para verificar se um argumento foi fornecido, use `-z` (string vazia) ou `-n` (string não vazia):

```bash
#!/bin/bash

idade=$1

if [ -z "$idade" ]; then
  echo "Você precisa fornecer a sua idade como argumento."
  exit 1
fi

if [ "$idade" -ge 18 ]; then
  echo "Você pode tirar habilitação."
else
  echo "Você não pode tirar habilitação."
fi
```

Ou

```bash
#!/bin/bash

idade=$1

if [ -z "$idade" ]; then
  echo "Você precisa fornecer a sua idade como argumento."
  exit 1
elif [ "$idade" -lt 0 ]; then
  echo "Idade inválida."
elif [ "$idade" -ge 18 ]; then
  echo "Você pode tirar habilitação."
else
  echo "Você não pode tirar habilitação."
fi

```

## 3. **Loops (`for`):**

#### **Estrutura Básica do `for` Loop:**

```bash
for variável in lista; do
  # Bloco de comandos para cada item da lista
done
```

Imagine que você tem uma lista de compras com vários itens, como **"Arroz", "Feijão", "Leite" e "Pão"**. Você vai ao supermercado e pega um item da lista por vez, riscando cada um após colocá-lo no carrinho. Quando todos os itens da lista estão riscados, suas compras estão completas!

A lista:

```
Arroz
Feijão
Leite
Pão
```

Vamos passar no argumento a lista e vamos imprimir cada um dos itens. Já sabemos como pegar todos argumento, utilizando $@

```bash
#!/bin/bash

lista=$@

# Lista de compras
for item in $lista; do
  echo "Pegando $item no supermercado"
done
```

1. **Iteração 1**:
   * `item = "arroz"`.
   * Executa: `echo "Pegando arroz no supermercado."`.
2. **Iteração 2**:
   * `item = "feijao"`.
   * Executa: `echo "Pegando feijao no supermercado."`.
3. **Iteração 3**:
   * `item = "leite"`.
   * Executa: `echo "Pegando leite no supermercado."`.
4. **Fim**:
   * Não há mais itens. O loop termina.

**Fluxograma básico:**

```sh
[Início do Loop]
      ↓
[Obter o próximo item da lista]
      ↓
[Executar o bloco para o item atual]
      ↓
[Ainda existem itens?] --> Sim → Retornar ao início do Loop
                          Não → [Terminar o Loop]
```

Saída:

```bash
$ ./compras.sh arroz feijao leite 

Pegando arroz no supermercado
Pegando feijao no supermercado
Pegando leite no supermercado
```

**Iterações com Saída Visual**

1.  **Input no script**:

    ```bash
    $ ./script.sh arroz feijao leite 
    ```
2.  **Saída esperada**:

    ```bash
    Pegando arroz no supermercado.
    Pegando feijao no supermercado.
    Pegando leite no supermercado.
    ```
3.  **Forma Visual (Iterações)**:

    ```bash
    Iteração 1: item = "arroz".
    Comando executado: echo "Pegando arroz no supermercado."

    Iteração 2: item = "feijao".
    Comando executado: echo "Pegando feijao no supermercado."

    Iteração 3: item = "leite".
    Comando executado: echo "Pegando leite no supermercado."

    Loop concluído.
    ```

**Mais  exemplo:**

```bash
#!/bin/bash

# Usando $@ para iterar sobre os argumentos
for item in "$@"; do  # As aspas são importantes aqui!
  echo "Pegando $item no supermercado."
done

# Exemplo com uma lista fixa
frutas="maçã banana laranja"
for fruta in $frutas; do
  echo "Comendo uma $fruta."
done

# Iterando sobre um range numérico
for i in {1..5}; do
    echo "Número: $i"
done
```

**Explicação detalhada do `for in do done`:**

* `for variável in lista`: Inicia o loop. A variável (`item`, `fruta`, `i` nos exemplos) assume o valor de cada elemento da `lista` a cada iteração.
* `do`: Marca o início do bloco de código a ser executado para cada iteração.
* `comandos`: Os comandos dentro do bloco `do...done` são executados para cada elemento da lista.
* `done`: Marca o fim do bloco de código do loop.

**Exemplo com saída:**

```bash
$ ./compras.sh arroz feijao leite "ovo de páscoa"
Pegando arroz no supermercado.
Pegando feijao no supermercado.
Pegando leite no supermercado.
Pegando ovo de páscoa no supermercado.
Comendo uma maçã.
Comendo uma banana.
Comendo uma laranja.
Número: 1
Número: 2
Número: 3
Número: 4
Número: 5
```

## 4. **Diferença Entre `$@` e `$*`**

* **`$@`:** Preserva cada argumento como um item separado, mesmo se contiver espaços ou aspas.
* **`$*`:** Trata todos os argumentos como uma única string, o que pode ser problemático para argumentos com espaços.

#### **Exemplo Prático:**

```bash
#!/bin/bash

echo "Usando \$@:"
for arg in "$@"; do
  echo "Argumento: $arg"
done

echo -e "\nUsando \$*:"
for arg in "$*"; do
  echo "Argumento: $arg"
done
```

**Execução e Saída:**

```bash
$ ./meu_script.sh "item 1" item2 "item 3"
```

**Saída:**

```makefile
Usando $@:
Argumento: item 1
Argumento: item2
Argumento: item 3

Usando $*:
Argumento: item 1 item2 item 3
```



