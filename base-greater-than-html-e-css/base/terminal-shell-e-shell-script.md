# Terminal, Shell e Shell Script

## **1. O que é o Terminal?**

Imagine o seu computador como um prédio com muitos departamentos (programas). A interface gráfica (janelas, ícones, menus) é como o hall de entrada, bonito e fácil de usar para visitantes. O Terminal, por outro lado, é como a porta dos fundos, um acesso direto para os "bastidores" do sistema. Ele permite interagir com o computador através de comandos de texto.

* **Windows:** O Terminal é conhecido como "Prompt de Comando" (cmd.exe) ou "PowerShell".
* **macOS:** O Terminal é um aplicativo chamado "Terminal".

**Como abrir o Terminal:**

* **Windows:**
  * **Prompt de Comando:** Pesquise por "cmd" no menu Iniciar e execute "Prompt de Comando".
  * **PowerShell:** Pesquise por "PowerShell" no menu Iniciar e execute "Windows PowerShell".
* **macOS:** Command + a tecla espaço e digite "terminal".

## 2. **O que é o Shell?**



O Shell é o "tradutor" entre você e o sistema operacional. Quando você digita um comando no Terminal, o Shell interpreta esse comando e o envia para o sistema executar. Ele também exibe o resultado da execução para você.

Pense no Shell como um intérprete em uma reunião entre pessoas que falam idiomas diferentes. Você fala com o intérprete (Shell) em sua língua (comandos), ele traduz para a língua do outro (sistema operacional) e vice-versa.

Existem diferentes tipos de Shell, como `bash` (o mais comum em macOS e Linux), `zsh`, `ksh`, `csh` e o `cmd.exe` e PowerShell no Windows.

Imagine que seu computador é um prédio com muitos apartamentos (pastas). Você já está dentro do prédio (logado no computador). Para visitar um apartamento específico (uma pasta, como "Documentos"), você precisa se deslocar até ele.

Na interface gráfica (com janelas e ícones), você usaria o explorador de arquivos (Finder no macOS ou Explorador de Arquivos no Windows) e clicaria na pasta "Documentos". No terminal com o shell, você usa o comando `cd` (change directory), que significa "mudar de diretório".

Pense no `cd` como entrar no elevador e apertar o botão do andar correspondente ao apartamento (pasta) que você quer visitar.

Exemplo:

```sh
$ cd Documentos 
```

Ou, de forma mais completa e robusta (independente do idioma do sistema):

<pre class="language-bash"><code class="lang-bash"><strong>$ cd ~/Documentos
</strong></code></pre>

**Explicação:**

* `cd`: Comando para mudar de diretório.
* `Documentos` ou `~/Documentos`: Caminho para a pasta "Documentos". O `~` representa o diretório home do usuário.

## 3. **Como instalar o Git Bash no Windows:**



{% hint style="info" %}
Para unificar o ambiente de desenvolvimento, a partir de agora, utilizaremos o Git Bash no Windows. Isso significa que os mesmos comandos usados no macOS (e Linux) serão usados também no Windows, através do Git Bash.
{% endhint %}

**Como instalar o Git Bash no Windows:**

O Git Bash é um emulador de terminal Unix que vem junto com a instalação do Git para Windows. Ele fornece um ambiente Bash completo, com os comandos Unix/Linux que usaremos.

