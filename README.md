# ENZI

ENZI est un skill Claude Code / Codex conçu pour enseigner, analyser et stratégiser — avec une méthode architecturale, visuelle et structurée.

Il opère en **3 domaines** :

| Domaine | Ce qu'il fait |
|---|---|
| **Enseignement** | Explique algorithmes, preuves, code, architecture avec une carte descendante |
| **Creator** | Analyse les algorithmes de recommandation et construit des stratégies de publication |
| **Personal Branding** | Identifie l'archétype de marque, définit palette, tone of voice et stratégie multi-plateformes |

---

## Modes disponibles

### Mode Enseignement (défaut)

Pour tout sujet technique : algorithme, preuve, flux de code, architecture système.

Pipeline de sortie :
1. `(Système)` — carte d'ensemble
2. `[Nœud Critique]` — l'idée porteuse
3. `[Plan]` — diagramme Mermaid
4. `[Pseudo-code]` — si l'algorithme doit être appris
5. `[Mécanique]` — explication pas à pas
6. `[Audit Ligne]` — ligne par ligne avec types d'opérations
7. `[Déploiement]` — ancrage ingénierie

Toutes les réponses s'ouvrent avec `[ENZI ACTIF]`.

---

### Mode Analyse de Systèmes de Recommandation

Activé quand l'utilisateur demande comment fonctionne un algorithme de plateforme.

Plateformes couvertes : TikTok · YouTube · YouTube Shorts · Instagram Reels · Spotify · Netflix · LinkedIn · X/Twitter · Pinterest

Ancres spécifiques :
- `[Pipeline]` — flux de bout en bout
- `[Signaux]` — implicites vs explicites
- `[Score]` — fonction de classement
- `[Biais]` — bulles de filtre, froid démarrage
- `[Levier]` — ce que le créateur peut actionner

---

### Mode Profil Créateur

Construit un profil personnalisé pour percer sur une ou plusieurs plateformes.

```
[Profil Créateur]
Niche : [thématique principale]
Plateforme : [TikTok / YouTube / Reels / multi]
Format : [face caméra / voix off / montage / live…]
Audience cible : [description courte]
Objectif : [notoriété / abonnés / monétisation / test]
Rythme : [x vidéos / semaine]
Niveau actuel : [débutant / en croissance / établi]
```

---

### Mode Stratégie de Publication

Génère une stratégie de posting adaptée à la niche et à la plateforme.

Ancres :
- `[Calendrier]` — créneaux optimaux par jour et plateforme
- `[Format Gagnant]` — durée et format selon la niche
- `[Événements]` — tendances et calendrier éditorial à anticiper
- `[Fréquence]` — rythme algorithmique optimal
- `[Hook]` — 3 accroches adaptées à la niche

---

### Mode Plan HTML

Génère un fichier HTML autonome (tableau de bord créateur) exportable sur le bureau, avec :
- profil créateur en carte visuelle
- planning semaine par semaine avec couleurs d'accent
- fiche par vidéo : date, créneau, hook, script horodaté, CTA
- bloc stratégie de conversion

---

### Mode Script Rapide

Génère un script TikTok / YouTube Shorts en 5 blocs horodatés :

| Bloc | Durée | Rôle |
|---|---|---|
| Hook | 0–3s | Force à ne pas scroller |
| Setup | 3–15s | Pose le problème |
| Corps | 15–45s | Le contenu réel |
| Punchline | 45–55s | Ce que l'audience retient |
| CTA | 55–60s | Une seule action demandée |

---

### Mode Personal Branding

Construit une identité de marque complète pour devenir visible sur les réseaux.

**7 archétypes** : La Star · L'Artiste · L'Expert · L'Entrepreneur · Le Créateur · L'Activiste · Le Luxe

Livrables :
```
[Identité de Marque]
Archétype dominant : ...
WHY : ...
Valeurs : ...
Mot signature : ...
Palette de couleurs : dominante / secondaire / accent
Tone of voice : ...
Style visuel : ...
```

Inclut : psychologie des couleurs, stratégie multi-plateformes, erreurs à éviter, export HTML branding.

---

## Structure du dépôt

```
enzi/
├── SKILL.md                  # Définition principale du skill
├── references/
│   ├── patterns.md           # Modèles de réponse stables (algo, preuve, archi, comparaison)
│   ├── examples.md           # Exemples pédagogiques résolus (binary search, merge sort, sum)
│   └── identity.md           # Identité visuelle et de marque ENZI
├── agents/
│   └── openai.yaml           # Métadonnées d'interface Codex
├── assets/                   # Icônes ENZI
└── README.md
```

---

## Utiliser ENZI

### Dans Claude Code

Le skill est disponible via `/enzi` dans Claude Code.

### Dans Codex

```bash
git clone https://github.com/marceldigbeu/enzi
cd enzi
codex .
```

Ou directement depuis ton projet :

```bash
codex --instructions path/to/enzi/SKILL.md
```

Prérequis : [Node.js](https://nodejs.org) puis `npm install -g @openai/codex`

### Prompt d'invocation

```text
Utilise $enzi pour expliquer cela avec une carte descendante, un nœud critique nommé, un plan Mermaid et des sections architecturales courtes.
```

---

## Exemples de déclenchement

**Enseignement**
- « Explique cet algorithme en me montrant d'abord la structure globale »
- « Donne-moi la vue d'ensemble avant la preuve »
- « Donne le pseudocode et explique chaque ligne »

**Creator & Algorithmes**
- « Comment fonctionne l'algorithme TikTok / Instagram Reels / LinkedIn ? »
- « Pourquoi mes Reels ne décollent pas ? »
- « Comment avoir du reach sur X sans abonnés ? »

**Stratégie de publication**
- « Construis mon profil créateur »
- « Quoi poster, quand et comment pour percer sur YouTube Shorts ? »
- « Génère un plan de contenu sur 4 semaines »
- « Exporte le plan en HTML »

**Personal Branding**
- « Construis mon personal branding »
- « Quel est mon archétype de marque ? »
- « Quelles couleurs pour mon image de marque ? »
- « Crée mon identité de marque complète »
