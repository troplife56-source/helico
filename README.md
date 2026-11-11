# Hélico

Un Helicopter Game jouable dans le navigateur, en HTML, CSS et JavaScript, sans dépendance.

**Jouer :** https://troplife56-source.github.io/helico/

## Comment jouer

Maintiens pour monter, relâche pour descendre. Évite la roche, ramasse les pièces.

| Action | Commande |
| --- | --- |
| Monter | Espace, flèche haut, W, clic maintenu ou doigt maintenu |
| Pause | P, Échap ou le bouton Pause |
| Son | M ou le bouton Son |

## Fonctionnalités

- Trois niveaux de difficulté (Facile, Normal, Difficile), avec un record séparé pour chacun.
- Compte à rebours 3, 2, 1 avant chaque départ.
- Une nouvelle zone tous les 500 m : Grotte, Glacier, Lave, Cristaux.
- Pièces (+10 points) et bouclier qui absorbe un choc.
- Fumée du rotor, explosion, légère secousse d'écran, parallaxe.
- Sons générés dans le navigateur (Web Audio), aucun fichier audio.
- Record et réglages sauvegardés dans le navigateur.
- Adapté au téléphone et à l'écran tactile.

## Structure

Tout le jeu tient dans `index.html` : styles, rendu sur canvas, physique et sons.

Pour jouer en local, ouvre simplement `index.html` dans un navigateur.

## Mesure d'audience

La page charge un Google tag (`GTM-KGTH2DQP`) et envoie ces événements dans le `dataLayer` :

| Événement | Quand | Paramètres |
| --- | --- | --- |
| `helico_start` | Au lancement d'une partie | `difficulty` |
| `helico_crash` | À la fin d'une partie | `difficulty`, `score`, `meters`, `coins`, `zone`, `new_record` |
| `helico_zone` | Quand une nouvelle zone commence | `difficulty`, `zone`, `zone_name` |

Pour les exploiter, crée dans Google Tag Manager des déclencheurs de type « Événement personnalisé » avec ces noms.
