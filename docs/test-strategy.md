# Stratégie de test — QuickOrder
## 1.1 Contexte et objectif de l'audit

QuickOrder est une application web de commande de repas (Flask, SQLite) avec une API REST.

L'objectif de l'audit est de vérifier sa qualité avant la mise en production, de trouver et prouver les anomalies, puis de recommander Go ou No-Go.

## 1.2 Périmètre

- Inscription, connexion, déconnexion
- Recherche, filtres et tri des restaurants
- Fiche restaurant et menu
- Panier (ajout, quantité, suppression, mono-restaurant)
- Coupons (minimum, expiration, plafond)
- Checkout et paiement simulé (carte, PayPal, espèces)
- Suivi et annulation de commande
- Profil et adresses
- Espace administrateur (contrôle d'accès)
- API REST via Swagger (clé, codes HTTP, réponses JSON)

## 1.3 Hors périmètre

| Élément non testé | Raison |
|---|---|
| Performance et montée en charge | Pas d'outil ni d'environnement dédié |
| Vrai paiement bancaire | Le paiement est simulé |
| Application mobile | QuickOrder n'existe qu'en version web |
| Tests de sécurité avancés (intrusion) | Hors des objectifs du cours |
| Compatibilité tous navigateurs | Campagne réalisée sur Chrome uniquement |

## 1.4 Parcours critiques

| # | Parcours (enchaînement d'étapes) | Pourquoi il est critique |
|---|---|---|
| P1 | Connexion → choix d'un restaurant → panier → paiement → commande confirmée | C'est le parcours qui fait gagner de l'argent |
| P2 | Appliquer un coupon au checkout | Risque de perte d'argent si la réduction est fausse |
| P3 | Payer (carte, PayPal, espèces) | Une commande ne doit être payée que si l'argent est reçu |
| P4 | Annuler une commande | Un client doit pouvoir annuler, et seulement quand c'est permis |
| P5 | Respect du stock et de l'ouverture du restaurant | Sinon on vend des plats impossibles à livrer |
| P6 | Accès à l'admin et à l'API | Un client ne doit pas accéder aux fonctions réservées |

## 1.5 Risques identifiés

- Vente d'un produit épuisé ou au-delà du stock
- Commande dans un restaurant fermé
- Paiement validé sans recevoir tout l'argent
- Coupon détourné ou réduction mal calculée
- Minimum de commande non respecté
- Client qui accède à l'espace admin

## 1.6 Types de tests

| Type de test | Ce qu'on vérifie | Outil |
|---|---|---|
| Fonctionnel | Les fonctionnalités font ce qu'elles doivent | Navigateur |
| Limites | Valeurs au bord : minimum exact, plafond, quantité 0, stock | Navigateur |
| Erreurs | Saisies invalides refusées avec un message clair | Navigateur, Swagger |
| Règles métier | Stock, restaurant fermé, coupons, paiement | Navigateur, Swagger |
| API REST | Codes HTTP, réponses JSON, clé API | Swagger |
| Sécurité de base | Accès admin et API sans autorisation | Navigateur, Swagger |
| Utilisabilité | Facilité d'usage pour de vrais utilisateurs | Tests utilisateurs |

## 1.7 Priorisation et critères Go / No-Go

Critères de décision

| Champ | Valeur |
|---|---|
| Go | Tous les tests des parcours critiques passent, aucun bug critique ou majeur ouvert. |
| Go avec réserves | Aucun bug critique ; les bugs majeurs restants ont un contournement. |
| No-Go | Au moins un bug critique reste ouvert sur un parcours critique. |

## 1.8 Organisation de l'équipe

| Membre | Zone / livrables pris en charge |
|---|---|
| Dylan Hamadouche | Tous les livrables : stratégie, cas de test, campagne, bugs, analyse, tests utilisateurs, plan d'amélioration |
