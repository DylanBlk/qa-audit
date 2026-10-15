# Audit qualité de QuickOrder — quality-audit-team-X

- Membre : Dylan Hamadouche
- Application auditée : QuickOrder V3.1 — https://github.com/amine-el-amrani/quickorder-qa-project/tree/master
- Période de la campagne : 15/10/2026
- Environnement : QuickOrder lancé en local avec Docker Compose (http://127.0.0.1:5000), API testée dans Swagger (http://127.0.0.1:5000/docs/)

## Objectif

Évaluer la qualité de QuickOrder avant sa mise en production, trouver et prouver les anomalies, puis recommander Go ou No-Go.

## Décision : ❌ No-Go

4 bugs critiques restent ouverts sur les parcours vitaux (stock, restaurant fermé, paiement en espèces). L'application peut vendre ce qu'elle ne peut pas livrer et valider des paiements incomplets.

## Résultats en bref

| Indicateur | Valeur |
|---|---|
| Cas de test exécutés | 24 / 24 |
| Pass | 16 (66,7 %) |
| Fail | 8 (33,3 %) |
| Blocked / Skipped | 0 / 0 |
| Bugs documentés | 10 (4 critiques, 5 majeurs, 1 mineur) |
| Tests utilisateurs | 3 scénarios, 2 participants |
| Améliorations proposées | 10 |

## Livrables

| Livrable | Fichier |
|---|---|
| Stratégie de test | [docs/test-strategy.md](docs/test-strategy.md) |
| Matrice des risques | [docs/risk-matrix.md](docs/risk-matrix.md) |
| Cas de test (24) | [docs/test-cases.xlsx](docs/test-cases.xlsx) |
| Rapport d'exécution et Go / No-Go | [docs/execution-report.md](docs/execution-report.md) |
| Bug reports (10) et preuves | [docs/bug-reports/](docs/bug-reports/) |
| Tests utilisateurs | [docs/user-feedback.md](docs/user-feedback.md) |
| Plan d'amélioration | [docs/improvement-plan.md](docs/improvement-plan.md) |

## Bugs

| ID | Titre | Sévérité | Priorité |
|---|---|---|---|
| [BUG-01](docs/bug-reports/BUG-01.md) | Docker Compose échoue sur Mac (script non exécutable) | Majeure | Haute |
| [BUG-02](docs/bug-reports/BUG-02.md) | Docker Compose échoue sous Windows (fins de ligne CRLF) | Majeure | Haute |
| [BUG-03](docs/bug-reports/BUG-03.md) | Commande possible au-delà du stock | Critique | Haute |
| [BUG-04](docs/bug-reports/BUG-04.md) | Produit hors stock ajoutable et commandable | Critique | Haute |
| [BUG-05](docs/bug-reports/BUG-05.md) | Commande possible dans un restaurant fermé | Critique | Haute |
| [BUG-06](docs/bug-reports/BUG-06.md) | Téléphone accepté dans n'importe quel format | Mineure | Moyenne |
| [BUG-07](docs/bug-reports/BUG-07.md) | Paiement en espèces insuffisant accepté (API) | Critique | Haute |
| [BUG-08](docs/bug-reports/BUG-08.md) | Coupon validé avec un sous-total falsifié (API) | Majeure | Haute |
| [BUG-09](docs/bug-reports/BUG-09.md) | Minimum de commande non respecté | Majeure | Haute |
| [BUG-10](docs/bug-reports/BUG-10.md) | Coupon ATLAS15 : 10 % appliqués au lieu de 15 % | Majeure | Moyenne |

## Lancer QuickOrder pour rejouer les tests

```bash
git clone -c core.autocrlf=false https://github.com/amine-el-amrani/quickorder-qa-project.git
cd quickorder-qa-project
docker compose up --build
```

Comptes de démo : `alice@example.com` / `Password123!` · admin `admin@quickorder.local` / `Admin123!` · clé API Swagger `quickorder-demo-key`.
Pour repartir d'une base propre : `docker compose down -v` puis `docker compose up --build`.

Le code de QuickOrder n'a pas été modifié pendant la campagne.
