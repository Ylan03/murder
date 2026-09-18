# Murder — modifications Hyltaria

Base : Murder officiel (master récent). Seules les modifications ci-dessous ont été ajoutées ;
elles sont repérables dans le code par le tag `[HYLTARIA]` (ou listées ici).

## Code (gamemodes/murder/gamemode/)
- `sv_bystandername.lua` : le nom de bystander = vrai pseudo du joueur (plus de nom aléatoire).
- `sv_loot.lua` : premier Magnum à **3** indices (au lieu de 5). Le Magnum tous les 15 indices est inchangé.
- `sv_player.lua` : messages de kill → pseudo affiché une seule fois (2 endroits).
- `sv_rounds.lua` : annonces de fin de manche / déconnexion du Murderer → pseudo affiché une seule fois (3 endroits).

## Loots (gamemodes/murder/content/data/murder/)
- `mu_parking/loot.txt` : 22 emplacements (perso).
- `mu_abandoned/` :
  - `loot.txt` → fichier **actif** (actuellement = CUSTOM)
  - `loot_CUSTOM.txt` → tes 21 emplacements perso
  - `loot_OFFICIEL.txt` → les 18 emplacements de la version officielle
  Le jeu ne lit que `loot.txt` : pour changer de version, copie le fichier voulu à la place de `loot.txt`.
- `ph_bikinibottom` : volontairement non inclus (à refaire en jeu).

## Ordre de chargement des loots
1. `garrysmod/data/murder/<map>/loot.txt` (ce que sauvegarde l'éditeur de loot en jeu)
2. `gamemodes/murder/content/data/murder/<map>/loot.txt` (fichiers ci-dessus)
3. `data_static/murder/<map>/loot.txt` (données officielles)

Commande admin : `mu_loot_reload [--data | --embedded | --static]`.
Attention : un fichier dans `data/murder/<map>/` passe avant tout le reste.

## Installation
- `gamemodes/murder` → `garrysmod/gamemodes/murder`
- `data_static` → `garrysmod/data_static`
