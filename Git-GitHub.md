GIT / GITHUB


TERMINAL 1: INSTALAÇÃO DO GIT
rafa@rcb-lm20:~$ sudo add-apt-repostitory ppa:git-core/ppa
rafa@rcb-lm20:~$ sudo apt update
rafa@rcb-lm20:~$ sudo apt install git
	





TERMINAL 2: CHAVE SSH
rafa@rcb-lm20:~$ ssh-keygen -t ed25519 -C acb.economist@gmail.com
Generating public/private ed25519 key pair.
Enter file in which to save the key (/home/rafa/.ssh/id_ed25519): 
Created directory '/home/rafa/.ssh'.
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in /home/rafa/.ssh/id_ed25519
Your public key has been saved in /home/rafa/.ssh/id_ed25519.pub
The key fingerprint is:
SHA256:vDd2ijZ5Ano/RdWyHYkgYH+xo6AoYR5P5frTJuY+qpI acb.economist@gmail.com
The key's randomart image is:






rafa@rcb-lm20:~$ cd /
rafa@rcb-lm20:/$ cd home
rafa@rcb-lm20:/home$ cd rafa
rafa@rcb-lm20:~$ cd .ssh
rafa@rcb-lm20:~/.ssh$ ls
id_ed25519  id_ed25519.pub
rafa@rcb-lm20:~/.ssh$ cat id_ed25519.pub
ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAICNPXzKj25EJIqQTFlFyGqPjGfvtvvK71Fqtf0W/j5Ig acb.economist@gmail.com
rafa@rcb-lm20:~/.ssh$ ls
id_ed25519  id_ed25519.pub
rafa@rcb-lm20:~/.ssh$ pwd
/home/rafa/.ssh
rafa@rcb-lm20:~/.ssh$ eval $(ssh-agent -s)
Agent pid 3161
rafa@rcb-lm20:~/.ssh$ ssh-add id_ed25519
Enter passphrase for id_ed25519: 
Identity added: id_ed25519 (acb.economist@gmail.com)
	

TERMINAL 3: VALIDAR CHAVE SSH
rafa@rcb-lm20:/workspace/ssh-test$ sudo git clone git@github.com:cb-aline/senha.git
Cloning into 'senha'...
git@github.com: Permission denied (publickey).
fatal: Could not read from remote repository.


Please make sure you have the correct access rights
and the repository exists.




	

TERMINAL 4: CRIANDO COMMIT 
rafa@rcb-lm20:~$ cd /
rafa@rcb-lm20:/$ cd workspace/
rafa@rcb-lm20:/workspace$ cd livro-receitas/
rafa@rcb-lm20:/workspace/livro-receitas$ git init
/workspace/livro-receitas/.git: Permissão negada
rafa@rcb-lm20:/workspace/livro-receitas$ sudo git init
[sudo] senha para rafa:         
Repositório vazio Git inicializado em  /workspace/livro-receitas/.git/
rafa@rcb-lm20:/workspace/livro-receitas$ ls
rafa@rcb-lm20:/workspace/livro-receitas$ ls -a
.  ..  .git
rafa@rcb-lm20:/workspace/livro-receitas$ cd .git
rafa@rcb-lm20:/workspace/livro-receitas/.git$ 
rafa@rcb-lm20:/workspace/livro-receitas/.git$ 






rafa@rcb-lm20:/workspace/livro-receitas/.git$ cd ..
rafa@rcb-lm20:/workspace/livro-receitas$ git config --global user.email "acb.economist@gmail.com"
rafa@rcb-lm20:/workspace/livro-receitas$ git config --global user.name cb-aline


(arquivo md criado na pasta)


rafa@rcb-lm20:/workspace/livro-receitas$ git add *
fatal: unsafe repository ('/workspace/livro-receitas' is owned by someone else)
To add an exception for this directory, call:


        git config --global --add safe.directory /workspace/livro-receitas


rafa@rcb-lm20:/workspace/livro-receitas$ sudo git add *
rafa@rcb-lm20:/workspace/livro-receitas$ git commit -m "commit inicial"
fatal: unsafe repository ('/workspace/livro-receitas' is owned by someone else)
To add an exception for this directory, call:


        git config --global --add safe.directory /workspace/livro-receitas


rafa@rcb-lm20:/workspace/livro-receitas$ sudo git commit -m "commit inicial"
[master (root-commit) 464be70] commit inicial
 1 file changed, 10 insertions(+)
 create mode 100644 strogonoff.md
rafa@rcb-lm20:/workspace/livro-receitas$ 




