# Photobooth des 40 ans d'Auré

Page web autonome (rien à installer sur les téléphones) : selfie → Auré à l'âge et dans le style choisis → image 1080 × 1350 à partager.

- `index.html` : toute l'application (styles d'Auré dans l'objet `STYLES`).
- `morphing/` : copie de `diaporama/morphing/` (visages de 0 à 70 ans). À recopier si le morphing est régénéré.

## Confidentialité
Tout se passe dans le téléphone : le selfie n'est envoyé à aucun serveur et rien n'est enregistré en ligne.
La page demande aux moteurs de recherche de ne pas l'indexer (`robots.txt` et balise `noindex`).

## Mise en ligne
La caméra du téléphone n'est accessible qu'en **HTTPS**, d'où l'hébergement sur GitHub Pages.
Ce dossier est publié dans un dépôt public à part, qui ne contient que lui (le reste du projet reste privé).
Après une modification, depuis la racine du projet :

    git subtree push --prefix photobooth photobooth main

La page en ligne est mise à jour en une à deux minutes.

## QR code dans le diaporama
Dans `construire_diaporama.py`, l'adresse du photobooth est dans `PHOTOBOOTH_URL` ; relancer `python construire_diaporama.py` (nécessite `pip install segno`).

## Tester sur PC
Ouvrir `index.html` par double-clic ne suffit pas (le navigateur bloque la création de l'image). Depuis la racine du projet :

    python -m http.server 8000

puis http://localhost:8000/photobooth/ (la webcam fonctionne aussi sur localhost).
