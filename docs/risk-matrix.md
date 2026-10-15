# Matrice des risques — QuickOrder
Probabilité et impact notés de 1 (faible) à 3 (fort). Score = Probabilité × Impact. 6 à 9 : Haute · 3 à 4 : Moyenne · 1 à 2 : Basse.

| ID | Risque | Zone | Prob. (1-3) | Impact (1-3) | Score | Priorité |
|---|---|---|---|---|---|---|
| R1 | Vente d'un produit épuisé ou au-delà du stock | Panier / commande | 3 | 3 | 9 | Haute |
| R2 | Commande dans un restaurant fermé | Commande | 2 | 3 | 6 | Haute |
| R3 | Paiement validé sans recevoir tout l'argent | Paiement | 2 | 3 | 6 | Haute |
| R4 | Coupon détourné ou réduction fausse | Coupons | 2 | 3 | 6 | Haute |
| R5 | Minimum de commande non respecté | Commande | 2 | 2 | 4 | Moyenne |
| R6 | Client qui accède à l'espace admin | Sécurité | 1 | 3 | 3 | Moyenne |
| R7 | Données de profil invalides | Profil | 2 | 2 | 4 | Moyenne |
| R8 | API utilisable sans clé | API | 1 | 3 | 3 | Moyenne |
| R9 | Installation impossible (Docker) | Installation | 2 | 2 | 4 | Moyenne |
| R10 | Recherche ou tri incorrect | Catalogue | 2 | 1 | 2 | Basse |

## Vue synthétique

| Impact ↓ / Probabilité → | 1 – Faible | 2 – Moyenne | 3 – Forte |
|---|---|---|---|
| 3 – Fort | R6, R8 | R2, R3, R4 | R1 |
| 2 – Moyen |  | R5, R7, R9 |  |
