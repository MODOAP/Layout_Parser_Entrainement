# Détection de mise en page de documents (Entrainement)

Ce carnet permet d'entraîner un modèle de détection de mise en page de documents grâce à l'outil Layout Parser.
L'entraînement doit être réalisé à partir d'un corpus de pages de documents dont les éléments de mise en page souhaités ont été annotées au format COCO (https://cocodataset.org/#home)
Le modèle entraîné peut être sauvegardé dans un dossier Google Drive, et utilisé ensuite pour la détection avec Layout Parser.
Une fonctionnalité permet d'essayer un modèle entraîné sur une page de document et de visualiser les résultats.

Le dossier Corpus_entrainement_COCO-exemple contient un mini-corpus d'entraînement au format COCO, donné en exemple, contenant deux classes annotées : illustrations et légendes.

Un corpus d'entraînement plus conséquent, contenant les classes Illustration et Légende, peut être constitué automatiquement à partir de certains documents de presse illustrée, via le script ModOAP_Creation_corpus_entrainement_LayoutParser contenu dans le dossier Creation_corpus_entrainement_LayoutParser.

Ce carnet doit être lancé dans un environnement d'exécution GPU : Exécution -> Modifier le type d'exécution -> GPU

Il nécessite de synchroniser un compte Google Drive.

La détection de mise en page utilise l'outil Layout Parser décrit sur https://github.com/Layout-Parser/layout-parser

## Utilisation

1. Ouvrir le carnet dans l'interface Google Colab et se connecter à un compte Google Drive 

2. Lancer la première cellule et cliquer sur le lien généré pour synchroniser un compte Drive si demandé.
Cette cellule importe les bibliothèques nécessaires à l'utilisation du carnet, et connecte un compte Drive.

3. Dans la cellule Entraînement : 
	- spécifier le chemin vers le dossier Google Drive contenant le corpus d'entraînement au format COCO
	- spécifier le chemin vers un dossier Google Drive où sauvegarder le modèle
	- spécifier le nombre d'itérations lors de l'entraînement dans le champ MAX_ITER
	- spécifier un nombre d'itérations pour la sauvegarde automatique du modèle dans le champ CHECKPOINT_PERIOD
	- Spécifier le taux d'apprentissage dans le champ LEARNING_RATE : un décimal compris entre 0 et 1. Ce paramètre détermine la vitesse 		d'apprentissage du modèle.
	- Pour lancer un apprentissage à partir d'un modèle précédemment entraîné (reprise de l'apprentissage ou transfer learning), spécifier le chemin 		vers le fichier .pth du dossier de ce modèle dans le champ MODELE. Laisser vide autrement.
	- lancer la cellule
	
### Pour essayer ce modèle sur une page de document :

4. Dans la cellule "Essai du modèle" :
	- entrer le chemin vers le fichier .pth dans le dossier du modèle
	- entrer le chemin vers le fichier config.yaml dans le dossier du modèle
	- préciser l'association entre les indices des classes et leur nom. Laisser vide pour ne pas préciser.
	- lancer la cellule
	
5. Dans la cellule "Visualisation de l'inférence sur une page de document" :
	- spécifier le chemin vers une page d'un document au format jpg
	- préciser le seuil du score au dessus duquel un objet est associé à une classe (un décimal entre 0 et 1, 0 ou vide pour ne pas filtrer)
	- lancer la cellule 