rafa@rcb-lm20:/workspace/livro-receitas$ ls
strogonoff.md
rafa@rcb-lm20:/workspace/livro-receitas$ sudo git status
No ramo master
nothing to commit, working tree clean
rafa@rcb-lm20:/workspace/livro-receitas$ sudo mkdir receitas
rafa@rcb-lm20:/workspace/livro-receitas$ ls
receitas  strogonoff.md




rafa@rcb-lm20:/workspace/livro-receitas$ sudo mv strogonoff.md ./receitas/
rafa@rcb-lm20:/workspace/livro-receitas$ ls
receitas
rafa@rcb-lm20:/workspace/livro-receitas$ cd receitas
rafa@rcb-lm20:/workspace/livro-receitas/receitas$ ls
strogonoff.md
rafa@rcb-lm20:/workspace/livro-receitas/receitas$  




rafa@rcb-lm20:/workspace/livro-receitas/receitas$ sudo git status
No ramo master
Changes not staged for commit:
  (utilize "git add/rm <arquivo>..." para atualizar o que será submetido)
  (use "git restore <file>..." to discard changes in working directory)
        deleted:    ../strogonoff.md


Arquivos não monitorados:
  (utilize "git add <arquivo>..." para incluir o que será submetido)
        ./


nenhuma modificação adicionada à submissão (utilize "git add" e/ou "git commit -a")


rafa@rcb-lm20:/workspace/livro-receitas/receitas$ cd ..
rafa@rcb-lm20:/workspace/livro-receitas$ sudo git status
No ramo master
Changes not staged for commit:
  (utilize "git add/rm <arquivo>..." para atualizar o que será submetido)
  (use "git restore <file>..." to discard changes in working directory)
        deleted:    strogonoff.md


Arquivos não monitorados:
  (utilize "git add <arquivo>..." para incluir o que será submetido)
        receitas/


nenhuma modificação adicionada à submissão (utilize "git add" e/ou "git commit -a")








rafa@rcb-lm20:/workspace/livro-receitas$ sudo git add strogonoff.md receitas
rafa@rcb-lm20:/workspace/livro-receitas$ sudo git status
No ramo master
Mudanças a serem submetidas:
  (use "git restore --staged <file>..." to unstage)
        renamed:    strogonoff.md -> receitas/strogonoff.md


rafa@rcb-lm20:/workspace/livro-receitas$ sudo git commit -m "cria pasta receitas, move arquivo para receitas"
[master 8e93512] cria pasta receitas, move arquivo para receitas
 1 file changed, 0 insertions(+), 0 deletions(-)
 rename strogonoff.md => receitas/strogonoff.md (100%)
rafa@rcb-lm20:/workspace/livro-receitas$ sudo git status
No ramo master
nothing to commit, working tree clean






rafa@rcb-lm20:/workspace/livro-receitas$ ls
receitas
rafa@rcb-lm20:/workspace/livro-receitas$ sudo su
root@rcb-lm20:/workspace/livro-receitas# echo > README.md
root@rcb-lm20:/workspace/livro-receitas# ls
README.md  receitas
root@rcb-lm20:/workspace/livro-receitas# git status
No ramo master
Arquivos não monitorados:
  (utilize "git add <arquivo>..." para incluir o que será submetido)
        README.md


nada adicionado ao envio mas arquivos não registrados estão presentes (use "git add" to registrar)












root@rcb-lm20:/workspace/livro-receitas# git status
No ramo master
Arquivos não monitorados:
  (utilize "git add <arquivo>..." para incluir o que será submetido)
        README.md


nada adicionado ao envio mas arquivos não registrados estão presentes (use "git add" to registrar)
root@rcb-lm20:/workspace/livro-receitas# git add * 
root@rcb-lm20:/workspace/livro-receitas# ls
README.md  receitas
root@rcb-lm20:/workspace/livro-receitas# git status
No ramo master
Mudanças a serem submetidas:
  (use "git restore --staged <file>..." to unstage)
        new file:   README.md


root@rcb-lm20:/workspace/livro-receitas# git commit -m "adiciona index"
[master 65f043b] adiciona index
 1 file changed, 7 insertions(+)
 create mode 100644 README.md
root@rcb-lm20:/workspace/livro-receitas# 


	

