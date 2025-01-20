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





