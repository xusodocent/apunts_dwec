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



