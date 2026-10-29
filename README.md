# Carnet de gares

Un petit jeu pour découvrir les trains de France, de 1950 à aujourd'hui. Pour les enfants de 5 à 10 ans, à faire seul ou avec un parent.

- **Explorer** : 19 vrais trains rangés par époque. Chaque train a sa fiche, son style (couleurs, lettres, formes) et sa photo ; certains ont une vidéo.
- **Jeux** : *Tape et roule* (taper le nom du train pour le faire avancer sur la carte) et, au hasard, un deuxième jeu parmi *Mémo des trains*, *Quelle heure ?*, *Aiguillage* et *Plus ou moins* (deviner la vitesse ou le nombre de places d'un train). Réussir l'un des deux débloque le train suivant.
- **Progression** : un seul train est ouvert au début. Sur la fiche d'un train, la vitesse ou le nombre de places reste caché (« ? ») tant que *Plus ou moins* n'est pas réussi. Le bouton « Recommencer le jeu » est dans *Mon album*. La progression est gardée dans le navigateur (`localStorage`).
- **Vidéos** : quelques clips libres (dans `videos/`) et des vidéos YouTube, chargées seulement quand on clique dessus.
- **Liens directs** : `#/` accueil, `#/epoques`, `#/album`, `#/train/duplex`, `#/jeu/tape/duplex`, `#/jeu/memo/duplex`, `#/jeu/heure/duplex`, `#/jeu/rail/duplex`, `#/jeu/speed/duplex`, `#/jeu/cap/duplex`. Un jeu ou un train encore verrouillé renvoie vers la fiche du train. Le bouton « Retour » du navigateur marche.
- **Mode test** : ajoute `?debug` à l'adresse (par exemple `index.html?debug#/album`) pour tout débloquer et voir tous les jeux sur chaque fiche. Le mode test n'est pas mémorisé : enlève `?debug` de l'adresse (ou clique sur « Quitter ») pour revenir au jeu normal.

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
- **Les jeux** : une fonction par jeu (`memo`, `heure`, `rail`, `speed`, et le voyage `journey`). Le deuxième jeu proposé est tiré au hasard dans `randOther`. Les vidéos YouTube sont dans le tableau `YT`.
- **Ajouter un train** : copie une entrée de `TRAINS`, mets sa photo dans `photos/` (nom = valeur de `img`), et ajoute son auteur et sa licence dans `CREDITS.md`.

## Licences

Les vidéos YouTube restent la propriété de leurs auteurs : elles sont intégrées avec le lecteur de YouTube, jamais copiées. Elles ont été choisies d'après leur titre, sans être toutes regardées : vérifie-les avant de publier. Les photos et vidéos libres ont chacune leur licence : voir [CREDITS.md](CREDITS.md). Pense à choisir une licence pour le code (par exemple MIT) et à ajouter un fichier `LICENSE`.
