# Les étapes pour mettre en place un site web sur GitHub avec Git

#### Le site web de ce repo est disponible à l'adresse : https://dtresiea.hd.free.fr/ (il est pour le moment hors ligne)
#### Liens
- https://www.youtube.com/watch?v=4o9qzbssfII&t=981s
- https://www.journaldunet.fr/web-tech/developpement/1202943-effacer-une-branche-git-a-la-fois-locale-et-distante/

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

## Ignorer certains fichiers
        $ touch .gitignore <fichier>
        $ touch .gitignore <dossier>/

## Commit les fichiers ajoutés
        $ git commit

## Changer l’éditeur 
        $ export GIT_EDITOR=vim (ou l’éditeur de votre choix)

## Effectuer un commit sans ouvrir vim  (+ push)
        $ git commit -m 'add first line in css file'
        $ git push

## "Remiser" les modifications faites dans un fichier depuis le dernier commit
        $ git checkout -- index.html

## Revenir au commit précédent (en créant une copie de l'avancée actuelle si nécessaire)
        $ git commit -m "saves current state, need debug"
        $ git push
        $ git checkout 0d1d7fc32        (l'id des commits s'obtient avec la commande git log)
        
## Travailler avec les branches git
        $ git branch JSfile             (créé la branche JSfile)
        $ git branch --list             (permet aussi de savoir dans laquelle on est)
        $ git checkout JSfile           (copie de travail devient JSfile)
        $ touch main.js                 (création d'un fichier dans JSfile)
        $ git add main.js               (ajoute le nouveau fichier au prochain commit)       
        $ git commit -m ‘add js’        (commit le fichier)
        $ git push                      (pousse la modif dans la nouvelle branche)
        $ git checkout master           (retour dans la branche master, pas de fichier js...)
        $ git merge JSfile              (merge la branche créée vers la branche master)

## Supprimer une branche
        $ git branch test
        $ git branch -d test (suppression locale)
        $ git push origin --delete test (suppression sur le dépôt distant)
        $ git fetch --all -prune (à executer sur un autre PC pour propager le changement sur ce dernier)

## Ajouter son travail sur GitHub (créer au préalable un repository)
        $ git remote add origin https://github.com/RaphyStark/dtresiea-web-site.git
        $ git add .
        $ git commit -m 'initial commit into github repo'
        $ git push -u origin master

## Renommer la branche en main (master : reference à l'esclavagisme)
        $ git branch -m master main
        $ git push -u origin main
        $ git remote set-head origin main

## Ajouter un README.md
        $ touch README.md
        $ git add README.md
        $ git commit -m ‘add README.md’
        $ git push
        
## Mettre à jour son espace de travail local
        $ git status
### Ne trouvera rien de nouveau
        $ git fetch
### Demande à git de chercher les modifications
        $ git status
### Les modifications seront visibles
        $ git pull
### L'espace de travail local est mis à jour
