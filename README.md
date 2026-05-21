# RecuDons — Module Dolibarr

**Editeur :** [BARNECKI SPIRITS](https://github.com/Barnecki)  
**Depot :** [https://github.com/Barnecki/recudon](https://github.com/Barnecki/recudon)  
**Version :** 0.1.4
**Compatibilite :** Dolibarr 21+  
**Licence :** GPL v3

---

## Description

Module Dolibarr ajoutant la generation de **recus de dons au format PDF** au module Don natif.  
Le document reprend l'en-tete de la societe (logo, coordonnees), les informations du donateur, le tableau de paiement (date, mode de reglement, montant, reference) et le bloc signature.

---

## Fonctionnalites

- **Modele PDF natif** : integre dans le selecteur de modeles de la section Documents de la fiche don (bouton standard Dolibarr)
- **En-tete** : logo et coordonnees lus depuis *Configuration > Ma societe* — aucun fichier a fournir dans le module
- **Bloc donateur** : resolution automatique depuis le tiers lie (fk_soc), le champ societe ou le prenom/nom
- **Tableau de paiement** : date, mode de reglement, montant en devise, reference du don
- **Signature** : ville et nom du signataire configurables via les constantes Dolibarr
- **Stockage** : PDF genere dans `documents/don/<id>/` selon la convention Dolibarr

---

## Installation

1. Decompresser le ZIP dans `htdocs/custom/`
2. Activer le module dans *Configuration > Modules > Finances > RecuDons*
3. Renseigner les constantes de signature (voir ci-dessous)

---

## Configuration

| Constante | Description | Defaut |
|---|---|---|
| `RECUDON_PRESIDENT` | Nom affiche sur la ligne de signature | Vide |
| `RECUDON_VILLE_SIGNATURE` | Ville affichee sur la ligne de signature | Vide |

Les constantes sont editables dans *Configuration > Constantes*.

Logo et coordonnees de l'organisation : lus depuis *Configuration > Ma societe*.

---

## Utilisation

Sur la fiche d'un don (*Don > liste > clic sur un don*) :

1. Aller en bas de page, section **Documents**
2. Selectionner le modele `recudon` si non pre-selectionne
3. Cliquer sur **Generer** — le PDF est cree et disponible immediatement

---

## Structure des fichiers

```
recudon/
├── ChangeLog.md                               Historique des versions
├── README.md                                  Ce fichier
├── VERSION                                    Version courante
├── modulebuilder.txt                          Marqueur ModuleBuilder Dolibarr
├── core/modules/
│   ├── modRecuDons.class.php                  Descripteur du module
│   └── dons/
│       └── pdf_recudon.modules.php            Generateur PDF TCPDF
└── langs/
    └── fr_FR/
        └── recudon.lang                       Traductions francais
```

---

## Verification des mises a jour

La derniere version disponible est consultable sur :  
[https://raw.githubusercontent.com/Barnecki/recudon/main/VERSION](https://raw.githubusercontent.com/Barnecki/recudon/main/VERSION)

---

## Licence

Ce module est distribue sous licence **GPL v3**.  
(c) 2026 BARNECKI SPIRITS — [https://github.com/Barnecki](https://github.com/Barnecki)
