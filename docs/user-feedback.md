# Tests utilisateurs — QuickOrder
## 7.1 Participants

| ID | Profil (âge, métier, aisance numérique) | Habitude des apps de livraison | Date / durée |
|---|---|---|---|
| U1 | Femme, 45 ans, assistante administrative, aisance numérique moyenne | Commande environ 1 fois par mois | 15/10/2026 — 20 min |
| U2 | Homme, 22 ans, étudiant, très à l'aise avec le numérique | Commande chaque semaine | 15/10/2026 — 10 min |

## 7.2 Scénarios

| ID | Mission donnée à l'utilisateur | Critère de réussite |
|---|---|---|
| S1 | Commandez un plat végétarien et payez par carte. | Commande confirmée sans aide. |
| S2 | Utilisez le code promo WELCOME10 sur une commande. | Réduction visible au total. |
| S3 | Annulez votre dernière commande. | Statut « annulée » affiché. |

## 7.3 Résultats par scénario

| Scénario | Participant | Réussi ? | Temps | Nb d'hésitations / erreurs |
|---|---|---|---|---|
| S1 | U1 | Oui | 4 min | 2 (filtre végétarien, produit hors stock) |
| S1 | U2 | Oui | 1 min 30 | 0 |
| S2 | U1 | Oui | 3 min | 2 (champ du code promo cherché dans le panier) |
| S2 | U2 | Oui | 1 min | 1 (minimum du coupon découvert après l'erreur) |
| S3 | U1 | Oui | 2 min | 1 (statut « cancelled » mal compris) |
| S3 | U2 | Oui | 40 s | 0 |

## 7.4 Problèmes observés

Observation O1

| Champ | Valeur |
|---|---|
| Profil | U1 — aisance moyenne |
| Contexte (scénario) | S1 — plat végétarien |
| Problème | Elle ajoute le Quinoa Bowl marqué « HORS STOCK » : il entre quand même dans le panier. |
| Fréquence (x / nb participants) | 1 / 2 |
| Impact | ☒ Bloquant   ☐ Gênant   ☐ Mineur |
| Verbatim (citation exacte) | « C'est marqué hors stock mais il est dans mon panier, il va arriver ou pas ? » |
| Hypothèse d'amélioration | Désactiver le bouton « Ajouter » quand le stock est à 0. |
| Priorité | ☒ Haute   ☐ Moyenne   ☐ Basse |

Observation O2

| Champ | Valeur |
|---|---|
| Profil | U1 et U2 |
| Contexte (scénario) | S2 — code promo |
| Problème | Le champ du code promo n'existe qu'au checkout : les deux utilisateurs le cherchent d'abord dans le panier. |
| Fréquence (x / nb participants) | 2 / 2 |
| Impact | ☐ Bloquant   ☒ Gênant   ☐ Mineur |
| Verbatim (citation exacte) | « Je cherchais où mettre le code dans le panier. » |
| Hypothèse d'amélioration | Afficher le champ du code promo dès le panier. |
| Priorité | ☐ Haute   ☒ Moyenne   ☐ Basse |

Observation O3

| Champ | Valeur |
|---|---|
| Profil | U1 et U2 |
| Contexte (scénario) | S3 — annulation |
| Problème | Les statuts de commande sont en anglais (« confirmed », « cancelled »). |
| Fréquence (x / nb participants) | 2 / 2 |
| Impact | ☐ Bloquant   ☒ Gênant   ☐ Mineur |
| Verbatim (citation exacte) | « C'est écrit cancelled, donc c'est bien annulé ? » |
| Hypothèse d'amélioration | Traduire les statuts en français. |
| Priorité | ☐ Haute   ☒ Moyenne   ☐ Basse |

Observation O4

| Champ | Valeur |
|---|---|
| Profil | U2 — très à l'aise |
| Contexte (scénario) | S2 — code promo |
| Problème | Le minimum de 20 € du coupon n'est indiqué qu'après le message d'erreur. |
| Fréquence (x / nb participants) | 1 / 2 |
| Impact | ☐ Bloquant   ☐ Gênant   ☒ Mineur |
| Verbatim (citation exacte) | « J'aurais aimé savoir avant qu'il fallait 20 €. » |
| Hypothèse d'amélioration | Afficher les conditions du coupon (minimum, plafond) près du champ. |
| Priorité | ☐ Haute   ☐ Moyenne   ☒ Basse |

Observation O5

| Champ | Valeur |
|---|---|
| Profil | U1 — aisance moyenne |
| Contexte (scénario) | S1 — plat végétarien |
| Problème | Elle ne trouve pas tout de suite le filtre « végétarien » sur l'accueil. |
| Fréquence (x / nb participants) | 1 / 2 |
| Impact | ☐ Bloquant   ☐ Gênant   ☒ Mineur |
| Verbatim (citation exacte) | « Je ne vois pas comment voir seulement les plats végétariens. » |
| Hypothèse d'amélioration | Rendre le filtre végétarien plus visible (bouton en haut de la liste). |
| Priorité | ☐ Haute   ☐ Moyenne   ☒ Basse |
