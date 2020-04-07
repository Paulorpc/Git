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

> #### Rebase
O comando rebase atualiza a branch atual com as modificações mergeadas na branch de origem, mantendo o histórico corretamente. Por exemplo: O dev1 (branch A) e o dev2 (branch B) criaram novas branchs a partir da branch develop. O dev1 finalizou seu trbalho e fez o merge na branch develop, enquanto o dev2 seguiu trabalhando na branch B. Quando o dev2 for fazer o merge na develop, poderá acontecer um conflito, pois a branch develop pode ter alterações nos mesmos arquivos que o dev2 estava trabalhando (um exemplo). Neste caso, pode ser utilizado o rebase na branchB da branch develop, atualizando a branch develop para o estado atual e permitindo que o dev2 resolva os conflitos existentes. Esse mesmo procedimento poderia ser feito com merges, porém o histórico não fica correto.    
```
git checkout [branch feature]
git rebase [branch origem feature]
git push
```

> #### Reset
O comando reset permite reverter as mudanças realizadas numa branch.    
Obs: Comando bastante útil, mas deve ser usado com cautela, pois ele irá eliminar determinados commits e após subir para o github, não tem como restaurar. Apesar de desfazer determinados commits, ele não apaga as alterações dos arquivos ao qual fez o pull, logo é possível subir um novo commit com as alterações local.
- Talvez seja necessário fazer um push forçado, pois o github poderá estar apontando pra um commit posterior ao seu atual e irá pedir para fazer um pull.
- A opção HEAD permite voltar n commits atrás   
```
git reset [hash_destino] OU git reset HEAD~3
git push -f 
```
