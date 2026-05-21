# ChangeLog — RecuDons

## [0.1.0] — 2026-05-21

### Version initiale

Premier module stable de generation de recus de dons au format PDF pour Dolibarr 14+.

**Fonctionnalites incluses :**
- Modele PDF `pdf_recudon` integre dans le selecteur natif Dolibarr (section Documents de la fiche don)
- En-tete : logo et coordonnees lus depuis *Configuration > Ma societe*
- Bloc donateur avec resolution automatique : tiers lie (fk_soc) > champ societe > prenom/nom
- Tableau de paiement : date, mode de reglement, montant en devise, reference du don
- Bloc signature avec ville et nom du signataire configurables via constantes (`RECUDON_VILLE_SIGNATURE`, `RECUDON_PRESIDENT`)
- Stockage du PDF dans `documents/don/<id>/` selon la convention Dolibarr
- Support multi-entite Dolibarr
- ID module : 250001

---

## [0.1.1] — 2026-05-21

### Corrections
- Génération du ZIP : suppression des anciens ZIPs avant recréation, lecture propre de VERSION avec `tr -d '[:space:]'` pour éviter les caractères résiduels dans le nom du fichier
