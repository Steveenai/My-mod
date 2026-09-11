# Oeil de l'Empereur — Mod NeoForge 1.21.1

## Ce que fait le mod
- **Clic droit** avec l'Œil de l'Empereur en main : vise l'entité sous ton viseur (jusqu'à 48 blocs)
  et tire une perle rouge qui **suit une trajectoire courbe** (elle s'infléchit vers la cible au lieu
  d'aller tout droit), avec une **traînée de particules rouges en 3D**.
- **Quand la perle touche une entité** : tu possèdes son corps, ta caméra se place dessus.
- **Touche Z** : bascule le "Mode Empereur Suprême" (liseré rouge à l'écran + particules rouges
  autour de ta tête, visibles par les autres joueurs).
- **Touche R (maintenue)** pendant une possession : tu contrôles le déplacement (ZQSD/WASD),
  le saut, le regard et l'attaque de la victime possédée.

## Limitations volontaires (à faire évoluer si besoin)
- Le contrôle de la victime couvre déplacement / saut / regard / attaque — pas d'actions
  "arbitraires" façon script libre (utiliser un objet, ouvrir un coffre, etc. peut être ajouté
  en étendant `ControlVictimPayload` et `ServerPayloadHandler`).
- Pas de texture fournie pour l'item : ajoute un PNG 16x16
  `src/main/resources/assets/emperoreye/textures/item/emperor_eye.png`.
- L'effet "yeux rouges" du joueur est un liseré d'écran + particules ; un vrai calque de rendu
  sur le skin du joueur (CustomHeadLayer) demanderait plus de code de rendu.

## Compiler
Prérequis : JDK 21, connexion internet (Gradle télécharge NeoForge la première fois).

```
./gradlew build
```

Le `.jar` sera dans `build/libs/`. Pour tester directement :

```
./gradlew runClient
```

Si le build échoue à cause des numéros de version dans `gradle.properties`
(`neo_version`, `parchment_*`), va sur https://projects.neoforged.net/neoforged/neoforge
pour prendre la version exacte disponible pour le 1.21.1 et remplace-la.
