# ChangeLog — RecuDon

## [1.0.0] — 2026-05-22

### Version initiale stable

Premier module stable de génération de reçus de dons au format PDF pour Dolibarr 21+.

**Fonctionnalités incluses :**
- Modèle PDF `pdf_recudon` intégré dans le sélecteur natif Dolibarr (section Documents de la fiche don)
- Bouton **"Reçu PDF"** dans la barre d'actions de la fiche don (visible uniquement aux statuts "Promesse validée" et "Don payé")
- En-tête : logo, coordonnées, SIRET et TVA lus depuis *Configuration > Ma société*
- Bloc donateur avec résolution automatique : tiers lié (`fk_soc`) > champ societe > prénom/nom
- Adresse et identifiants fiscaux (SIRET, TVA) du donateur lus depuis la fiche tiers si lié
- Tableau de paiement : date, mode de règlement, montant en devise, référence du don
- Bloc signature : ville et nom du signataire configurables via constantes (`RECUDON_VILLE_SIGNATURE`, `RECUDON_PRESIDENT`), nom/prénom/poste du gestionnaire connecté
- Pied de page : version Dolibarr et version du module
- Stockage du PDF dans `documents/don/<id>/` selon la convention Dolibarr
- Support multi-entité Dolibarr
- ID module : 250001
- Compatibilité Dolibarr 21+ / PHP 7.4+
