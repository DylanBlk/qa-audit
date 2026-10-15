# Plan d'amélioration — QuickOrder
Améliorations classées par priorité. Origine : bug report (BUG) ou observation des tests utilisateurs (O).

| # | Amélioration | Origine (BUG / O) | Justification | Effort | Priorité |
|---|---|---|---|---|---|
| A1 | Contrôler le stock à l'ajout, au panier, au checkout et dans l'API | BUG-03, BUG-04 | Évite de vendre des plats impossibles à livrer | Faible | Haute |
| A2 | Bloquer les commandes quand le restaurant est fermé | BUG-05 | Le restaurant ne peut pas préparer la commande | Faible | Haute |
| A3 | Refuser un paiement en espèces inférieur au total | BUG-07 | Perte d'argent directe | Faible | Haute |
| A4 | Calculer le sous-total du coupon côté serveur | BUG-08 | Empêche de tricher sur les coupons | Faible | Haute |
| A5 | Appliquer le minimum de commande au checkout | BUG-09 | Commandes trop petites non rentables | Faible | Haute |
| A6 | Mettre le coupon ATLAS15 à 15 % (ou corriger l'annonce) | BUG-10 | Promesse affichée au client non tenue | Faible | Moyenne |
| A7 | Vérifier le format du téléphone (10 chiffres ou +33) | BUG-06 | Le livreur doit pouvoir joindre le client | Faible | Moyenne |
| A8 | Corriger le lancement Docker (script exécutable, fins de ligne LF) | BUG-01, BUG-02 | Installation bloquée sur Mac et Windows | Faible | Moyenne |
| A9 | Traduire les statuts de commande en français | Tests utilisateurs O3 | 2 utilisateurs sur 2 n'ont pas compris « cancelled » | Faible | Moyenne |
| A10 | Afficher le champ code promo et ses conditions dès le panier | Tests utilisateurs O2, O4 | 2 utilisateurs sur 2 ont cherché le champ dans le panier | Faible | Moyenne |
