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
