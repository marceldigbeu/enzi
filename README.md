# ENZI

ENZI est un skill Codex conçu pour expliquer des sujets techniques avec une méthode architecturale, visuelle et structurée.
Il s'adresse aux utilisateurs qui comprennent mieux quand ils voient :
- le système entier avant les détails locaux
- le concept porteur principal très tôt
- un plan logique avec Mermaid
- du pseudo-code compact et un audit ligne par ligne quand c'est nécessaire

## Positionnement

ENZI ne cherche pas seulement à répondre. Il cherche à faire comprendre.

Le skill transforme une explication technique en parcours pédagogique lisible :
- une cartographie descendante du système
- un `[Nœud Critique]` explicite
- des sections structurées et peu bruyantes
- des analogies d'ingénierie ancrées dans le mécanisme réel
- des exemples résolus au lieu d'une longue prose abstraite

## Cas d'usage

ENZI est particulièrement utile pour :
- algorithmes
- preuves et invariants
- parcours du flux de code
- architecture système
- comparaisons entre concepts techniques

## Format de sortie

Les sorties ENZI suivent généralement cette séquence :
1. `(Système)`
2. `[Nœud Critique]`
3. `[Plan]`
4. `[Pseudo-code]`
5. `[Mécanique]`
6. `[Audit Ligne]`
7. `[Déploiement]`

L'objectif est de faire passer l'utilisateur du global vers le local, sans surcharge cognitive.

## Structure du dépôt

- `SKILL.md` : définition principale du skill et règles de fonctionnement
- `references/patterns.md` : modèles de réponse stables
- `references/examples.md` : exemples pédagogiques résolus
- `references/identity.md` : identité visuelle et de marque
- `agents/openai.yaml` : métadonnées d'interface
- `assets/` : icônes ENZI

## Utiliser ENZI

Dans Codex, invoquez-le avec :
```text
Utilise $enzi pour expliquer cela avec une carte descendante, un nœud critique nommé, un plan Mermaid et des sections architecturales courtes.
```

Exemples de demandes adaptées :
- « Explique cet algorithme en me montrant d'abord la structure globale »
- « Donne-moi la vue d'ensemble avant la preuve »
- « Cartographie le flux de ce code et montre le nœud critique »
- « Explique chaque ligne avec les types d'opérations »



## ?? Installation en 2 minutes avec Codex CLI

```bash
# 1. Clone le skill
git clone https://github.com/marceldigbeu45-ux/enzi

# 2. Lance Codex avec ENZI
cd enzi
codex .
```

Ou sans cloner, directement depuis ton projet :

```bash
codex --instructions path/to/enzi/SKILL.md
```

Pr?requis : [Node.js](https://nodejs.org) puis `npm install -g @openai/codex`

## Publication GitHub

Ce dépôt est autonome et peut être versionné directement comme dépôt GitHub.
