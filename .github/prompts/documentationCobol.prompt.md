---
name: documentationCobol
description: Générer une documentation développeur complète et professionnelle pour un programme COBOL mainframe ou GnuCOBOL
---

# Prompt : Documentation Développeur COBOL

## Objectif
Générer une documentation technique et développeur de qualité professionnelle pour un programme COBOL donné. La documentation doit être exploitable par des développeurs mainframe, faciliter la maintenance et la collaboration.

## Instructions

### 1. Analyser le programme COBOL
- Identifier la structure (IDENTIFICATION, ENVIRONMENT, DATA, PROCEDURE)
- Lister tous les fichiers d'entrée/sortie (SELECT ... ASSIGN)
- Identifier les copybooks utilisés
- Relever les sections/paragraphes principaux
- Documenter les variables importantes (WS-*, FD-*, LS-*)
- Identifier les appels de sous-programmes (CALL)
- Relever les appels DB2/CICS/IMS si présents

### 2. Sections obligatoires

#### 2.1 En-tête et résumé (50-100 mots)
- **Program ID** : [à extraire du PROGRAM-ID]
- **Objectif** : description brève du rôle
- **Environnement** : Batch / CICS / IMS / Mixte
- **Version** : numéro de version (ex: 1.5.2)
- **Date de dernière modification** : [date]
- **Auteur(s)** : [noms]

#### 2.2 Description fonctionnelle détaillée
- Expliquer le flux de traitement principal étape par étape
- Décrire chaque flux de données (entrée → traitement → sortie)
- Lister les règles métier appliquées
- Identifier les cas nominaux et cas d'exception
- Documenter les calculs/transformations clés

#### 2.3 Fichiers et datasets
Pour chaque fichier accédé:
- **Nom logique** (SELECT) et **nom physique** (ASSIGN)
- **Organisation** : Sequential / Indexed / Relative
- **Record format** : [ex: 80 caractères]
- **Copybook** associé (s'il existe)
- **Mode d'accès** : INPUT / OUTPUT / I-O
- Exemple d'enregistrement (si pertinent)

#### 2.4 Sous-programmes appelés (CALL)
Pour chaque CALL détecté:
- **Nom du sous-programme** (PROGRAM-ID appelé)
- **Description rapide** de son rôle
- **Paramètres passés** (USING clause)
- **Valeur retour** (RETURN-CODE expecté)

#### 2.5 Appels externes (DB2/CICS/IMS)
Si le programme utilise:
- **DB2** : lister les tables accédées, SQL statements clés
- **CICS** : lister les commandes CICS (SEND MAP, RECEIVE, etc.)
- **IMS** : lister les appels DL/I (GU, ISRT, REPL, DLET)
- **MQ** : lister les queues accédées)

#### 2.6 Copybooks utilisés
Pour chaque copybook:
- **Nom** (ex: CP-EMPLOYEE-RECORD.CPY)
- **Localisation** (ex: SYSLIB)
- **Description** : structures de données incluses

#### 2.7 Variables principales
Tableau avec:
- **Variable Name** (ex: WS-EMPLOYEE-ID)
- **Type** (PIC clause)
- **Description** : rôle/usage
- **Initial Value** : valeur par défaut

#### 2.8 Codes de sortie (RETURN-CODE)
Tableau avec:
- **Code** (0, 4, 8, 12, etc.)
- **Meaning** : description
- **Cause** : quand/pourquoi ce code est retourné
- **Action** : que faire en cas de ce code

#### 2.9 Gestion d'erreurs
- Actions en cas de fichier non trouvé
- Actions en cas d'erreur DB2/CICS/IMS
- Actions en cas de données invalides
- Logging/traçage disponibles

#### 2.10 Paramètres et configuration
- Paramètres JCL (PARM=...)
- Variables d'environnement utilisées
- Fichiers de configuration

