---
title: Unitat 1 - Eines de programació
titlepage: true
subtitle: Xuso Ortí Monton
lang: es
toc-own-page: true
toc-title: Continguts
titlepage-rule-height: 0
titlepage-text-color: "7421D6"
titlepage-background: "./img/portadaparcial.png"
page-background: "./img/bkaztar.png"
header-left: \includegraphics{./img/logocap.png} Unitat 1 - Eines de programació
header-right: Curs 2022-2023
footer-left: IES Jaume II el Just - Desenvolupament Web en Entorn Client
footer-right: \thepage/\pageref{LastPage}
header-includes:
    - \usepackage{graphicx}
    - \usepackage{lastpage}
    - \usepackage{xltxtra}
    - \usepackage{listings}
    - \usepackage{pdflscape}
    - \usepackage{caption}
...

# 1 Introducció

Les pricipals eines que anem a utilitzar durant el curs van a ser:

- **Visual Studio Code** com a entorn de desenvolupament.
- **GitHub** com a repositori dels nostres programes.

Es recomana utilitzar **Ubuntu** o qualsevol altra distro de **Linux** com a sistema operatiu.

# 2 Instal·lació de Visual Studio Code

En [aquest enllaç](https://ubunlog.com/visual-studio-code-editor-codigo-abierto-ubuntu-20-04/) podeu consultar com fer el procés tant com a paquet `snap` o com a `deb`.

# 3 Compte d'usuari a GitHub

Caldrà que et dones d'alta a **GitHub** i crees un repositori per a utilitzar durant el curs. Ha de ser públic, per tant no publiques informació o dades sensibles al repositori.

Consulta [ací](https://docs.github.com/es/repositories/creating-and-managing-repositories/creating-a-new-repository) com fer un repositori.

# 4 Git

## 4.1 Instal·lació
Per a insta·lar Git en el teu ordinador amb **Ubuntu** pots fer ús de la terminal.

```bash
$ sudo apt-get update
$ sudo apt-get install git
```
Comprova que està correctament instal·lat amb

```bash
xus@angliru:~$ git version
git version 2.34.1
```

## 4.2 Iniciar Git a un directori

Comandament: `git init`

```bash
xus@angliru:~$ mkdir prova_git
xus@angliru:~$ cd prova_git/
xus@angliru:~/prova_git$ git init
hint: Using 'master' as the name for the initial branch. This default branch name
hint: is subject to change. To configure the initial branch name to use in all
hint: of your new repositories, which will suppress this warning, call:
hint: 
hint: 	git config --global init.defaultBranch <name>
hint: 
hint: Names commonly chosen instead of 'master' are 'main', 'trunk' and
hint: 'development'. The just-created branch can be renamed via this command:
hint: 
hint: 	git branch -m <name>
Initialized empty Git repository in /home/xus/prova_git/.git/
```

Comprova que ha creat un subdirectori ocult `.git`

```bash
xus@angliru:~/prova_git$ ll
total 12
drwxrwxr-x  3 xus xus 4096 de set.  15 09:05 ./
drwxr-x--- 23 xus xus 4096 de set.  15 09:05 ../
drwxrwxr-x  7 xus xus 4096 de set.  15 09:05 .git/
```

Podem indentificar-nos amb el nostre nom i correu.

```bash
xus@angliru:~/Documents/IES_El_Just_2022_2023/apunts_markdown$ git config --global user.email "jorti@ieseljust.com"
xus@angliru:~/Documents/IES_El_Just_2022_2023/apunts_markdown$ git config --global user.name "Xuso"
```

## 4.3 Unir repositori local i remot

Hem de tindre la `url` del nostre repositori a GitHub

```bash
xus@angliru:~/prova_git$ git remote add origin https://github.com/xusodocent/apunts_dwec.git
```

## 4.4 Afegir arxius

Quan treballem en local, podem vore els arxius que està controlant `Git` amb `git status`. Si no heu afegit cap arxiu `git` informa de que hi ha arxius que no està controlant. En el cas següent una carpeta anomenada `T1`.

```bash
xus@angliru:~/Documents/IES_El_Just_2022_2023/apunts_markdown$ git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	T1/

nothing added to commit but untracked files present (use "git add" to track)
```

Afegim tots els arxius amb `git add . ` i tornem a comprovar l'estat.

```bash
xus@angliru:~/Documents/IES_El_Just_2022_2023/apunts_markdown$ git add .
xus@angliru:~/Documents/IES_El_Just_2022_2023/apunts_markdown$ git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
	new file:   T1/Tema1.html
	new file:   T1/Tema1.md
	new file:   T1/Tema1.pdf
	new file:   T1/eisvogel.latex
	new file:   T1/img/bkaztar.png
	new file:   T1/img/bkaztar.xcf
	new file:   T1/img/bkmo.png
	new file:   T1/img/bkmotar.png
	new file:   T1/img/logocap.png
	new file:   T1/img/portadaparcial.png

```

Vegem que s'han afegit correctament.

## 4.5 El commit

El `commit` serveix per a guardar els canvis fets als arxius del nostre projecte afegint un missatge.

> L'opció `-m` indica que s'utilitzarà un missatge o comentari

```bash
xus@angliru:~/Documents/IES_El_Just_2022_2023/apunts_markdown$ git commit -m "Fem el primer commit"
[master (root-commit) b7d39d6] Fem el primer commit
 10 files changed, 1185 insertions(+)
 create mode 100644 T1/Tema1.html
 create mode 100644 T1/Tema1.md
 create mode 100644 T1/Tema1.pdf
 create mode 100644 T1/eisvogel.latex
 create mode 100644 T1/img/bkaztar.png
 create mode 100644 T1/img/bkaztar.xcf
 create mode 100644 T1/img/bkmo.png
 create mode 100644 T1/img/bkmotar.png
 create mode 100644 T1/img/logocap.png
 create mode 100644 T1/img/portadaparcial.png
```

Tens una explicació més detallada al següent [enllaç](https://www.freecodecamp.org/espanol/news/el-comando-git-commit-explicado/).

## 4.6 Pujar arxius a repositori remot

El comandament per a pujar arxius des del nostre repositori local a `Github` és `git push`.

> Recorda que cal utilitzar el token de Github

```bash
xus@angliru:~/Documents/IES_El_Just_2022_2023/apunts_markdown$ git push origin master
Username for 'https://github.com': jorti@ieseljust.com
Password for 'https://jorti@ieseljust.com@github.com': 
Enumerating objects: 14, done.
Counting objects: 100% (14/14), done.
Delta compression using up to 4 threads
Compressing objects: 100% (13/13), done.
Writing objects: 100% (14/14), 440.53 KiB | 15.73 MiB/s, done.
Total 14 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/xusodocent/apunts_dwec.git
 * [new branch]      master -> master
```
## 4.7 Actualitzar des del repositori remot.

Pot donar-se el cas que participes a un projecte amb més programadors i tots contribui pujant arxius a un mateix repositori remot. Per tal d'actualitzar el teu repositori local des del remot cal fer `git pull`. 

> Tal vegada necessites especificar repositori i branca.

```bash
xus@angliru:~/Documents/IES_El_Just_2022_2023/apunts_markdown$ git pull origin master
From https://github.com/xusodocent/apunts_dwec
 * branch            master     -> FETCH_HEAD
Already up to date.
```

[Ací](https://www.freecodecamp.org/espanol/news/el-comando-git-commit-explicado/) tens una explicació més detallada.


