# Éditeur de sauvegarde — The Infected Grounds

Éditeur de sauvegarde pour le jeu [Zombie Survivor / The Infected Grounds](https://github.com/Ghoster-001/Zombie-Survivor-By-C02) de Ghoster. C'est une page web unique (`index.html`), sans installation ni serveur : elle s'ouvre directement dans un navigateur.

**Version du jeu prise en charge : 0.68** (affichée en haut de la page).

## Utilisation

1. Dans le jeu, exportez votre sauvegarde (fichier `infected-grounds-sauvegarde.json`).
2. Ouvrez `index.html` dans votre navigateur.
3. Chargez le fichier (bouton « Ouvrir un fichier… » ou glisser-déposer), collez son JSON, ou partez d'une nouvelle sauvegarde.
4. Modifiez ce que vous voulez, puis cliquez sur **Exporter**.
5. Réimportez le fichier dans le jeu.

## Ce qui est modifiable

| Onglet | Contenu |
|---|---|
| Général | argent, XP, niveau de vie max, record de manches, arme de mêlée équipée |
| Armes | possession et niveau d'amélioration (0 à 4) des 201 armes |
| Bonus | niveau de chaque bonus |
| Cartes | cartes terminées, meilleure manche par difficulté, carte et difficulté sélectionnées |
| Tenues | tenue équipée (y compris skins zombies), sexe, silhouette, couleurs, tenues du pack de fêtes possédées |
| JSON brut | édition directe du JSON |

Les plafonds du jeu sont appliqués à l'import et à l'export : 200 000 000 $, 2 000 000 000 XP, vie max 15, 1 000 manches, bonus au niveau maximal prévu par le jeu. Les armes inconnues sont retirées.

## Limite : l'anti-triche du jeu

Le jeu signe ses exports avec une clé propre à l'appareil (C02 Anti-Cheat). Cet éditeur **ne produit pas et ne contourne pas** cette signature : le fichier exporté n'est pas signé.

Conséquence : le jeu n'accepte un fichier modifié que s'il n'apporte rien de plus que sa propre copie chiffrée (valeurs égales ou réduites), ou s'il provient d'une version plus ancienne du jeu. Un import refusé est le comportement attendu, pas un bug de l'éditeur.

## Mise à jour

Quand le jeu change de version, vérifier la liste des armes, les plafonds de la fonction `plaus`, les bonus, les cartes et les tenues dans son `index.html`, puis mettre à jour les données et la constante `GAME_VERSION` de l'éditeur.
