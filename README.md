# How to setup the web site using git

## Initialiser git à la racine d’un projet
        $ git init

## S’identifier avec son compte git (github)
        $ git config --global user.name ‘user_name’
        $ git config --global user.email ‘user_email’

## Indiquer à git les fichiers à sauvegarder
        $ git add index.html

## Visualiser les fichiers s'apprêtant à être commit 
        $ git status

## Désindexer certains fichiers (ou tous avec -r)  
        $ git rm --cached <fichier>

## Remettre un fichier supprimé qui a été ajouté avec git add 
        $ git checkout -- .
Le point est important  il permet de dire à git qu’on souhaite restaurer les fichiers du répertoire courant

## Commit les fichiers ajoutés 
        $ git commit

## Changer l’éditeur 
        $ export GIT_EDITOR=vim (ou l’éditeur de votre choix)

## Effectuer un commit sans ouvrir vim 
        $ git commit -m 'add first line in css file'

## Ignorer certains fichiers 
        $ touch .gitignore <fichier>
        $ touch .gitignore <dossier>/

## Créer une nouvelle branche 
        $ git branch JSfile

## Naviguer et développer dans la branche
        $ git checkout JSfile

## Savoir quelles sont les branches créées et dans laquelle on se trouve
        $ git branch --list

## Commit un fichier depuis la branche JSfile
        $ touch main.js
        $ git add .
        $ git commit -m ‘js file added’

## Retour dans la branche master
        $ git checkout master
Les fichiers ou modifications ajoutés ne sont plus visibles

## Merger la branche créée vers la branche master
        $ git merge JSfile

## Ajouter son travail sur GitHub (créer au préalable un repository)
        $ git remote add origin https://github.com/RaphyStark/dtresiea-web-site.git
        $ git branch -M main
        $ git push -u origin main

## Ajouter un README.md
        $ touch README.md
        $ git add .
        $ git commit -m ‘add README.md’
        $ git push