TERMINAL 5: CRIANDO REPOSITÓRIO NO GIT (SITE) E ASSOCIANDO COM O LOCAL
rafa@rcb-lm20:~$ cd /workspace/livro-receitas
rafa@rcb-lm20:/workspace/livro-receitas$ git config --list
user.email=acb.economist@gmail.com
user.name=cb-aline
rafa@rcb-lm20:/workspace/livro-receitas$ ls
README.md  receitas
rafa@rcb-lm20:/workspace/livro-receitas$ sudo gitrrrrrrrrafa@rcb-lm20:/workspace/livro-receitas$ sudo git remote add oringin https://github.com/cb-aline/livro-receitas.git
[sudo] senha para rafa:         
rafa@rcb-lm20:/workspace/livro-receitas$ sudo git remote -v
oringin        https://github.com/cb-aline/livro-receitas.git (fetch)
oringin        https://github.com/cb-aline/livro-receitas.git (push)




rafa@rcb-lm20:/workspace/livro-receitas$ sudo git status
rafa@rcb-lm20:/workspace/livro-receitas$ sudo git push oringin master
[sudo] senha para rafa:         
Username for 'https://github.com': cb-aline
Password for 'https://cb-aline@github.com': TOKEN
Enumerating objects: 8, done.
Counting objects: 100% (8/8), done.
Delta compression using up to 2 threads
Compressing objects: 100% (6/6), done.
Writing objects: 100% (8/8), 828 bytes | 165.00 KiB/s, done.
Total 8 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/cb-aline/livro-receitas.git
 * [new branch]      master -> master


	



TERMINAL 6: RESOLVENDO PROBLEMA
Caso: Edição no arquivo local README.md, que também sofreu mudança no repositório remoto (outra pessoa)




rafa@rcb-lm20:~$ cd /workspace/livro-receitas/
rafa@rcb-lm20:/workspace/livro-receitas$ ls
README.md  receitas
rafa@rcb-lm20:/workspace/livro-receitas$ sudo git status
[sudo] senha para rafa:         
No ramo master
Changes not staged for commit:
  (utilize "git add <arquivo>..." para atualizar o que será submetido)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md


nenhuma modificação adicionada à submissão (utilize "git add" e/ou "git commit -a")
rafa@rcb-lm20:/workspace/livro-receitas$ sudo git add*
git: 'add*' não é um comando git. Veja 'git --help'.


The most similar command is
        add
rafa@rcb-lm20:/workspace/livro-receitas$ sudo git add *
rafa@rcb-lm20:/workspace/livro-receitas$ ls
README.md  receitas
rafa@rcb-lm20:/workspace/livro-receitas$ sudo git status
No ramo master
Mudanças a serem submetidas:
  (use "git restore --staged <file>..." to unstage)
        modified:   README.md


rafa@rcb-lm20:/workspace/livro-receitas$ 
rafa@rcb-lm20:/workspace/livro-receitas$ sudo git commit -m "adiciona receita pave"
[master a5c19cd] adiciona receita pave
 1 file changed, 2 insertions(+)
rafa@rcb-lm20:/workspace/livro-receitas$ sudo git push oringin master
Username for 'https://github.com': cb-aline
Password for 'https://cb-aline@github.com': 


ERRO


rafa@rcb-lm20:/workspace/livro-receitas$ sudo git pull oringin master


CONFLITO


(Edita o o arquivo para concertar o erro)


rafa@rcb-lm20:/workspace/livro-receitas$ sudo git status
rafa@rcb-lm20:/workspace/livro-receitas$ sudo git add *
rafa@rcb-lm20:/workspace/livro-receitas$ sudo git commit -m “corrigido”
rafa@rcb-lm20:/workspace/livro-receitas$ sudo git push oringin master


	



TERMINAL 7: CLONAR CÓDIGO DO GIT DE OUTRA PESSOA 
rafa@rcb-lm20:~$ cd /workspace/
rafa@rcb-lm20:/workspace$ ls
livro-receitas  ssh-test
rafa@rcb-lm20:/workspace$ sudo git clone https://github.com/Perkles/perkles.git
[sudo] senha para rafa:         
Cloning into 'perkles'...
remote: Enumerating objects: 48, done.
remote: Counting objects: 100% (48/48), done.
remote: Compressing objects: 100% (31/31), done.
remote: Total 48 (delta 13), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (48/48), 11.01 KiB | 1.38 MiB/s, done.
Resolving deltas: 100% (13/13), done.
rafa@rcb-lm20:/workspace$ ls
livro-receitas  perkles  ssh-test
rafa@rcb-lm20:/workspace$ cd perkles
rafa@rcb-lm20:/workspace/perkles$ ls -a
.  ..  .git  README.md
rafa@rcb-lm20:/workspace/perkles$ sudo git remote -v
origin        https://github.com/Perkles/perkles.git (fetch)
origin        https://github.com/Perkles/perkles.git (push)