# 🛡️ Secured — Generic Hash Table Implementation in C

[![Academic Year](https://img.shields.io/badge/Epitech-Tek1-blue?style=for-the-badge&logo=epitech&logoColor=white)](https://www.epitech.eu/)
[![Module](https://img.shields.io/badge/Module-B--CPE--110-informational?style=for-the-badge)](#)
[![Language](https://img.shields.io/badge/Language-C-00599C?style=for-the-badge&logo=c&logoColor=white)](#)

## 📘 Description
**Secured** est une bibliothèque C implémentant une table de hachage associative générique haute performance. Elle propose une gestion dynamique des alvéoles mémoire et une résolution des collisions par chaînage.

## ⚙️ Fonctionnalités de l'API
- `ht_create` : Initialisation de la table avec fonction de hachage personnalisée.
- `ht_destroy` : Libération propre de l'intégralité des nœuds et données allouées.
- `ht_insert` : Insertion d'une paire clé/valeur avec gestion des collisions.
- `ht_search` : Recherche en temps moyen `O(1)`.
- `ht_delete` : Suppression et restructuration des chaînes de collision.

## 🔨 Compilation
```bash
make
# Produit libhashtable.a
```
