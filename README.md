# Les Caves de Brumefosse

Prototype de jeu de rôle « de canapé », inspiré de Sunderfolk.
La télé fait office de maître du jeu (carte, monstres, narration). Chaque joueur utilise son téléphone comme manette, feuille de personnage et dés.

## Jouer

1. Sur l'écran partagé (ordinateur branché à la télé), ouvrez le site et choisissez **Écran de jeu**. Un code de 4 lettres et un QR code s'affichent.
2. Chaque joueur scanne le QR code avec son téléphone (ou ouvre le site, choisit **Manette** et tape le code), puis choisit un nom et une classe.
3. Sur la télé, cliquez **Commencer l'aventure**.

Aucun compte n'est nécessaire. Les appareils se connectent directement entre eux (WebRTC via PeerJS). Le plus simple est que tout le monde soit sur le même wifi.

## Contenu

- 4 classes : Guerrier, Mage, Rôdeuse, Clerc.
- Mission 1, *Les Caves de Brumefosse* : porte verrouillée, clé à récupérer sur un gobelin, chef à vaincre.
- Mission 2, *Les Geôles du Croc-Noir* : libérer Sire Aldric puis fuir avant la fin de l'alarme.
- Décor avec effets : bureau (couvert et hauteur), étagère (couvert, bloque la vue), trou (sortie coûteuse).
- Bilan de fin de mission avec trophées.

## Organisation du code

Tout le jeu tient dans `index.html`, sans étape de compilation :

- **Données** : `TERRAIN` (propriétés des cases), `CLASSES`, `FOE_TPL` (monstres), `MISSIONS` (cartes, portes, objectifs, déclencheurs).
- **Moteur de règles partagé** : ligne de vue, couvert, coûts de déplacement, chemins.
- **Écran de jeu** : fait autorité sur l'état de la partie et diffuse l'état aux manettes.
- **Manette** : envoie des intentions (déplacement, action, lancers de dés) et affiche la fiche du héros.
- **Transport** : salle temps réel de claude.ai quand la page est ouverte dans Claude, sinon connexion directe PeerJS.

Le site est publié par GitHub Pages depuis la branche `main`.
