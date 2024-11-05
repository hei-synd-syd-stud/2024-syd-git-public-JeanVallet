# Answers of Jean Vallet JeanVallet

## Basics

### Task 1

Après le clonage du Git Repo, dans le répertoire, on trouve:

- le fichier answer.md (le fichier pour répondre aux questions)
- un dossier img (pour des images du fichier markdown)
- un dossier .git (un répertoire caché qui contient tous les fichiers et informations nécessaires pour gérer le dépôt Git)

### Task 2

Après avoir exécuté pour la première fois la commande `git status` on peut voir en **rouge** qu'on a modifié le fichier **answers.md** et qu'on n'a pas fait de commit pour ce document. La deuxième fois, après avoir crée le fichier **README.md**, on peut voir que cette fois ci on a deux fichier qui ont été modifiés et pas commité. 

Avec la ligne de commande `git log --oneline` on visualise l'historique des commits et, vu qu'on n'en a pas fait, rien est changé.

### Task 3

Quand on exécute la commande `git add README.md`, Git ajoute le fichier `README.md` à la **staging area**, ce qui signifie que le fichier est préparé pour être inclus dans le prochain commit. On peut en effet voir que le nom du fichier devient **vert**.

### Task 4

Si on consulte à nouveau les infos de `git status` on peut voir que les changements apportés à `README.md` n'ont pas été ajouter à la **stagging area**.

### Task 5

Après avoir fait le premier commit, et avoir utilisé la commande `git log --oneline` j'obtient:

*febb11f* (**HEAD** -> **main**) *ADD: README file.*
*5da930b* (**origin/main**, **origin/HEAD**) *Initial commit*

- La chaîne de caractère `febb11f` au début est un identifiant abrégé qui est générer automatiquement par Git. Cet identifiant est appelé **hash** et il est utilisé pour référencer précisément ce commit

- **`HEAD`** est un pointeur spécial qui indique l’emplacement actuel dans l'historique de Git. Il pointe généralement vers la branche ou le commit sur lequel on travaille actuellement.

- **`main`** est le nom de la branche actuelle (la branche par défaut dans la plupart des dépôts Git). Dans ce cas, `HEAD -> main` signifie que `HEAD` pointe sur la branche `main`, qui elle-même pointe sur le commit avec le hash`febb11f`.

- Après le sparenthèses il y a `ADD: README file.`, le message du commit.

- Enfin le mot `Initial commit` indique le début de la branche ou bien le tout premier commit d'un dépôt Git

### Task 6

Quand on effectue le `git checkout <SHA1>` avec le **short hash**, Git passe en mode "détaché" (`detached HEAD`). Cela signifie que `HEAD` pointe directement sur le `initial commit`, et non sur une branche comme `main`. Git restaure les fichiers exactement tels qu'ils étaient au moment de ce commit. Ainsi, on revient au commit initial, les fichiers et dossiers ajoutés dans les commits ultérieurs disparaissent temporairement du disque dur, car Git a restauré l’état du dépôt à la date du commit initial. En effet le fichier `README.md` n'est plus présent et le fichier `answers.md` ne contient aucune reponse.
Tout les fichier et les dossier créés ne sont donc plus présents dans le disque dur du PC mais ils sont sauvé dans la **stagging area** (Le fichier `README.md` n'existe pas et le fichier `answers.md` ne contient aucune reponse). Quand on fait un `git checkout main` on revient à la dernière version et tous les fichier et éventuels dossier créés sont à nouveau disponible dans le PC. En revenant à la branche `main` avec `git checkout main`, on revient à la version la plus récente, où tous les fichiers et dossiers créés ultérieurement sont de nouveau disponibles.

## Gitgraph

### Task 7

![Gitgraph](img/gitgraph.svg)

1. `develop` est le nom qui a été donné à la branche bleu.

2. `baa6795` est le **short hash** générer automatiquement par Git pour référencer précisément ce commit.

3. `Merge branch 'feature-auth' into 'develop'` est le commentaire qui indique qu'est ce qui a été fait dans le dernier commit.

4. `ByteMe Bob <bob.byteme@hevs.ch>` indique l'indentité de l'auteru du commit

5. `v1.0.0` indique la version de la branche main où:
   
   - `1` représente la version majeure,
   
   - `0` représente la version mineure,
   
   - `0` représente le correctif ou patch.
   - `v` indique le mot "version"
6. Le dernier noeud est appelé `HEAD` et il correspond au dernier commit effectué sur la branche `develop`. Ici on a fait aussi un merge entre la branche `feature-auth` et `evelop`.
7. Le noeud indique un commit de la nouvelle branche `feature-auth` qui vient du merge entre la branche `main` et `develop`. Cette branche à été crée par `<carol.codequeen@hevs.ch` et elle possède le **short hash** `c93cfcc`.
8. Ce noeud est le dernier de la branche `main` où on effectue un merge entre cette branche et `develop`.
9. La ligne bleu indique toute la branche `develop`.
10. La ligne grise indique toute la branche `main`.