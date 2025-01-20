# Permissões de arquivos

## Permissões

Comandos:

* `ls` exibi o que tem na minha pasta

<figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

* `ls -la` exibi o que tem na minha pasta inclusive arquivos ocultos.

<figure><img src="../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

Se observamos temos alguns arquivos e diretórios com letras. O que essas letras significam?

* Leitura → r - 4
* Escrita, permissão de gravação→ w - 2
* Execução → x -1

{% hint style="success" %}
&#x20;**Leitura(read)** permite ao usuário ler o conteúdo do arquivo mas não alterá-lo. \
**Escrita(write)** permite que o usuário altere o arquivo. \
**Execução(x)**, como o nome diz, permite que o usuário execute o arquivo, no caso de ser executável.
{% endhint %}

E são divididos em 3 partas:

* 1 → **proprietário**: usuário que controla o arquivo.
* 2 → **grupo**: conjunto de usuários com permissões específicas.
* 3 → **outros** usuários: usuários que não pertencem nem ao proprietário, nem ao grupo, e têm permissões restritas (ou nenhuma permissão).

Exemplo:

<figure><img src="../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

* **`-` → que dizer que é um arquivo e não um `d` diretório(pasta)**
* **`rw-` → a primeira parte significa permissões do proprietário, `leitura(r) e escrita(w)`(4,2)**
* **`r--` → a segunda parte significa permissões do grupo ao qual o usuário pertence, `leitura`(4)**
* **`r--` →a terceira parte significa permissões para os demais usuários, `leitura`(4)**

E o que seria `4 - 2 - 1` (leitura - escrita - executável) ?

Seria Octal. Octal **é um sistema de números base 8 que usa os dígitos 0 a 7.**

Veja a tabela:

| 0 | --- | nenhuma permissão           |
| - | --- | --------------------------- |
| 1 | --x | somente execução            |
| 2 | -w- | somente escrita             |
| 3 | -wx | escrita e execução          |
| 4 | r-- | somente leitura             |
| 5 | r-x | leitura e execução          |
| 6 | rw- | eitura e escrita            |
| 7 | rwx | leitura, escrita e execução |

| --------- | 000 | Nenhuma permissão                                                                              |
| --------- | --- | ---------------------------------------------------------------------------------------------- |
| r-------- | 400 | somente leitura para propriétário(4)                                                           |
| r--r--r-- | 444 | leitura para proprietário, grupo e outros usuários                                             |
| rw------- | 600 | leitura e escrita somente para proprietário(4+2 = 6)                                           |
| rw-r--r-- | 644 | leitura e escrita para proprietário(6), leitura para grupo e para outros                       |
| rw-rw-rw- | 666 | leitura e escrita para proprietário, grupo e outros.                                           |
| rwx------ | 700 | leitura, escrita e executável somente para proprietário(4+2+1=7)                               |
| rwxr-x--- | 750 | leitura, escrita e executável para proprietário(4+2+1=7), leitura e executavel para grupo(4+3) |

Fonte: [infowester](https://www.infowester.com/linuxpermissoes.php)

Exemplo, temos um arquivo **teste.txt**

<figure><img src="../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

* Proprietário(rw): leitura e escrita&#x20;
* grupo(r) e demais(r): leitura&#x20;

Vamos alterar para proprietário ser o unico que tenha leitura e escrita e grupo e os demais não terão permissão de leitura.

Para fazer isso vamos usar [**chmod**](https://rockcontent.com/br/blog/chmod/) e passar o octal para nome do arquivo, ficaria assim:

`chmod 600 teste.txt`

* proprietário: leitura(4) e escrita(2) → 4 + 2 = 6 ⇒ rw
* grupo: 0
* demais: 0

<figure><img src="../../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

Alterado com sucesso!



## Script: `configurar_permissoes.sh`

Exemplo de um script em Shell que recebe o nome do arquivo como argumento, adiciona a extensão `.txt` ao nome e depois define permissões para o proprietário, grupo e outros usuários.

```bash
#!/bin/bash

# Verificar se o argumento foi fornecido
if [ -z "$1" ]; then
  echo "Por favor, forneça o nome do arquivo como argumento."
  exit 1
fi

# Nome do arquivo (adiciona a extensão .txt)
nome_arquivo="$1.txt"

# Criar o arquivo 
touch "$nome_arquivo"

# Definir permissões para o proprietário, grupo e outros
chmod 744 "$nome_arquivo"

# Exibir o arquivo e suas permissões
echo "Arquivo criado: $nome_arquivo"
ls -l "$nome_arquivo"
```

#### Explicação:

1. O script verifica se o nome do arquivo foi passado como argumento. Se não, ele solicita o nome.
2. O nome do arquivo fornecido tem a extensão `.txt` adicionada.
3. O comando `touch` cria o arquivo (caso não exista).
4. O comando `chmod 744` define as permissões do arquivo:
   * **Proprietário**: leitura, escrita e execução (7).
   * **Grupo**: leitura (4).
   * **Outros**: leitura (4).
5. O script exibe o arquivo criado e suas permissões com o comando `ls -l`.

#### Como executar:

1.  Torne o script executável:

    ```bash
    chmod +x configurar_permissoes.sh
    ```
2.  Execute o script passando o nome do arquivo (sem a extensão):

    ```bash
    $ ./configurar_permissoes.sh meu_arquivo
    ```

#### Saída esperada:

Se o nome do arquivo passado for "meu\_arquivo", o script criará "meu\_arquivo.txt" e configurará as permissões. A saída será algo como:

```bash
Arquivo criado: meu_arquivo.txt
-rwxr--r-- 1 usuario usuario 0 jan 20 12:00 meu_arquivo.txt
```



