# 🐀 Rat Invasion — mod Fabric pour Minecraft 1.21.1

Des rats partout, des pièges, des cages, du fromage, un Roi et un Empereur des Rats, et la **Garenne des Rats** :
une dimension pleine de ratanium pour fabriquer du matériel surcheaté.

## Compiler
1. Java 21 + Gradle 8.12 : `gradle wrapper --gradle-version 8.12` (une seule fois, génère `gradlew`)
2. `./gradlew build` → le mod est dans `build/libs/ratinvasion-1.0.0.jar`
3. `./gradlew runClient` pour tester directement
4. Si Gradle râle sur une version : prends celles de https://fabricmc.net/develop/ et édite `gradle.properties`
   (`loader_version`, `fabric_version`, `yarn_mappings`). Utilise un **nouveau monde** pour tester.

## Contenu
**Rats** : 6 variantes selon le biome (brun plaines, gris forêt/montagne, blanc froid, sable désert/mesa/savane,
noir marais/jungle, vert égout dans la Garenne). Fuient le joueur sauf s'il tient du fromage, suivent le fromage,
se reproduisent avec, et foncent vers les pièges appâtés.

**Capturer / tuer** : Piège à rats (appâter avec du fromage, clic droit à vide pour ré-armer), Cage à rat (rat affaibli,
bébé, ou fromage dans l'autre main ; la cage occupée relâche le rat), Fromage empoisonné, Tapette à rats
(tue les rats d'un coup, +8 dégâts aux boss).

**Boss** : Roi des Rats (Fromage royal, n'importe où) et Empereur des Rats (Fromage impérial, dans la Garenne) :
barre de boss, invocation de rats agressifs, phase enragée sous 50 %, coup au sol pour l'Empereur.

**Dimension** : Clé de la Garenne (clic droit = aller/retour). Minerai de ratanium → lingots → outils, armure
(bonus d'armure complète), Sceptre des rats, Fromage divin.

## Égouts
Grandes structures souterraines (45x45 ou 31x31, 3 variantes) : couloirs avec canal d'eau, salles de nids de rats
(spawners de rats), salles au trésor (coffres avec loot spécial), fromage, toiles, lanternes.
- **Sous les villages** : même placement que les villages vanilla (même spacing/séparation/salt), donc un égout
  se trouve sous chaque village.
- **Égouts sauvages** : dans la plupart des biomes terrestres.
- Entrée : un puits à échelle fermé par une trappe en épicéa dans le sol (2 puits par égout).

## Obtenir le .jar sans rien installer (GitHub)
1. Crée un compte sur github.com, puis un dépôt vide (« New repository »).
2. Envoie-y tout le contenu de ce dossier (« Add file » > « Upload files »), y compris le dossier `.github`.
3. Onglet **Actions** : le workflow « Construire le mod » démarre seul (3-5 min).
4. Ouvre l'exécution terminée, télécharge l'artefact **ratinvasion-jar** : dézippe-le, le `.jar` est dedans.

## Installer pour jouer
1. Installe **Fabric Loader** pour Minecraft 1.21.1 (https://fabricmc.net/use/installer/).
2. Télécharge **Fabric API** pour 1.21.1 (Modrinth/CurseForge) et mets le `.jar` dans `.minecraft/mods`.
3. Mets aussi `ratinvasion-1.0.0.jar` dans `.minecraft/mods`, puis lance le profil Fabric.

## Textures
Tout est dans `src/main/resources/assets/ratinvasion/textures` (16x16 pour items/blocs, 32x32 entités, 64x32 armure).
Elles sont générées par `tools/gen_textures.py` (relance-le après modification) ; `tools/preview_sheet.png` est un aperçu.
`tools/gen_sewers.py` régénère les égouts (.nbt + worldgen). `tools/gen_data.py` régénère modèles, langues (FR/EN), recettes, loot, tags et worldgen.
