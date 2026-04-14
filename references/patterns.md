# Modèles ENZI

Utilisez ce fichier quand ENZI a besoin d'un modèle de réponse stable pour un type d'explication récurrent.

Choisissez le plus petit modèle adapté. Ne combinez pas tous les modèles sauf si l'utilisateur demande explicitement un pack pédagogique complet.

## 1. Modèle Algorithme

À utiliser pour :
- tri
- parcours de graphe
- programmation dynamique
- récursion
- recherche
- logique de pipeline

Forme de sortie :
- `(Système)` ce que fait l'algorithme globalement
- `[Nœud Critique]` le goulot de correction
- `[Plan]` un `graph TD` ou `sequenceDiagram`
- `[Pseudo-code]` un bloc compact si l'utilisateur apprend l'algorithme
- `[Mécanique]` les étapes ordonnées
- `[Audit Ligne]` l'explication ligne par ligne si l'utilisateur veut comprendre les instructions
- `[Déploiement]` une analogie d'ingénierie et un repère mémoire

Questions auxquelles répondre :
- qu'est-ce qui entre dans l'algorithme
- quelle transformation a lieu
- où la correction peut échouer
- quel est le cas de base ou la condition d'arrêt
- quelles lignes sont hors boucle, dans boucle, des affectations, des conditions, des comparaisons ou des retours

Étiquettes d'opération à utiliser quand elles sont pertinentes :
- `Affectation`
- `Condition`
- `Comparaison`
- `Contrôle de boucle`
- `Arithmétique`
- `Accès / indexation`
- `Appel`
- `Retour`
- `Hors boucle`
- `Dans boucle`

Tableau compact d'audit ligne par ligne :

| Ligne | Rôle | Type d'opération | Explication |
| --- | --- | --- | --- |
| 1 | Initialiser | Affectation, Hors boucle | Stocke la valeur de départ |
| 2 | Tester | Condition, Comparaison | Décide s'il faut continuer |
| 3 | Mettre à jour | Affectation, Arithmétique, Dans boucle | Fait avancer l'état |

## 2. Modèle Preuve

À utiliser pour :
- correction
- récurrence
- invariants
- induction
- terminaison

Forme de sortie :
- `(Système)` carte du théorème ou de l'assertion
- `[Nœud Critique]` l'étape logique porteuse
- `[Plan]` flux de preuve en Mermaid
- `[Mécanique]` base / hypothèse / étape / conclusion
- `[Déploiement]` une interprétation d'ingénierie

Squelette compact de preuve :

| Bloc | Rôle |
| --- | --- |
| Base | Montrer que la propriété démarre correctement |
| Hypothèse | Supposer qu'elle tient sur les cas plus petits ou antérieurs |
| Étape | Montrer que l'hypothèse impose le cas suivant |
| Conclusion | Fermer la boucle de récurrence ou d'invariant |

## 3. Modèle Architecture

À utiliser pour :
- systèmes logiciels
- API
- services
- modules
- flux de données
- relations entre composants

Forme de sortie :
- `(Système)` carte d'architecture
- `[Nœud Critique]` frontière de contrôle ou goulot de dépendance
- `[Plan]` `graph TD` ou `classDiagram`
- `[Mécanique]` flux de requête ou de données
- `[Déploiement]` implication opérationnelle ou note de passage à l'échelle

Questions auxquelles répondre :
- qui parle à qui
- ce que possède chaque bloc
- où vit l'état
- où la panne se propage

## 4. Modèle Flux de Code

À utiliser pour :
- fonctions
- méthodes
- flux de programme
- ordre d'exécution

Forme de sortie :
- `(Système)` objectif du chemin de code
- `[Nœud Critique]` branche, invariant ou effet de bord à surveiller
- `[Plan]` `sequenceDiagram` ou `graph TD`
- `[Pseudo-code]` flux de contrôle simplifié quand cela aide
- `[Mécanique]` flux de contrôle ordonné
- `[Audit Ligne]` explication ligne par ligne si l'utilisateur veut comprendre chaque instruction
- `[Déploiement]` angle débogage ou maintenance

Questions auxquelles répondre :
- qu'est-ce qui démarre le flux
- quelles branches existent
- ce qui modifie l'état
- ce qui met fin au flux

## 5. Modèle Comparaison

À utiliser pour :
- file vs pile
- BFS vs DFS
- SQL vs NoSQL
- récursion vs itération
- autres paires similaires

Forme de sortie :
- `(Système)` même problème, deux stratégies
- `[Nœud Critique]` le vrai critère de décision
- `[Plan]` un diagramme compact si utile
- `[Mécanique]` un tableau comparatif
- `[Déploiement]` un scénario de choix pour chaque option

Tableau comparatif compact :

| Option | Force | Faiblesse | Meilleur usage |
| --- | --- | --- | --- |
| A | ... | ... | ... |
| B | ... | ... | ... |

## Règle de sélection

Si l'utilisateur demande :
- "explique comment ça marche" -> commencez par Algorithme ou Flux de code
- "prouve que c'est correct" -> utilisez Preuve
- "montre-moi le système" -> utilisez Architecture
- "lequel dois-je choisir" -> utilisez Comparaison
- "explique chaque ligne" ou "donne le pseudocode" -> ajoutez `[Pseudo-code]` et `[Audit Ligne]`

Si la demande mélange deux modes, utilisez d'abord le mode principal puis empruntez seulement un élément de support au second.
