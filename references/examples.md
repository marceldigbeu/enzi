# Exemples guidés ENZI

Utilisez ce fichier quand l'utilisateur a besoin d'un apprentissage guidé, pas seulement d'une réponse directe.

Pour chaque exemple :
- commencez par la vue d'ensemble
- isolez le nœud critique
- montrez le pseudocode quand il aide
- expliquez ligne par ligne quand l'apprenant le demande
- nommez explicitement les types d'opérations
- ajoutez un ancrage mémoire à la fin

## 1. Recherche binaire

### `(Système)`
- La recherche binaire est un système de recherche dans une liste triée.
- Elle réduit la zone de recherche de moitié à chaque itération.

### `[Nœud Critique]`
- **Nœud Critique :** la liste doit être triée.

### `[Pseudo-code]`
```text
binary_search(L, x):
    start = 0
    end = len(L) - 1

    while start <= end:
        mid = floor((start + end) / 2)

        if L[mid] == x:
            return mid
        else if L[mid] < x:
            start = mid + 1
        else:
            end = mid - 1

    return -1
```

### `[Audit Ligne]`
| Ligne | Type d'opération | Explication |
| --- | --- | --- |
| `start = 0` | Affectation, Hors boucle | Initialise la borne gauche. |
| `end = len(L) - 1` | Affectation, Arithmétique, Hors boucle | Initialise la borne droite. |
| `while start <= end` | Condition, Comparaison, Contrôle de boucle | Continue tant que la zone de recherche existe. |
| `mid = floor((start + end) / 2)` | Affectation, Arithmétique, Dans boucle | Calcule l'indice du milieu. |
| `if L[mid] == x` | Accès / indexation, Comparaison, Condition, Dans boucle | Vérifie si la valeur centrale est la cible. |
| `return mid` | Retour, Dans boucle | S'arrête immédiatement si l'élément est trouvé. |
| `start = mid + 1` | Affectation, Arithmétique, Dans boucle | Se déplace vers la droite. |
| `end = mid - 1` | Affectation, Arithmétique, Dans boucle | Se déplace vers la gauche. |
| `return -1` | Retour, Hors boucle | Signale l'échec après la boucle. |

### Ancrage mémoire
- Liste triée -> test du milieu -> réduction de moitié.

## 2. Tri fusion

### `(Système)`
- Le tri fusion découpe un grand problème de tri en deux plus petits problèmes.
- Puis il reconstruit le résultat en fusionnant deux moitiés déjà triées.

### `[Nœud Critique]`
- **Nœud Critique :** `merge` doit combiner correctement deux listes déjà triées.

### `[Pseudo-code]`
```text
merge_sort(L):
    n = len(L)
    if n <= 1:
        return L

    mid = floor(n / 2)
    left = merge_sort(L[0:mid])
    right = merge_sort(L[mid:n])
    return merge(left, right)
```

### `[Audit Ligne]`
| Ligne | Type d'opération | Explication |
| --- | --- | --- |
| `n = len(L)` | Affectation, Appel, Hors boucle | Stocke la taille de la liste. |
| `if n <= 1` | Condition, Comparaison, Hors boucle | Détecte le cas de base. |
| `return L` | Retour, Hors boucle | Arrête la récursion sur une liste triviale. |
| `mid = floor(n / 2)` | Affectation, Arithmétique, Hors boucle | Calcule le point de découpe. |
| `left = merge_sort(L[0:mid])` | Affectation, Appel, Accès / indexation, Hors boucle | Trie récursivement la moitié gauche. |
| `right = merge_sort(L[mid:n])` | Affectation, Appel, Accès / indexation, Hors boucle | Trie récursivement la moitié droite. |
| `return merge(left, right)` | Retour, Appel, Hors boucle | Fusionne les deux moitiés triées. |

### Ancrage mémoire
- Découper, trier plus petit, fusionner proprement.

## 3. Somme dans une boucle

### `(Système)`
- Cet algorithme accumule les valeurs de `0` à `n` dans un total courant.
- Il se comporte comme un compteur avec un registre mémoire.

### `[Nœud Critique]`
- **Nœud Critique :** `tmp` doit toujours contenir la somme partielle déjà traitée.

### `[Pseudo-code]`
```text
sum_int(n):
    tmp = 0
    for i in range(n + 1):
        tmp = tmp + i
    return tmp
```

### `[Audit Ligne]`
| Ligne | Type d'opération | Explication |
| --- | --- | --- |
| `tmp = 0` | Affectation, Hors boucle | Initialise l'accumulateur. |
| `for i in range(n + 1)` | Contrôle de boucle, Appel, Arithmétique, Hors boucle | Met en place l'itération de `0` à `n`. |
| `tmp = tmp + i` | Affectation, Arithmétique, Dans boucle | Ajoute la valeur courante au total cumulé. |
| `return tmp` | Retour, Hors boucle | Renvoie la somme finale accumulée. |

### Ancrage mémoire
- `tmp` est le réservoir de stockage ; chaque boucle ajoute une unité de plus.