1. **Baixe o Git para Windows:** Acesse o site oficial do Git: [https://git-scm.com/download/win](https://www.google.com/url?sa=E\&source=gmail\&q=https://git-scm.com/download/win) e baixe o instalador.
2. **Execute o instalador:** Abra o arquivo baixado e siga as instruções.
3. **Conclua a instalação:** Após a instalação, você encontrará o "Git Bash" no menu Iniciar.

**Usando o Git Bash:**

Após a instalação, abra o Git Bash. Você verá um terminal com um prompt semelhante a este:

Bash

```bash
user@PC MINGW64 ~
$
```

A partir de agora, todos os exemplos e exercícios usarão comandos Unix/Linux, como:

* `ls`: Listar arquivos e diretórios.
* `cd`: Navegar entre diretórios.
* `mkdir`: Criar um diretório.
* `cp`: Copiar arquivos.
* `rm`: Remover arquivos.
* `pwd`: Mostrar o diretório atual.

## 4. **O que é um Shell Script?**



Um Shell Script é um arquivo de texto que contém uma sequência de comandos que seriam digitados no Terminal. É como uma "receita" ou um "programa" que automatiza tarefas.

Imagine que você precisa realizar uma série de ações repetidamente, como copiar arquivos de uma pasta para outra, renomear vários arquivos, etc. Em vez de digitar cada comando individualmente no Terminal toda vez, você pode escrever um Shell Script com esses comandos e executá-lo com um único comando.

**Analogia com uma receita de bolo:**

* **Terminal:** A cozinha.
* **Shell:** O cozinheiro.
* **Shell Script:** A receita do bolo (lista de ingredientes e instruções).

Voltando à analogia do prédio, imagine que você precisa executar uma sequência de ações todos os dias: sair do térreo, pegar o elevador até o 13º andar, entrar no seu apartamento e verificar um recado na geladeira.

No contexto do computador, imagine que você precisa realizar as seguintes ações diariamente: acessar a pasta "Documentos", navegar até a pasta "tarefas" e ler o conteúdo do arquivo "tarefasDeHoje.txt". Para exibir o conteúdo de um arquivo, usamos o comando `cat`.

**Executando os comandos manualmente no terminal:**

Se você fosse executar essas ações manualmente no terminal todos os dias, você faria o seguinte:

```bash
# Navega até a pasta Documentos
cd Documentos

# Navega até a pasta tarefas (dentro de Documentos)
cd tarefas

# Exibe o conteúdo do arquivo tarefasDeHoje.txt
cat tarefasDeHoje.txt
```

**Automatizando com um Shell Script:**

Como você precisa executar esses comandos repetidamente, o ideal é automatizar essa tarefa com um _shell script_. Como vimos, um shell script é um arquivo de texto que contém uma sequência de comandos que o shell executa.

**Criando o Shell Script:**

1.  **Criando o arquivo:** Usaremos o comando `touch` (ou `nano`, `vi`, `vim`, ou qualquer editor de texto) para criar o arquivo do script. O nome do arquivo geralmente tem a extensão `.sh` (de "shell").

    <pre class="language-bash"><code class="lang-bash"><strong>$ touch script.sh
    </strong></code></pre>

    Ou, usando um editor de texto diretamente do terminal:

    ```sh
    $ nano script.sh  # Abre o arquivo script.sh no editor nano
    ```
2.  **Escrevendo o script:** Abra o arquivo `script.sh` com um editor de texto (como o Nano, Vim, VS Code, Bloco de Notas, etc.) e adicione as seguintes linhas:

    ```bash
    #!/bin/bash

    cd ~/Documentos/tarefas  # Caminho completo para evitar erros
    cat tarefasDeHoje.txt
    ```
3. **Explicação:**
   * `#!/bin/bash`: Esta linha, chamada de "shebang", especifica qual interpretador (shell) deve ser usado para executar o script (neste caso, o Bash). É _essencial_ para que o script funcione corretamente.
   * `cd ~/Documentos/tarefas`: Este comando navega diretamente para a pasta "tarefas" dentro de "Documentos". Usar o caminho completo (`~/Documentos/tarefas`) é mais robusto, pois funciona independentemente do diretório atual em que você está quando executa o script.
   * `cat tarefasDeHoje.txt`: Este comando exibe o conteúdo do arquivo "tarefasDeHoje.txt".
4.  **Dando permissão de execução:** Para executar o script, você precisa dar permissão de execução a ele. Use o comando `chmod +x`:



    ```bash
    chmod +x script.sh
    ```

**Executando o Shell Script:**

Agora você pode executar o script simplesmente digitando:

```sh
./script.sh
```



## 6. **Exemplos Práticos e Comandos Básicos:**



* `cd` (change directory): Navega entre pastas.
  * Exemplo: `cd Documentos` - Entra na pasta "Documentos".
  * `cd ..`  - Volta para a pasta anterior.
* `ls`: Lista os arquivos e pastas no diretório atual.
* `mkdir`: Cria uma nova pasta.
  * Exemplo: `mkdir NovaPasta`- Cria uma pasta chamada "NovaPasta".
* `echo`: Imprime um texto na tela.
  * Exemplo: `echo "Olá, mundo!"`  - Imprime "Olá, mundo!".
* `cp` (macOS): Copia arquivos.
  * Exemplo: `cp arquivo.txt destino.txt` - Copia "arquivo.txt" para "destino.txt".

**Tabela com os principais comandos**



| Categoria                                | Comando                 | Descrição                                                                                                                                                                | Exemplo                                                 | Observações                                                                                                                                   |
| ---------------------------------------- | ----------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------- |
| **Navegação**                            | `pwd`                   | Imprime o diretório de trabalho atual (mostra o caminho completo da pasta onde você está).                                                                               | `pwd`                                                   | Essencial para saber sua localização no sistema de arquivos.                                                                                  |
|                                          | `ls`                    | Lista os arquivos e diretórios no diretório atual.                                                                                                                       | `ls` ou `ls -l` (lista com detalhes)                    | `ls -l` mostra informações como permissões, tamanho, data de modificação, etc. `ls -a` lista arquivos ocultos.                                |
|                                          | `cd [diretório]`        | Muda o diretório de trabalho atual para o diretório especificado.                                                                                                        | `cd Documentos`, `cd ~/Downloads`, `cd /var/log`        | Use `~` para representar seu diretório home. Caminhos absolutos começam com `/`.                                                              |
|                                          | `cd ..`                 | Navega para o diretório pai (o diretório que contém o diretório atual).                                                                                                  | `cd ..`                                                 | Equivalente a "voltar uma pasta".                                                                                                             |
|                                          | `cd ~`                  | Navega para o diretório home do usuário.                                                                                                                                 | `cd ~`                                                  | Atalho para ir diretamente para sua pasta pessoal.                                                                                            |
| **Manipulação de Arquivos e Diretórios** | `mkdir [nome]`          | Cria um novo diretório (pasta).                                                                                                                                          | `mkdir NovaPasta`                                       |                                                                                                                                               |
|                                          | `touch [nome]`          | Cria um novo arquivo vazio.                                                                                                                                              | `touch novo_arquivo.txt`                                | Útil para criar rapidamente arquivos de texto ou outros tipos de arquivos vazios.                                                             |
|                                          | `cp [origem] [destino]` | Copia um arquivo ou diretório da origem para o destino.                                                                                                                  | `cp arquivo.txt copia.txt`, `cp -r pasta1 pasta2`       | Use `-r` (recursivo) para copiar diretórios e seu conteúdo.                                                                                   |
|                                          | `mv [origem] [destino]` | Move ou renomeia um arquivo ou diretório.                                                                                                                                | `mv arquivo.txt novo_nome.txt`, `mv arquivo.txt pasta/` | Se o destino for um diretório, o arquivo é movido para dentro dele. Se o destino for um novo nome, o arquivo é renomeado.                     |
|                                          | `rm [arquivo]`          | Remove (deleta) um arquivo.                                                                                                                                              | `rm arquivo.txt`                                        | **Cuidado!** A remoção é permanente. Use com cautela.                                                                                         |
|                                          | `rmdir [diretório]`     | Remove um diretório _vazio_.                                                                                                                                             | `rmdir pasta_vazia`                                     | Só funciona se o diretório estiver vazio.                                                                                                     |
|                                          | `rm -r [diretório]`     | Remove um diretório e todo o seu conteúdo (arquivos e subdiretórios).                                                                                                    | `rm -r pasta_com_arquivos`                              | **Extremo cuidado!** A remoção é permanente e _não há como desfazer_. Use com extrema cautela.                                                |
| **Visualizar Conteúdo**                  | `cat [arquivo]`         | Exibe o conteúdo de um arquivo na tela.                                                                                                                                  | `cat arquivo.txt`                                       | Útil para arquivos pequenos. Para arquivos grandes, use `less`.                                                                               |
|                                          | `less [arquivo]`        | Exibe o conteúdo de um arquivo de forma paginada, permitindo navegar pelo conteúdo usando as setas do teclado, barra de espaço e outras teclas. Pressione `q` para sair. | `less arquivo_grande.txt`                               | Ideal para arquivos extensos.                                                                                                                 |
|                                          | `head [arquivo]`        | Mostra as primeiras linhas de um arquivo (por padrão, as 10 primeiras).                                                                                                  | `head arquivo.txt`, `head -n 20 arquivo.txt`            | `-n [número]` especifica o número de linhas a serem exibidas.                                                                                 |
|                                          | `tail [arquivo]`        | Mostra as últimas linhas de um arquivo (por padrão, as 10 últimas).                                                                                                      | `tail arquivo.txt`, `tail -f arquivo.txt`               | `-n [número]` especifica o número de linhas. `-f` (follow) monitora o arquivo em tempo real, mostrando novas linhas conforme são adicionadas. |



