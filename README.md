# Loto

Application web pour suivre ses cartons de loto (numéros de 1 à 90), sans papier ni jetons.

Site : https://tomgontard.github.io/Loto/

## Fonctionnement

- Saisissez vos cartons ligne par ligne (3 lignes, 9 colonnes). Chaque numéro se range dans sa colonne : 1‑9, 10‑19 … 80‑90.
- Ou prenez le carton en photo : les numéros sont lus automatiquement sur le téléphone (rien n'est envoyé), puis vous vérifiez avant d'enregistrer. Les numéros douteux sont entourés d'orange.
- Tapez les numéros annoncés : les jetons se placent tout seuls sur les cartons. Quines, doubles quines et cartons pleins sont signalés.
- Le tableau de 1 à 90 permet de corriger d'un clic. « Annuler le dernier » retire le dernier numéro, « Plus avancés » trie les cartons.
- « Nouvelle partie » efface les numéros sortis et garde les cartons. « Supprimer les cartons » efface tout.
- « Exporter » sauvegarde vos cartons dans un fichier JSON. « Importer » ajoute les cartons d'un fichier à ceux de l'appareil, sans doublons.

## Données

Tout est enregistré dans le navigateur (localStorage, clé `loto-state-v1`). Chaque appareil garde ses propres cartons : rien n'est envoyé sur un serveur ni partagé.

## Technique

Un seul fichier `index.html` (HTML, CSS et JavaScript), sans dépendance à part Google Fonts et, pour la lecture des photos, [Tesseract.js](https://github.com/naptha/tesseract.js) chargé depuis jsDelivr au premier usage seulement (environ 6 Mo, puis mis en cache). Pas de build : le site est publié par GitHub Pages depuis la branche `main`, dossier racine.
