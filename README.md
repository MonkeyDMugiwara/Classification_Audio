# Détection de Toux COVID-19

## Description
Ce projet a pour objectif de développer un système de classification audio basé sur l'IA pour détecter les toux liées au COVID-19 à partir de toux classiques. Le modèle utilise des techniques d'apprentissage profond, y compris des réseaux de neurones convolutifs (CNN), l'optimisation avec Optuna et l'apprentissage par transfert avec Yamnet, pour classifier les enregistrements audio de toux en tant que COVID-19 positif ou négatif.

## Fonctionnalités principales
- **Classification Audio** : Le modèle peut classer les enregistrements audio de toux en deux catégories : toux liée au COVID-19 et toux classique.
- **Prétraitement** : Les fichiers audio sont convertis en coefficients cepstraux en fréquence Mel (MFCC), utilisés comme caractéristiques pour l'entraînement du modèle.
- **Optimisation du modèle** : Les hyperparamètres du modèle sont optimisés à l'aide du framework Optuna pour améliorer les performances et réduire le sur-apprentissage.
- **Apprentissage par transfert** : Le projet utilise un modèle pré-entraîné (Yamnet) pour extraire des caractéristiques puissantes de l'audio, améliorant ainsi la précision de la classification.
- **Validation croisée** : Des techniques de validation croisée sont utilisées pour évaluer les performances du modèle et réduire les risques de sur-apprentissage.

## Données

Le jeu de données utilisé dans ce projet contient des enregistrements audio de toux :
- **Toux COVID-19** : Enregistrements audio de patients atteints du COVID-19.
- **Toux classique** : Enregistrements audio de personnes en bonne santé.

Le jeu de données utilisé pour l'entraînement du modèle provient du **CHU de Montpellier** et contient un total de 2291 fichiers audio. Les enregistrements sont prétraités à l'aide de la bibliothèque `librosa` pour les convertir en représentations MFCC utilisées dans l'extraction des caractéristiques.

## Aperçu du Modèle

Le modèle est une architecture de réseau de neurones convolutifs (CNN) entraînée pour classer les caractéristiques extraites des toux en deux classes : COVID-19 ou classique. Le processus d'entraînement suit les étapes suivantes :
1. **Prétraitement des données** : Conversion des fichiers audio en MFCC.
2. **Entraînement du modèle** : Utilisation des couches CNN pour apprendre les motifs dans les MFCC.
3. **Optimisation des hyperparamètres** : Le framework Optuna est utilisé pour ajuster les hyperparamètres du modèle, comme le taux d'apprentissage, la taille des batches et le nombre de couches convolutives.
4. **Apprentissage par transfert** : Utilisation de Yamnet, un modèle pré-entraîné, pour extraire des caractéristiques audio profondes qui seront utilisées pour entraîner le modèle de classification.

## Évaluation

Le modèle est évalué en utilisant :
- **Précision** : La proportion de toux correctement classifiées.
- **Validation croisée** : Validation croisée à 5 et 10 plis pour assurer une évaluation robuste.
- **Matrice de confusion** : Pour visualiser les vrais positifs, faux positifs, vrais négatifs et faux négatifs.

## Résultats

Le modèle atteint :
- **Précision de validation** : ~82% après optimisation et réglage des hyperparamètres avec Optuna.
- **Résultats de la validation croisée** : Performance stable sur les différents sous-ensembles du jeu de données.

## Travaux futurs

- **Augmentation des données** : Ajouter plus de données pour améliorer la généralisation du modèle.
- **Modèles avancés** : Tester des architectures plus complexes comme les réseaux de neurones récurrents (RNN) ou les LSTM (Long Short-Term Memory).
- **Test en conditions réelles** : Déployer le modèle dans des environnements réels pour évaluer son efficacité dans des contextes médicaux.

## Conclusion

Ce projet démontre comment l'IA et l'apprentissage automatique peuvent être appliqués dans le domaine médical pour une détection rapide et précise du COVID-19 en utilisant l'analyse audio. Grâce à l'utilisation de l'apprentissage par transfert avec Yamnet et l'optimisation des hyperparamètres avec Optuna, le projet a montré des résultats prometteurs pour identifier les toux liées au COVID-19, offrant ainsi un outil efficace pour un diagnostic précoce.

## Collaborateur
Projet fait par Rafael Letrillard : https://github.com/rafalet34
Projet fait par Amine Adib :  https://github.com/oildo
Projet fait par Dogukan Tokmak : https://github.com/MonkeyDMugiwara/
