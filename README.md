# Quoridor (Java)

Implémentation du jeu de plateau **Quoridor** en Java 21, avec interface graphique, interface console, jeu en réseau et plusieurs intelligences artificielles.

> Projet universitaire (Projet de programmation, Université de Bordeaux, 2025-2026), réalisé en équipe de 5 personnes :
> Abdeldjabar Ismail Abdraman, Cengiz Vasseur, Joris Douillet, Khadidja Ahmat Hassan, Matthieu Pourageaud.

## Fonctionnalités

- **Deux interfaces** : graphique (JavaFX) et console interactive (JLine).
- **Jeu en réseau** : serveur, client, découverte des serveurs par broadcast UDP.
- **Intelligences artificielles** : Minimax avec élagage alpha-bêta (3 heuristiques), MCTS (recherche arborescente Monte Carlo), joueur aléatoire, évaluation par réseau de neurones (TensorFlow).
- **Règles** : plateau de taille variable, 2 à 4 joueurs, mode blitz (temps limité), vérification des coups et des murs (le chemin vers l'arrivée ne doit jamais être bloqué).
- **Sauvegarde et chargement** de parties, annuler / rétablir (undo / redo).
- **Deux langues** : français et anglais.
- **Tests automatisés** : environ 640 tests (JUnit 5, Mockito, TestFX), couverture mesurée avec JaCoCo (seuil de 85 %).

## Organisation du code

```
src/main/java/fr/bordeaux/
├── core/         règles du jeu, plateau, coups, moteur
├── graph/        graphe du plateau (plus court chemin)
├── ai/           Minimax, MCTS, heuristiques, réseau de neurones
├── cli/          interface console et ses commandes
├── gui/          interface graphique JavaFX
├── network/      serveur, client, broadcast
├── persistence/  sauvegarde et chargement des parties
├── main/         point d'entrée et options de la ligne de commande
├── i18n/         traductions
└── config/ util/
docs/             rapports du projet (préliminaire et final)
```

## Lancer le projet

Prérequis : **Java 21** et **Maven**.

```bash
# Compiler et lancer les tests
mvn test

# Construire le jar exécutable
mvn package -DskipTests

# Lancer en mode console (par défaut)
java -jar target/quoridor-1.0-SNAPSHOT.jar

# Lancer l'interface graphique
java -jar target/quoridor-1.0-SNAPSHOT.jar --gui
```

L'option `--help` affiche toutes les options (taille du plateau, nombre de joueurs, blitz, choix de l'IA, mode réseau…).

## Documentation

- [Rapport préliminaire](docs/rapport-preliminaire.pdf)
- [Rapport final](docs/rapport-final.pdf)

## Licence

Projet universitaire publié à titre de démonstration. Tous droits réservés aux auteurs.
