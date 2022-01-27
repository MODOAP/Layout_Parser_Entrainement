# Création d'un corpus d'entraînement pour Layout Parser à partir de données OLR de documents Gallica

Ce script permet de créer un corpus d'entraînement pour l'outil ModOAP - Détection de mise en page (Entrainement), à partir d'annotations de mise en page (OLR) opérées sur des documents de presse numérisés en mode article et disponibles sur Gallica (voir les corpus disponibles sur https://api.bnf.fr/fr/documents-de-presse-numerises-en-mode-article)

Le script nécessite de synchroniser un compte Google Drive sur lequel se trouve un dossier contenant les informations de mise en page téléchargées depuis https://api.bnf.fr/fr/documents-de-presse-numerises-en-mode-article (fichiers .xml contenus dans le dossier ocr)

Ce script utilise le protocole de récupération d'images IIIF de Gallica : https://api.bnf.fr/fr/api-iiif-de-recuperation-des-images-de-gallica


## Utilisation

1. Ouvrir le carnet dans l'interface Google Colab et se connecter à un compte Google Drive 

2. Lancer la première cellule et cliquer sur le lien généré pour synchroniser un compte Drive si demandé.
Cette cellule importe les bibliothèques nécessaires à l'utilisation du carnet, et connecte un compte Drive.

3. Dans la seconde cellule : 
	- spécifier le chemin vers le dossier Google Drive contenant le corpus préparé en fonction des instructions du script 
	- lancer la cellule

