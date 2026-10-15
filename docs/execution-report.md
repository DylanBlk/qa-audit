# Rapport d'exécution — QuickOrder
## Journal de campagne

| Date | Testeur | Cas exécutés | Outils (navigateur, DevTools, Swagger, Postman) | Remarques |
|---|---|---|---|---|
| 15/10/2026 | Équipe QA | TC-NOM-01 à TC-RM-06 (24 cas) | Chrome, DevTools (Network), Swagger | Base réinitialisée avant la campagne. Bugs rejoués 2 fois. |

### Inventaire des preuves

| Fichier | Type (capture, vidéo, console, requête API) | Cas / bug lié | Description |
|---|---|---|---|
| Capture terminal (dans BUG-01) | Capture console | BUG-01 | Erreur Docker sur Mac |
| BUG-03-panier / commande | Captures | TC-LIM-01 / BUG-03 | Salmon Bowl × 10 commandé |
| BUG-04-produit / commande | Captures | TC-RM-01 / BUG-04 | Veggie Burger hors stock commandé |
| BUG-05-restaurant / commande | Captures | TC-RM-02 / BUG-05 | Commande chez Night Sushi fermé |
| BUG-06-telephone | Capture | TC-ERR-01 / BUG-06 | Téléphone « 06 » enregistré |
| BUG-07-swagger-cash | Requête / réponse API | TC-RM-03 / BUG-07 | Réponse 201, change_due -25.79 |
| BUG-08-swagger (2 captures) | Requête / réponse API | TC-ERR-02 / BUG-08 | Sous-total 25 refusé, 1000 accepté |
| BUG-09-checkout / commande | Captures | TC-LIM-05 / BUG-09 | Commande de 3,50 € sous le minimum |
| BUG-10-promo / checkout | Captures | TC-RM-06 / BUG-10 | ATLAS15 : 10 % au lieu de 15 % |

## Analyse de campagne

### 6.1 Résultats chiffrés

| Indicateur | Nombre | % |
|---|---|---|
| Tests exécutés / prévus | 24 / 24 | 100 % |
| Pass | 16 | 66,7 % |
| Fail | 8 | 33,3 % |
| Blocked | 0 | 0 % |
| Skipped | 0 | 0 % |
| Total | 24 | 100 % |

### 6.2 Répartition par catégorie

| Catégorie | Pass | Fail | Blocked | Skipped |
|---|---|---|---|---|
| Nominal | 6 | 0 | 0 | 0 |
| Limite | 4 | 2 | 0 | 0 |
| Erreur | 4 | 2 | 0 | 0 |
| Règle métier | 2 | 4 | 0 | 0 |

### 6.3 Bugs par sévérité

| Sévérité | Nombre | ID des bugs |
|---|---|---|
| Critique | 4 | BUG-03, BUG-04, BUG-05, BUG-07 |
| Majeure | 5 | BUG-01, BUG-02, BUG-08, BUG-09, BUG-10 |
| Mineure | 1 | BUG-06 |
| Cosmétique | 0 | — |

### 6.4 Principaux risques restants

| Risque (matrice) | Bugs associés | Conséquence pour l'entreprise |
|---|---|---|
| R1 — Stock | BUG-03, BUG-04 | Plats vendus mais impossibles à livrer, clients mécontents |
| R3 — Paiement | BUG-07 | Commandes payées sans recevoir l'argent : perte directe |
| R4 — Coupons | BUG-08, BUG-10 | Réductions injustifiées ou promesse non tenue |
| R2 / R5 — Commande | BUG-05, BUG-09 | Commandes non préparées ou non rentables |
| R9 — Installation | BUG-01, BUG-02 | Équipe bloquée pour installer l'application |

### 6.5 Recommandation

Go / No-Go

| Champ | Valeur |
|---|---|
| Décision | ☐ Go     ☐ Go avec réserves     ☒ No-Go |
| Argumentation (critères de la section 1.7) | 8 tests sur 24 échouent (33 %), dont 6 sur des parcours critiques.<br>4 bugs critiques sont ouverts (stock, restaurant fermé, paiement en espèces) : le critère No-Go est atteint. |
| Conditions pour passer en Go | Corriger et revalider les 4 bugs critiques et les bugs majeurs BUG-08 et BUG-09.<br>Rejouer les 8 cas en échec : tous doivent passer. |
