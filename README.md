# Git
Projeto de testes para aprendizado GIT. 

### Neste arquivo é apresentado os principais comandos git,sua descrição, opções e exemplos.  

#### Comandos Git básicos:
```shell
$ git init
$ git clone <link_projeto>
$ git remote add origin <link_projeto>
$ git status
$ git pull origin <nome_branch>
$ git add .
$ git commit -m 'comentário'
$ git push origin <nome_branch>
```

---

#### Init
O comando init permite inicializar um repositório GIT para novo projeto ou um projeto existente.

**Observação:** deve ser executado na pasta do projeto.

```shell
$ git init
```

---

#### Clone
O clone permite fazer uma cópia de um projeto de um repositório GIT existente para o sistema local.

```shell
$ git clone <url_projeto>
```

---

#### Status
O comando status exibe todos os arquivos que estão em um estado diferente ao da branch. 

```shell
$ git status
```

---

#### Add
O comando add permite adicionar um ou mais arquivos para a área de preparação, necessário para realizar commits e stashs, por exemplo.

**Observação:** é possível add um único arquivo através de seu nome, adicionar todos arquivos alterados utilizando '.', adicionar todos arquivos de uma pasta, entre outras variações.   

```shell
$ git add <nome_arquivo>
$ git add <.>
$ git add </pasta>
```

---

#### Commit
O comando commit permite tornar permanentes um conjunto de alterações.

**Exemplo:** O dev realizou as alterações que precisava em um determinado arquivo. Para finalizar essa alteração, informando o sistema que aquilo é uma alteração permanente, deve-se realizar o commit.

>**[-m]** faz um comando rápido já com o comentário da(s) alteração(ões).

```shell
$ git commit -m 'breve descrição da alteração realizada' 
```

---

#### Remote
O comando remote permite conectar o repositório local ao repositório remoto (servidor)
   
```shell
$ git remote add <nome_variável> <url_remoto>
$ git remote add origin https://github.com/Paulorpc/Git.git 
```

---

#### Log
O comando log exibe o log de alterações da branch atual (selecionada).
     
```shell
$ git log
```

---

#### Utilizando credenciais
O uso das credenciais facilitam o envios para o repositório sem necesidade de digitar usuário e senha. No entanto, estes dados ficam armazenados em arquivo. 

**Observação:** Recomenda-se o uso do protocolo SSH através de chaves criptografadas. 

```shell
$ git config --global credential.helper 'store'
```

---

#### Branch
O comando branch permite realizar uma série de tarefas com as branchs, como: criar, remover, listar, etc.

**Observação:** o comando git branch (sem comandos opcionais) lista as branchs locais. A branch selecionada sempre fica em destaque.

>**[-a]** lista todas as branchs (locais e remotas).  
**[-r]** lista todas as branchs remotas.  
**[nova_branch]** cria uma nova branch.

```shell
$ git branch
```

---

#### Checkout
O comando checkout permite inicializar em uma brach já existente ou criar e selecionar (inicializar) uma nova branch. 

**Exemplo:** Trocar da branch develop para uma branch feature.

>**[-b]** cria uma nova branch e faz o checkout nela.
 
```shell
$ git checkout [-b] <nome_branch>
```

---

#### Merge
O comando merge combina (faz a "junção") de duas branchs. 

**Exemplo:** O dev trabalhou numa nova feature e quer atualizar a branch develop com as mudanças dessa feature.

**Observação:** Antes é necessário fazer checkout na branch que receberá as modificações, ou seja, que será atualizada.   

```shell
$ git checkout <nome_branch>
$ git merge <feature/nova_funcao>
```

---

#### Rebase
O comando rebase atualiza a branch atual com as modificações mergeadas na branch de origem, mantendo as alterações do histórico corretas. 

**Exemplo:** O dev1 e dev2 criaram novas branchs a partir da branch develop, respectivamente a branch_A e branch_B. O dev1 finalizou seu trabalho e fez o merge na branch develop, enquanto o dev2 seguiu trabalhando na branch_B. Quando o dev2 for fazer o merge na develop, poderá acontecer um conflito, pois a branch develop pode ter alterações nos mesmos arquivos que o dev2 estava trabalhando (um exemplo). Neste caso, a melhor solução é utiliza o rebase da branch develop na branch_B, para que a branch_B volte a estar igual a develop, permitindo que o dev2 resolva os possíveis conflitos existentes. Esse mesmo procedimento poderia ser feito com merges, porém o histórico não fica correto.

**Observação:** para fazer o rebase, deve-se estar na branch que será atualizada.    

```shell
$ git checkout <branch_feature>
$ git rebase <branch_origem>
```

---

#### Reset
O comando reset permite reverter as mudanças realizadas numa branch, eliminando determinados commits.    

**Observações:** 
- Comando bastante útil, mas deve ser usado com cautela, pois após subir para o repositório remoto (ex: github), não tem como restaurar. Apesar de desfazer alguns commits desejados, não é apagado as alterações dos arquivos locais ao qual foi realizado o pull. Portanto, é possível fazer um novo commit se preciso.
- Talvez seja necessário fazer um push forçado, pois o repositório remoto poderá estar apontando pra um commit posterior ao seu atual e irá solicitar um pull, o que não seria o desejado neste caso.

>**[HEAD]** permite voltar n commits atrás.
   
```shell
$ git reset <hash_destino> 
$ git push -f 
```
ou

```shell
$ git reset HEAD~3
$ git push -f
```

---

#### Stash/Pop
O comando stash permite criar uma pilha com cópias do seu código para uso futuro. No momento em que é aplicado o stash, é salvo o estado atual da branch numa pilha de "backups" e volta a branch para o estado inicial do último commit. 

**Observação:** necessário fazer o add antes de adicionar um novo estado para a pilha.

>**[pop]** restaura o último stash adicionado na pilha.  
**[list]** lista todos os stashs aplicados.         

```shell
$ git add .
$ git stash

$ git stash list
$ git stash pop
```
