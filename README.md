[![Academic Year](https://img.shields.io/badge/Epitech-Tek1-blue?style=for-the-badge&logo=epitech&logoColor=white)](https://www.epitech.eu/)
[![Language: C](https://img.shields.io/badge/Language-C-00599C.svg?style=for-the-badge&logo=c)](https://en.wikipedia.org/wiki/C_(programming_language))
[![Module](https://img.shields.io/badge/Module-B--CPE--110-informational?style=for-the-badge)](#)

# 🛡️ Secured — Bibliothèque de Table de Hachage Générique en C

**Secured** est une bibliothèque logicielle en C (`libhashtable.a`) fournissant une implémentation robuste, générique et performante de la structure de données de **table de hachage associative**. Elle résout les collisions par chaînage séparé via des listes simplement chaînées.

---

## 📚 Spécification de l'API (`hashtable.h`)

| Fonction | Description | Complexité Moyenne |
|---|---|---|
| `hashtable_t *new_hashtable(int (*hash)(char *, int), int len)` | Alloue et initialise une nouvelle table de hachage de capacité `len` avec un pointeur de fonction de hachage. | $O(len)$ |
| `void delete_hashtable(hashtable_t *ht)` | Libère intégralement la table de hachage, l'ensemble de ses compartiments (*buckets*) et nœuds alloués. | $O(N + len)$ |
| `int ht_insert(hashtable_t *ht, char *key, char *value)` | Insère ou met à jour la valeur associée à la clé `key`. Retourne 0 en cas de succès, 84 en cas d'erreur. | $O(1)$ |
| `int ht_delete(hashtable_t *ht, char *key)` | Supprime l'entrée correspondant à la clé `key` de la table. | $O(1)$ |
| `char *ht_search(hashtable_t *ht, char *key)` | Recherche et retourne la valeur associée à la clé `key`, ou `NULL` si la clé est absente. | $O(1)$ |
| `void ht_dump(hashtable_t *ht)` | Affiche le contenu détaillé de chaque alvéole et liste chaînée pour faciliter le débogage. | $O(N + len)$ |
| `int hash(char *key, int len)` | Fonction de hachage par défaut distribuant uniformément les clés textuelles sur les alvéoles de la table. | $O(length(key))$ |

---

## 🛠️ Compilation & Intégration

```bash
make        # Génère la bibliothèque statique 'libhashtable.a'
make clean  # Nettoie les fichiers intermédiaires
make fclean # Supprime les bibliothèques et objets
make re     # Recompile la bibliothèque
```

---

## 💡 Exemple d'Utilisation

```c
#include "hashtable.h"
#include <stdio.h>

int main(void)
{
    // Création d'une table avec 10 alvéoles
    hashtable_t *ht = new_hashtable(&hash, 10);
    if (!ht)
        return 84;

    // Insertion de paires clé / valeur
    ht_insert(ht, "Vision", "./assets/vision.png");
    ht_insert(ht, "Kwh", "450");

    // Recherche
    char *value = ht_search(ht, "Vision");
    printf("Valeur trouvée : %s\n", value);

    // Affichage structurel
    ht_dump(ht);

    // Nettoyage
    delete_hashtable(ht);
    return 0;
}
```
