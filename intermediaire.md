# [Git](https://git-scm.com/)

* **_Forker le projet [`formation_git`](https://github.com/iOiurson/formation-git)_**
* **_Cloner le projet sur votre machine_**


## Lier des branches

Pour ne plus avoir à écrire `git push nom_remote nom_branche`.

```bash
git branch -u nom_remote/nom_branche # lie la branche locale à la branche remote
git checkout --track nom_remote/nom_branche # crée une branche locale liée à une branche remote
git push -u nom_remote nom_branche # si la branche remote n'existe pas, push la branche locale, crée la remote et lie les branches
```

* **_Créer une branche `mamie` sur votre projet local_**
* **_Modifier `mamie.md`_**
* **_Pousser cette branche sur votre repo distant en liant la branche_**


## Pull Request

Sert à proposer du code, et faire des revues de code.

**_Faire une PR sur le projet_**

## Merge

Fusionne une branche sur une autre.
En cas de conflit, crée un commit spécial.

Sur les PRs, il y a (presque) toujours un commit créé.


## Revert

Permet annule un commit en ajoutant un commit-miroir à l'historique.

On peut également annuler **tous** les commits liés à un commit de merge en revert le commit de merge.

```
git revert monSha
```


## La vérité sur `git pull` (et `fetch`)

Pour récupérer le travail des autres, il est souvent nécessaire de `git pull`.

`git pull` en réalité c'est `git fetch` + `git merge`.


## Rebase

`git rebase maBranche` réécrit l'historique des commits de `maBranche` un par un, en vérifiant les conflits à chaque étape.

Bien penser à utiliser `git rebase --continue` pour passer au commit suivant.

ATTENTION : surtout ne pas `git commit ...` au milieu d'un rebase.


```bash
git rebase maBranche
git rebase maBranche -i # mode interactif

git pull remote maBranche --rebase # pull et rebase à la place de merge
```

`git pull --rebase` en réalité c'est `git fetch` + `git rebase`.


## Le bon workflow pour récupérer le travail des autres

```bash
git checkout develop
git pull
git checkout maBranche
git rebase develop
```


**_Mettre à jour vos branches pour pouvoir merge_**


## Branches `master` et `develop`

Les branches `master` et `develop` sont par convention des branches réservées.
Elles doivent être **protégées**.

`master` pour la production.

`develop` pour le dévelopement.

Toujours envoyer le nouveau code via PR sur `develop`.

Une fois que les tests sont validés, `develop` est mergée sur `master`.

## Bonus: `.gitignore`
