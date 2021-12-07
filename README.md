# Les étapes pour mettre en place un site web sur GitHub avec Git

#### Le site web de ce repo est disponible à l'adresse : https://dtresiea.hd.free.fr/ (il est pour le moment hors ligne)
#### La vidéo YouTube pour mettre en place ce tuto : https://www.youtube.com/watch?v=4o9qzbssfII&t=981s


## Initialiser git à la racine d’un projet
        $ git init

## S’identifier avec son compte git (GitHub)
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

## Naviguer et développer dans la branche créée
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
        $ git add .
        $ git commit -m 'initial commit into github repo'
        $ git push -u origin master

## Ajouter un README.md
        $ touch README.md
        $ git add README.md
        $ git commit -m ‘add README.md’
        $ git push
        
## Mettre à son espace de travail local
        $ git status
### Ne trouvera rien de nouveau
        $ git fetch
### Demande à git de chercher les modifications
        $ git status
### Les modifications seront visibles
        $ git pull
### L'espace de travail local est mis à jour
