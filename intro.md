# [Git](https://git-scm.com/)

Outil de versioning créé par Linus Thorvald en 2005.

Sert à
* versioner
* collaborer
* documenter


**_Installer [git](https://git-scm.com/downloads)_**

**_Configurer la base de git_**

```bash
git config --global user.name "Blou blou"
git config --global user.email "bloublou@blou.blou"
```

**_Créer un dossier quelque part sur votre machine_**

## Commandes de bases

```bash
git init # initialise un projet git dans un dossier existant

git add # met des modifs en staging mode
git commit # enregistre les modifs en staging mode
git commit --amend # modifie le commit précédent

git status # affiche l'état du projet

git reset # enleve les modifs qui sont en staging mode
git reset --hard HEAD # annule toutes les modifs non commitées

git log # affiche l'historique des commits
```

## S'organiser

Chaque nouvelle avancée majeure doit faire l'objet d'une **branche**.

```bash
git branch # liste les branches
git branch maBranche # crée une branche
git branch -M ancienNom nouveauNom # renomme une branche
git branch -D maBranche # supprime la branche

git merge maBranche # fusionne maBranche sur la branche courante

git checkout maBranche # change de branche
git checkout -b maNouvelleBranche # crée et change de branche
```

## Github
Plateforme de partage de code, comme [Gitlab](https://gitlab.com/) ou [Bitbucket](https://bitbucket.org/)

Pas nécessaire pour travailler avec git.

**_Créer un profil sur [Github](https://github.com/)_**

**_Forker le projet `formation-git` depuis le repo [iOiurson](https://github.com/iOiurson/formation-git)_**


## Communiquer avec un repo distant

```bash
git clone adresse_du_projet.git # clone un projet

git remote -v # liste les repos distants
git remote add/remove/rename -v # manipule les repos distants

git push nom_remote nom_branche # envoie la branche sur le repo
git push -f ... # force le push quand l'historique est différent

git pull nom_remote nom_branche # récupère la branche depuis le repo
```

## Aller plus loin

### `fetch`

Récupère les infos de branche remote.

```bash
git fetch nom_remote # récupère tout le remote

git branch -a # affiche toutes les branches
```

### Lier des branches

Pour ne plus avoir à écrire `git push nom_remote nom_branche`.

```bash
git branch -u nom_remote/nom_branche # lie la branche locale à la branche remote
git checkout --track nom_remote/nom_branche # crée une branche locale liée à une branche remote
git push -u nom_remote nom_branche # si la branche remote n'existe pas, push la branche locale, crée la remote et lie les branches
```


### Fichiers cachés

```bash
.git
.gitconfig # peut être global ou local
.gitignore # peut être global ou local
.gitkeep
```

## [Authentification SSH](https://help.github.com/articles/connecting-to-github-with-ssh/)

Permet de ne pas taper son mot de passe Github/Gitlab/... à chaque push.


## [Les clients GUI](https://git-scm.com/downloads/guis)

Dangereux quand on ne sait pas ce qu'on fait, car il y a beaucoup de "magie".

