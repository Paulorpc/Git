# Git
Projeto de testes para aprendizado GIT. 

## Comandos GIT mais utilizados

> Comandos Git básicos:
```
git remote add origin [linkProjeto]
git status
git pull origin [branch]
git add .
git commit -m 'comentário do commit'
git push origin [branch]
```


> #### Clone
O clone permite fazer uam cópia do projeto GIT para o sistema local. 
```
git clone https://github.com/Paulorpc/Git
```


> #### Utilizando credenciais
O uso das credenciais facilitam o envios para o repositório sem necesidade de digitar usuário/senha. Os dados ficam armazenados em arquivo no disco. Portanto para uma opção mais segura, utilizar o SSH. 
```
git config --global credential.helper 'store'
```

> #### Branch
O comando branch permite realizar uma séri de tarefas com as branchs, como: criar, remover, listar, etc.
- Listar as branchs locais (A branch selecionada fica em destaque)
- -a para listar todas branchs locais e remotas
- -r para listar todas branchs remotas
```
git branch 
```


> #### Checkout
O comando checkout permite inicializar em uma brach qualquer. Por exemplo: Trocar entre branch master e develop. Ou caso um desenvolvedor inicie uma branch para trabalho e em seguida você precisa dar continuidade na branch dele.
- -b cria uma nova branch e faz o checkout nela. 
```
git checkout [-b] [branch]
```

> #### Merge
O comando merge faz a "junção" de duas branchs. Por exemplo: O dev trabalhou numa nova feature e quer atualizar a branch master com as mudanças dessa feature.
- Antes é necessário fazer checkout na branch que receberá as modificações, ou seja, que será atualizada.
- Depois é preciso fazer o envio para o repositório remoto.   
```
git checkout master
git merge feature/nova_funcao
git push
```


branch A
