# ChangeLog — RecuDon

## [1.0.2] — 2026-05-24

### Corrections
- `modRecuDon.class.php` : `$this->editor_url` restauré à `https://github.com/Barnecki`

---


## [1.0.1] — 2026-05-22

### Conformité ModuleBuilder
- `modRecuDon.class.php` : mise en conformité complète avec le template ModuleBuilder BARNECKI SPIRITS :
  - Ajout des balises `/* BEGIN/END MODULEBUILDER HOOKSCONTEXTS */`, `/* END MODULEBUILDER TABS */`, `/* BEGIN/END MODULEBUILDER DICTIONARIES */`, `/* BEGIN/END MODULEBUILDER PERMISSIONS */`, `/* BEGIN/END MODULEBUILDER MENUS */`
  - `module_parts` complété : toutes les clés du template présentes (`triggers`, `login`, `substitutions`, `menus`, `tpl`, `barcode`, `printing`, `theme`, `css`, `js`, `moduleforexternal`, `websitetemplates`, `captcha`)
  - `$this->hidden` : utilise `getDolGlobalInt('MAIN_MODULE_RECUDON_DISABLED')` au lieu de `false`
  - Ajout de `$this->need_javascript_ajax = 0`
  - Ajout de `$this->warnings_activation` et `$this->warnings_activation_ext`
  - Ajout de `$this->editor_squarred_logo = ''`
  - `$this->editor_url` corrigé en `www.barnecki-spirits.com`
  - `$this->module_position` en string `'501'` (conforme au template)
  - Ajout du bloc `if (!isModEnabled('recudon'))` avec `$conf->recudon`

---


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
- Compatibilité Dolibarr 21+ / PHP 8.0+