#### 2.11 Exécution et exemples JCL
Fournir un exemple de JCL pour lancer le programme:
```jcl
//PAYROLL  JOB CLASS=A,PRTY=5
//STEP1    EXEC PGM=pgm-payroll-calc
//INPUT    DD DSNAME=PAYROLL.MASTER,DISP=SHR
//OUTPUT   DD DSNAME=PAYROLL.REPORT,DISP=(NEW,CATLG)
//SYSOUT   DD SYSOUT=*
```

#### 2.12 Limitations et dépendances
- Taille maximale des fichiers supportée
- Dépendances vers autres programmes
- Prérequis (tables DB2 existantes, copybooks, etc.)

#### 2.13 Historique des modifications (changelog)
Tableau:
- **Version** | **Date** | **Auteur** | **Modification** | **Raison**

#### 2.14 Notes pour la maintenance
- Points critiques à surveiller
- Problèmes connus
- Améliorations futures suggérées
- Contacts mainteneur

#### 2.15 Références et liens
- Documentation métier associée
- Liens vers copybooks/sous-programmes
- Jira/tickets relatifs
- Doc mainframe relevant (VSAM, DB2, CICS, etc.)

### 3. Format et style

**Langage**
- Français : clair, précis, sans jargon inutile
- Une phrase par ligne pour lisibilité
- Exemples concrets toujours fournis

**Mise en forme**
- Titres hiérarchisés (# ## ###)
- Listes à puces/numérotées quand pertinent
- Tableaux Markdown pour données structurées
- Code blocks avec ```cobol pour snippets
- Gras **important**, italique pour termes techniques

**Métrique**
- Documentation globale : 500-2000 mots (selon complexité)
- Exemples : 3-5 obligatoires minimum
- Pas de copier-coller du code : toujours paraphraser

### 4. Exemple de sortie structurée

```markdown
---
Program-ID: pgm-payroll-calc
Version: 2.1.0
Environment: Batch z/OS
---

# Documentation - Programme de Calcul Paie

## 1. Résumé
Ce programme batch traite la paie mensuelle. Il lit le fichier maître employés, applique les règles de calcul (brut, cotisations, net), et génère un rapport de paie avec récapitulatif.

## 2. Flux de traitement
1. Initialisation (ouverture fichiers, variables)
2. Lecture employés du fichier MASTER
3. Pour chaque employé:
   - Valider ID et département
   - Consulter salaire en DB2
   - Calculer brut + cotisations
   - Écrire ligne rapport
4. Clôture (fermeture fichiers, affichage statistiques)

## 3. Fichiers

| Fichier | Mode | Copybook | Description |
|---------|------|----------|-------------|
| PAYROLL.MASTER | INPUT | CP-EMP-RECORD | Employés actifs |
| PAYROLL.REPORT | OUTPUT | - | Rapport paie généré |

... (suite)
```

### 5. Checklist de complétude

Avant de soumettre la documentation, vérifier:
- [ ] Résumé clair et court (< 100 mots)
- [ ] Description fonctionnelle complète (toutes étapes expliquées)
- [ ] Tous les fichiers documentés
- [ ] Tous les sous-programmes/appels listés
- [ ] Codes de retour exhaustifs
- [ ] Exemple JCL fourni
- [ ] Tableau des variables principales
- [ ] Gestion d'erreurs couverte
- [ ] Historique de modifications (changelog)
- [ ] Pas de jargon sans définition
- [ ] URLs/références actives (le cas échéant)
- [ ] Formatage Markdown cohérent

### 6. En cas de programme complexe

Pour les programmes > 1000 lignes:
- Découper en plusieurs sections logiques
- Ajouter table des matières (TOC) en début
- Fournir diagramme de flux (texte ou Mermaid)
- Annexes pour détails (SQL complets, CICS maps, etc.)

---

## Comment utiliser ce prompt

**Utilisateur fournit** :
- Code source program COBOL (complet ou excerpt)
- Contexte métier (paie? inventaire? facturation?)
- Copybooks associés (si jugés pertinents)

**Réponse attendue** :
- Documentation professionnelle Markdown selon structure ci-dessus
- Prête à intégrer dans wiki d'entreprise, Confluence, ou repo
- Exploitable par développeurs mainframe sans effort supplémentaire
