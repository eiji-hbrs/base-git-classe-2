# base-git-classe-2

## Git et Github pour votre projet personnel 

Il existe principalement trois scénarios pour lancer votre environnement de travail.

### A. La méthode "Local-First" (Nouveau projet sur votre machine)

C’est la méthode classique si vous commencez à coder sur votre ordinateur avant même d’avoir créé un compte ou un dépôt en ligne.
Ouvrez votre terminal dans le dossier du projet.
Initialisez Git : 

    git init

Cela crée un dossier caché .git.


Ajoutez des fichiers.

Regardez l'état :

    git status

Ajoutez vos fichiers en staged de git : 

    git add .


Effectuez votre premier sauvegarde : 

    git commit -m "Initial commit"


Liez votre dossier local au serveur distant : 

    git remote add origin <URL_DU_DEPOT_GITHUB>


Envoyez vos fichiers : 

    git push origin main

### B. La méthode "Remote-First" (Clonage d'un dépôt vide)

C'est souvent la méthode la plus simple pour éviter les erreurs de configuration entre le local et le distant.
Créez un nouveau dépôt sur GitHub via l'interface web.
Copiez l'URL (HTTPS ou SSH).

Dans votre terminal, utilisez la commande : 

    git clone <URL_DU_DEPOT>


Un dossier est créé, déjà lié à GitHub. Vous n'avez plus qu'à coder et "pusher".

### C. Connecter un projet local existant à GitHub

Si vous avez déjà commencé à coder et initialisé Git localement, mais que vous souhaitez maintenant le sauvegarder sur GitHub :
Créez un dépôt vide sur GitHub (sans README ni licence).

Liez votre dossier local au serveur distant : 

    git remote add origin <URL_DU_DEPOT_GITHUB>


Renommez votre branche principale (souvent par défaut sur master) en main : 

    git branch -M main


Ajoutez vos fichiers à la sauvegarde 

    git add .


Sauvegardez en créant le commit : 

     git commit -m”First commit”


Envoyez vos fichiers : 

    git push -u origin main

Vous pouvez également utiliser les branches si vous voulez tester une autre version sans risquer d'écraser le projet sur la `main` (à faire depuis `main`) : 

    # crée et va sur la branche
    git checkout -b mabranche1

ou

    # crée la branche
    git branch mabranche2
    # aller sur la branche
    git switch mabranche2

Voir les branches :

    git branch


Supprimer une branche (! à éviter si possible)

    git branch -d nom_de_la_branche

Pour envoyer une branche

    pit push origin mabranche1

Pour récupérer les branches de `origin`

    git fetch --all

Vous pourrez ensuite switcher sur la branche désirée
    
  
### Les indispensables du projet personnel

Pour qu'un projet soit propre et professionnel, deux éléments sont incontournables dès le départ :


Le fichier `.gitignore` : Ce fichier liste les éléments que Git doit ignorer (dépendances lourdes comme node_modules/, fichiers de configuration sensibles comme .env, ou fichiers temporaires d'IDE).

Le fichier `README.md` : C'est la vitrine de votre projet. Il doit expliquer ce que fait le projet, comment l'installer et comment l'utiliser.

Le fichier `.gitkeep` dans un dossier permet de mettre un dossier vide sur `github`, car `git` ne suit pas les dossiers vides.

---

## Git et Github pour votre projet d'équipe

Il faut commencer en créant un `fork` du projet d'équipe

Dans votre terminal, utilisez la commande : 

    git clone <VOTRE_FORK>


Un dossier est créé, déjà lié à GitHub. Vous n'avez plus qu'à renter dedans

    cd VOTRE_FORK

### Connecter un projet fork à l'`upstream` sur GitHub

Vous avez déjà un lien vers votre `fork` :

    git remote -v

Liez votre dossier local au répertoire (repository) d'équipe et nommez le `upstream` : 

    git remote add upstream <VOTRE_EQUIPE>


**Ne travaillez jamais sur la `main`, créez des branches** : 

    git checkout -b MA_BRANCHE


Ajoutez vos fichiers à la sauvegarde 

    git add .


Sauvegardez en créant le commit : 

     git commit -m”une contribution”


Envoyez votre branch sur github (vous n'avez accès qu'à votre `fork`) : 

    git push origin MA_BRANCHE

**Soumettez un `pull request` au(x) chef(s) du projet depuis `github`**

Récupérez le travail du groupe sur la branche `main` :

    # on va sur la branche main
    git switch main
    # on récupère le travail de groupe
    git pull upstream main
    # on remet son fork à jour
    git push origin main

Recommencez ensuite les étapes en créant une branche depuis la `main` (sauf pour continuer votre travail qui ne serait pas encore fusionné avec un `merge` par le chef d'équipe)
    


