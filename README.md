# 🦕 Le Parc de Diego

Jeu d'aventure sur téléphone pour le 1er anniversaire de Diego, entre amis (adultes).
4 équipes, 4 épreuves en rotation dans le jardin, puis une enquête finale pour retrouver
la nouvelle espèce échappée du parc… le **Diegosaurus Rex**.

👉 **Jeu en ligne : https://guicaron0201-hub.github.io/diegosaurus-rex/**

Tout le jeu tient dans un seul fichier, [`index.html`](index.html) : pas de serveur,
pas de compte, la progression est gardée sur chaque téléphone.

---

## L'histoire

Ornella, directrice du parc, annonce que le labo a vu naître il y a un an une espèce
toute nouvelle, encore sans nom. Cette nuit, les clôtures ont lâché et le petit s'est
échappé. Les équipes doivent réussir 4 épreuves pour rassembler 4 indices sur lui,
puis l'identifier au labo génétique.

Le nom « Diegosaurus Rex » n'apparaît qu'à la toute fin, dans la liste des suspects.

## Déroulé d'une partie (≈ 45 min)

1. **Prologue** (3 écrans), puis **choix de l'équipe**.
2. **Top départ commun** : au signal d'Ornella, les 4 équipes appuient sur « TOP » en même
   temps. Chaque téléphone calcule ensuite seul le tour en cours, ils restent synchronisés.
3. **4 tours**, chacun composé de :
   - **1 minute d'attente** : on rejoint le lieu et on lit les règles, une barre se remplit ;
   - **10 minutes d'épreuve** : l'épreuve démarre toute seule avec l'animation « CHOMP ! ».
   Entre deux épreuves, on revient au **tableau de bord « Notre parcours »**.
4. **Le labo** (sans chrono) : l'équipe compare ses 4 indices à une **liste de 5 suspects**.
5. **La révélation** : analyse ADN → radar → « On l'a retrouvé ! Il était dans la cuisine
   en train de piquer des parts de son gâteau » avec la photo de Diego, puis
   « Rejoignez le Diegosaurus Rex pour souffler sa première bougie ».

## Les 4 épreuves

| Épreuve | Lieu (réel) | Maître du jeu | Le jeu | Indice gagné |
|---|---|---|---|---|
| 🦏 Le défi d'Alain | Terrain de pétanque | Alain le Tricératops | L'équipe tire 5 boules, Alain 3. La plus proche du cochonnet gagne. Une victoire suffit. | 🍼 Un biberon |
| 🔤 Le mot secret de la Serre | Le jardin | aucun | 6 lettres cachées (à laisser en place). On les note dans l'app et on devine le mot **ÉCLORE**. | 👣 Empreinte pointure 21 |
| 🎯 L'antre du T-Rex | La forêt | Le Dresseur du T-Rex | 5 fléchettes chacun, le plus gros total gagne. Une victoire suffit. | 🌙 Le rapport secret des parents |
| 🏓 Le Dino-pong d'Ornella | Table de ping-pong | Ornella | Pong contre Ornella : un joueur qui marque sort. Le plus de verres en 10 min gagne. | 📱 Une télécommande mâchouillée |

Pour les 3 duels, l'équipe appuie sur **🏆 Gagné** ou **💀 Perdu**. Perdu → l'app affiche
le gage (chacun imite le cri d'un dinosaure), puis « Gage fait » donne quand même l'indice.

## Les 4 équipes et la rotation

| Équipe | Tour 1 | Tour 2 | Tour 3 | Tour 4 |
|---|---|---|---|---|
| 🌋 Les Volcanosaures | Pétanque | Lettres | Fléchettes | Dino-pong |
| 🌊 Les Aquaraptors | Lettres | Fléchettes | Dino-pong | Pétanque |
| 🌿 Les Jungle-Rex | Fléchettes | Dino-pong | Pétanque | Lettres |
| ⚡ Les Ptéro-Éclairs | Dino-pong | Pétanque | Lettres | Fléchettes |

À chaque tour, chaque épreuve accueille exactement une équipe.

## Tester

```bash
node serve.js
```

Puis ouvrir http://localhost:4173 (sur téléphone : l'adresse affichée dans le terminal,
même wifi).

- **Boutons de test** en bas des écrans : ⏩ saute la fin de la minute ou des 10 minutes,
  🔄 redémarre la partie.
- **`?test`** à la fin de l'adresse : partie accélérée (épreuves de 40 s, trajets de 15 s).

## Réglages (dans `index.html`)

| Constante | Rôle |
|---|---|
| `BOUTON_TEST` | `true` = boutons de test visibles. **Passer à `false` le jour J.** |
| `DUREE` | Durée d'une épreuve (10 min). |
| `TRAJET` | Temps d'attente avant chaque épreuve (1 min). |
| `EPREUVES` | Textes, règles et indices de chaque épreuve. |
| `EQUIPES` | Noms, couleurs et ordre de passage des équipes. |
| `SUSPECTS` | La liste des suspects du labo. |
| `GAGES` | Le(s) gage(s) donné(s) après une défaite. |

La photo de la révélation est [`diego.jpg`](diego.jpg) (version allégée de l'originale,
qui reste hors du dépôt).

## À imprimer (dossier `print/`)

| Fichier | Contenu |
|---|---|
| `qr-code-A5.pdf` | Affiche « Scannez pour jouer » avec le QR code du jeu. |
| `lettres-A5.pdf` | Les 6 lettres É · C · L · O · R · E à cacher dans le jardin. |
| `etiquettes-A4.pdf` | Étiquettes du buffet, toutes sur une feuille A4. |

Impression : format indiqué, sans marges, en cochant « graphiques d'arrière-plan ».

## Mise en ligne

Le site est publié par GitHub Pages depuis la branche `main` : chaque envoi sur `main`
met le jeu en ligne en une minute environ.
