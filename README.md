# Carnet de gares

Un petit jeu pour découvrir les trains de France, de 1950 à aujourd'hui. Pour les enfants de 5 à 10 ans, à faire seul ou avec un parent.

- **Explorer** : 19 vrais trains rangés par époque. Chaque train a sa fiche, son style (couleurs, lettres, formes) et sa photo ; certains ont une vidéo.
- **Jeux** : *Tape et roule* (taper le nom du train pour le faire avancer sur la carte), *Plus ou moins*, *Mémo des trains*, *Quelle heure ?*, *Aiguillage*, *Le bon train*. Chaque train propose *Tape et roule* et un deuxième jeu.
- **Progression** : un seul train est ouvert au début. Finir un voyage avec *Tape et roule* débloque le train suivant. Le bouton « Recommencer le jeu » est dans *Mon album*. La progression est gardée dans le navigateur (`localStorage`).

## Lancer en local

Aucune installation. Ouvre `index.html` dans un navigateur, ou lance un petit serveur :

```bash
python3 -m http.server 8000
```

Puis va sur http://localhost:8000.

## Publier avec GitHub Pages

1. Mets ce dossier dans un dépôt GitHub (la branche `main`).
2. Sur GitHub : **Settings → Pages → Build and deploy → Deploy from a branch → `main` / `/ (root)`**.
3. Le site sera sur `https://<ton-compte>.github.io/<nom-du-depot>/`.

Tout le site tient dans des fichiers statiques : `index.html` (la page, le style et le code), `photos/` et `videos/`. Il n'y a rien à construire.

## Où modifier quoi

Tout est dans `index.html`.

- **Les trains** : le tableau `TRAINS` (nom, mot à taper, époque, couleurs et formes de la page, chiffres, texte, photo, vidéo éventuelle). L'ordre du tableau est l'ordre de déblocage.
- **Les époques** : `ERAS`.
- **La carte et les lignes** : `CITY` et `EDGES`. Les lignes à grande vitesse (`L`) comptent comme plus rapides que les lignes classiques (`C`), donc Lyon–Bordeaux passe par Paris.
- **Les jeux** : une fonction par jeu (`memo`, `heure`, `rail`, `bon`, `speed`, et le voyage `journey`). Le deuxième jeu proposé par chaque train est choisi dans `otherGame`.
- **Ajouter un train** : copie une entrée de `TRAINS`, mets sa photo dans `photos/` (nom = valeur de `img`), et ajoute son auteur et sa licence dans `CREDITS.md`.

## Licences

Les photos et vidéos ont chacune leur licence : voir [CREDITS.md](CREDITS.md). Pense à choisir une licence pour le code (par exemple MIT) et à ajouter un fichier `LICENSE`.
