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

- `index.html` : tout le jeu (styles, rendu sur canvas, physique, sons) et le bandeau de consentement.
- `og-image.png` : image de 1200 × 630 affichée quand le lien est partagé (WhatsApp, Messenger, réseaux sociaux).

Pour jouer en local, ouvre simplement `index.html` dans un navigateur.

## Mesure d'audience

Un bandeau demande l'accord du visiteur. Tant qu'il n'a pas accepté, tout est refusé par défaut (Consent Mode) et le script Google (`GTM-KGTH2DQP`) n'est pas chargé. Le lien « Gérer les cookies », en bas de page, permet de changer d'avis. Une fois l'accord donné, le jeu envoie ces événements dans le `dataLayer` :

| Événement | Quand | Paramètres |
| --- | --- | --- |
| `helico_start` | Au lancement d'une partie | `difficulty` |
| `helico_crash` | À la fin d'une partie | `difficulty`, `score`, `meters`, `coins`, `zone`, `new_record` |
| `helico_zone` | Quand une nouvelle zone commence | `difficulty`, `zone`, `zone_name` |

Pour les exploiter, crée dans Google Tag Manager des déclencheurs de type « Événement personnalisé » avec ces noms.
