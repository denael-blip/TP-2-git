# TP-2-git

## Question 1 : Récupération de changements distants sans fusion automatique

### Question :
Quelle commande utiliseriez vous pour récupérer les changements distants sans les fusionner ? Montrez ensuite comment comparer écupérer les changements distants sans les fusionner avant de décider d'une fusion.

- pour récupérer les changements a distance sans les fusionner j'utilise `git fetch`

- et pour comparer ma branche local avec celle a distance j'utilise la commande `git diff main origin/main`

- Bonus

## Question 2 : Réstauration d'un fichier supprimé par erreur
Comment retrouver le commit ou le fichier existait encore ?
Quelle commande utiliserez-vous pour le restaurer sans revenir en arrière sur tout le projet ?

- pour trouver le commit ou le dossier existait : `git log -- <nom_du_fichier>`

- Restaurer le fichier sans revenir en arrière sur tout le projet :
`git checkout <commit_hash> -- <nom_du_fichier>`

## Question 3 : Travail sur plusieurs branches à la fois
Quelle commande permet de copier un commit spécifique d'une branche vers une autre ? Montrez comment identifier le bon commit hash avant de l'appliquer.

- pour copier un comic spécifique d'une branche à une autre, on utilise cette commande : `git cherry-pick <commit_hash>`
- et pour identifier le bon commîtes, on utilise : `git log <nom_de_branche>`

## Question 4 : Réécriture d'un message de commit mal rédigé
Comment modifier le message s'il s'agit :
    Du dernier commit ?
    D'un commit plus ancien dans l'historique ?
Expliquez les différences entre git commit -–amend et git rebase -i dans ce contexte .

- pour modifier le dernier comique, on utilise : `git commit --amend -m "Nouveau message"`
et pour un plus ancien, on utilise : `git rebase -i HEAD~N`

- la différence c'est que `git commit -–amend` va permettre de modifier le dernier commit uniquement alors que `git rebase -i` il pourra modifier plusieurs comiques passé

## Question 5 : Analyse de l'historique et retour en arrière sélectif
Comment identifier le commit fautif à l'aide de git bisect ?
Une fois trouvé, comment annuler uniquemant ce commit sans supprimer les autres ?

- pour trouver le commit fautif, il faut faire les commandes suivantes : 
```
git bisect start
git bisect bad
git bisect good <commit_hash_bon>
```
- pour annuler ce commit on va utiliser : `git revert <commit_hash>`

## Question 6 : Mise en pause et reprise d'un travail en cours (stash avancé)
Quelle commande stash permet d'enregistrer aussi les fichiers non suivis ?
Comment restaurer ensuite ces changements sans supprimer le stash de la pile ?

- pour enregistrer les fichiers non suivi avec stash on utilise cette commande :
 `git stash push -u`

- et pour restaurer ensuite ces changements sans supprimer : 
`git stash apply`

