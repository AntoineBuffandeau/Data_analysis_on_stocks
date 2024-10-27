# Analyse du Réseau de Corrélation d'Actions du CAC40

Ce projet explore la structure d'un réseau de corrélations basé sur les actions du CAC40. En appliquant des techniques de science des réseaux, l'objectif est d'étudier la connectivité, les structures de communauté, et la répartition core-périphérie du réseau, en comparaison avec des modèles de référence. 

## Auteurs

- Antoine Buffandeau
- Charles François
- Mathieu Gourmelen

## Contexte

Le projet a été réalisé dans le cadre d'un exercice d'innovation en finance. Il a pour objectif de créer un réseau de corrélations à partir d'un ensemble de données sur les actions. Le réseau est construit en appliquant des seuils spécifiques de corrélation pour filtrer les connexions entre les actions. Ce projet a été réalisé dans le cadre d'un exercice d'innovation en finance.

## Structure des Données

Le dataset utilisé contient des valeurs de corrélation entre des paires d'actions. Chaque corrélation représente la force de la relation entre deux actions. Trois réseaux sont créés en fonction de seuils définis (0,3, 0,5, et 0,7) :
- **Seuil 0,3** : Inclut les corrélations faibles, générant un réseau plus dense.
- **Seuil 0,5** : Filtre les corrélations modérées.
- **Seuil 0,7** : Ne conserve que les corrélations fortes, aboutissant à un réseau plus éparse.

Les réseaux obtenus permettent de comparer la densité et la connectivité en fonction des seuils, et de tirer des conclusions sur la structure relationnelle des actions du CAC40.

## Méthodologie

### Étapes de l'Analyse

1. **Calcul des Métriques de Réseau** : Des métriques telles que le degré moyen, la densité, la transitivité et l'assortativité ont été calculées pour chaque réseau :
   - **Densité** : Diminue avec l'augmentation du seuil, indiquant un réseau moins connecté.
   - **Transitivité** : Indique un haut niveau de clustering pour les seuils bas.
   - **Assortativité** : Change de signe selon le seuil, indiquant un changement de structure.

2. **Mesures de Centralité** : Quatre mesures de centralité (degré, proximité, intermédiaire, et centralité propre) permettent d'identifier les actions influentes à chaque niveau de seuil.

3. **Comparaison avec des Modèles de Réseau** : Le réseau est comparé aux modèles d'Erdős–Rényi et de Barabási–Albert pour évaluer les différences de structure.

4. **Détection de Communautés** : La méthode de Louvain est utilisée pour détecter des communautés, avec une modularité plus élevée pour les seuils bas, suggérant des clusters plus définis.

5. **Analyse Core-Périphérie** : Une décomposition k-core est appliquée pour révéler la structure centrale et périphérique à chaque seuil.

### Comparaison des Modèles

Les résultats montrent que le réseau de corrélations diffère des modèles aléatoires ou sans échelle, avec des structures de centralité et de clustering propres qui révèlent des liens naturels entre les actions, potentiellement basés sur les secteurs ou la dynamique de marché.

## Conclusion

Cette analyse de réseau démontre que la structure des corrélations d'actions présente des motifs de clustering et de centralité distincts, particulièrement aux seuils bas. En augmentant le seuil, la connectivité diminue et des clusters de corrélations fortes émergent, suggérant des relations structurelles significatives au sein du CAC40.

## Requis

- Python 3.x
- Librairies : `networkx`, `matplotlib`, `pandas`, `numpy`, `matplotlib.pyplot`, `plotly.graph_objects`

## Installation

Clonez le dépôt, installez les dépendances et exécutez les scripts dans l'ordre indiqué pour reproduire l'analyse.

```bash
git clone <url-du-dépôt>
cd <répertoire-du-projet>
pip install -r requirements.txt
```