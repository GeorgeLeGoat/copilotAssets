---
description: Instructions pour développer des programmes COBOL mainframe et GnuCOBOL
applyTo: '**/*.cbl, **/*.cob, **/*.cobol, **/*.jcl, **/*.cpy'
---

# Guide de développement COBOL

## 1. Structure générale d'un programme COBOL

Tout programme COBOL suit cette structure immuable:

```cobol
       IDENTIFICATION DIVISION.
           PROGRAM-ID. nom-programme.
           AUTHOR. votre-nom.
           DATE-WRITTEN. date.
           PURPOSE. description succincte.
       
       ENVIRONMENT DIVISION.
           INPUT-OUTPUT SECTION.
           FILE-CONTROL.
               SELECT input-file ASSIGN TO WS-INPUT-FILENAME
                   ORGANIZATION IS LINE SEQUENTIAL.
       
       DATA DIVISION.
           FILE SECTION.
               FD  input-file.
               01  input-record           PIC X(80).
       
           WORKING-STORAGE SECTION.
               01  WS-RETURN-CODE        PIC 9(4) VALUE ZEROS.
               01  WS-EOF-FLAG           PIC X VALUE 'N'.
       
       PROCEDURE DIVISION.
           MAIN-PROCEDURE.
               PERFORM INITIALIZATION.
               PERFORM PROCESS-FILES.
               PERFORM FINALIZATION.
               STOP RUN.
       
           INITIALIZATION.
               MOVE 'N' TO WS-EOF-FLAG.
               OPEN INPUT input-file.
       
           PROCESS-FILES.
               READ input-file
                   AT END MOVE 'Y' TO WS-EOF-FLAG
                   NOT AT END PERFORM PROCESS-RECORD
               END-READ.
       
           FINALIZATION.
               CLOSE input-file.
```

## 2. Conventions de nommage

### Variables
- **Format** : `PREFIX-DESCRIPTION` (majuscules, tirets comme séparateurs)
- **Préfixes réservés** :
  - `WS-` : Working-Storage (variables locales)
  - `LS-` : Local-Storage (variables persistantes dans CICS)
  - `FD-` : File Descriptor (enregistrements fichier)
  - `GD-` : Global Data (groupes partageables)
  - `CP-` : Linkage Section parameters
  - `IO-` : Entrées/sorties
  - `ERR-` : Codes/messages d'erreur
  - `CNT-` : Compteurs
  - `TMP-` : Variables temporaires

### Exemples
```cobol
01  WS-EMPLOYEE-NAME          PIC X(50).
01  WS-RECORD-COUNT           PIC 9(8) COMP-3.
01  WS-TOTAL-SALARY           PIC S9(11)V99 COMP-3.
01  ERR-FILE-NOT-FOUND        PIC 9(4) VALUE 2001.
```

### Programmes
- Format : `pgm-{domaine}-{fonction}.cbl`
- Exemples : `pgm-payroll-calc.cbl`, `pgm-inventory-audit.cbl`
- PROGRAM-ID en majuscules : `PGM-PAYROLL-CALC`

### Copybooks
- Format : `cp-{domaine}-{type}.cpy`
- Exemples : `cp-employee-record.cpy`, `cp-error-codes.cpy`

## 3. PICTURE clauses et types de données

Toujours être explicite sur le type et la longueur:

```cobol
       NUMERIC FIELDS
       01  WS-COUNTER            PIC 9(4).              *> 0-9999
       01  WS-SIGNED-AMOUNT      PIC S9(7)V99 COMP-3.  *> -9999999.99
       01  WS-DECIMAL            PIC 9(5)V9(3).         *> 99999.999
       
       ALPHANUM FIELDS
       01  WS-NAME               PIC X(30).             *> Chaîne fixe
       01  WS-VARIABLE-TEXT      PIC X(100).            *> Chaîne
       
       BOOLEAN-LIKE FLAGS
       01  WS-EOF-FLAG           PIC X VALUE 'N'.       *> 'Y' ou 'N'
       01  WS-ERROR-FLAG         PIC 9 VALUE 0.         *> 0=OK, 1=Error
```

**Nota Bene** :
- Toujours initialiser WITH VALUE en déclaration
- COMP vs COMP-3 : COMP pour binaire (perfs), COMP-3 pour packed-decimal (storage)
- Éviter PIC 9 sans taille explicite

## 4. Paragraphes et structure logique

**Naming** :
- Majuscules, tirets
- Verbe d'action en premier : `READ-FILE-RECORDS`, `CALCULATE-TOTALS`
- Grouper par logique métier

**Structure** :
```cobol
       PROCEDURE DIVISION.
       
       *> Point d'entrée principal
           MAIN-PROCEDURE.
               PERFORM 100-SETUP.
               PERFORM 200-PROCESS UNTIL WS-EOF-FLAG = 'Y'.
               PERFORM 300-CLEANUP.
               STOP RUN.
       
       *> Sections logiques numérotées (100s, 200s, 300s...)
       
           100-SETUP.
               PERFORM 110-OPEN-FILES.
               PERFORM 120-INITIALIZE-VARS.
       
           110-OPEN-FILES.
               OPEN INPUT master-file.
               OPEN OUTPUT report-file.
       
           120-INITIALIZE-VARS.
               MOVE 0 TO WS-RECORD-COUNT.
               MOVE 0 TO WS-TOTAL-AMOUNT.
       
           200-PROCESS.
               READ master-file
                   AT END MOVE 'Y' TO WS-EOF-FLAG
                   NOT AT END PERFORM 210-VALIDATE-RECORD
                              PERFORM 220-WRITE-REPORT
                   END-READ.
       
           210-VALIDATE-RECORD.
               IF master-key NOT NUMERIC
                   PERFORM 320-LOG-ERROR
               END-IF.
       
           220-WRITE-REPORT.
               MOVE record-data TO output-line.
               WRITE output-line.
               ADD 1 TO WS-RECORD-COUNT.
       
           300-CLEANUP.
               CLOSE master-file.
               CLOSE report-file.
               DISPLAY "Traitement terminé. Enregistrements: " 
                       WS-RECORD-COUNT.
```

## 5. Gestion d'erreurs et codes retour

**Codes de retour standard** :
- `0` : Succès
- `4` : Avertissement (traitement partiel)
- `8` : Erreur (traitement échoué)
- `12` : Erreur fatale (arrêt immédiat)

**Implémentation** :
```cobol
       IDENTIFICATION DIVISION.
           PROGRAM-ID. pgm-validation.
       
       PROCEDURE DIVISION.
           MAIN-PROCEDURE.
               PERFORM 100-VALIDATE.
               IF WS-RETURN-CODE NOT = 0
                   PERFORM 200-HANDLE-ERROR
                   GOBACK
               END-IF.
               PERFORM 300-PROCESS-DATA.
               STOP RUN.
       
           100-VALIDATE.
               IF input-file-name = SPACES
                   MOVE 8 TO WS-RETURN-CODE
                   MOVE "Fichier entrée obligatoire" TO WS-ERROR-MSG
                   PERFORM 250-LOG-ERROR
               END-IF.
       
           200-HANDLE-ERROR.
               EVALUATE WS-RETURN-CODE
                   WHEN 4
                       DISPLAY "AVERTISSEMENT: " WS-ERROR-MSG
                   WHEN 8
                       DISPLAY "ERREUR: " WS-ERROR-MSG
                   WHEN 12
                       DISPLAY "ERREUR FATALE: " WS-ERROR-MSG
                       STOP RUN RETURNING 12
               END-EVALUATE.
       
           250-LOG-ERROR.
               ACCEPT WS-CURRENT-TIME FROM DATE YYYYMMDD.
               DISPLAY "["WS-CURRENT-TIME"] CODE=" WS-RETURN-CODE
                       " MSG=" WS-ERROR-MSG.
```

## 6. Gestion des fichiers

### Fichiers séquentiels
```cobol
       ENVIRONMENT DIVISION.
           INPUT-OUTPUT SECTION.
           FILE-CONTROL.
               SELECT input-file ASSIGN TO WS-INPUT-FILENAME
                   ORGANIZATION IS LINE SEQUENTIAL.
       
       PROCEDURE DIVISION.
           READ-FILES.
               OPEN INPUT input-file.
               PERFORM UNTIL WS-EOF-FLAG = 'Y'
                   READ input-file INTO WS-RECORD
                       AT END MOVE 'Y' TO WS-EOF-FLAG
                       NOT AT END PERFORM PROCESS-RECORD
                   END-READ
               END-PERFORM.
               CLOSE input-file.
```

### Fichiers indexés (VSAM/KSDS)
```cobol
               SELECT emp-file ASSIGN TO WS-EMP-FILENAME
                   ORGANIZATION IS INDEXED
                   RECORD KEY IS emp-id
                   ALTERNATE RECORD KEY IS emp-name
                       WITH DUPLICATES.

       DATA DIVISION.
           FILE SECTION.
               FD  emp-file.
               01  emp-record.
                   05  emp-id             PIC 9(7).
                   05  emp-name           PIC X(30).
                   05  emp-salary         PIC 9(9)V99 COMP-3.

       PROCEDURE DIVISION.
           ACCESS-VSAM.
               OPEN I-O emp-file.
               *> Chercher par clé primaire
               MOVE "1234567" TO emp-id.
               READ emp-file INTO WS-EMPLOYEE
                   KEY IS emp-id
                   INVALID KEY
                       MOVE 8 TO WS-RETURN-CODE
                   NOT INVALID KEY
                       PERFORM UPDATE-EMPLOYEE
               END-READ.
               CLOSE emp-file.
```

### Gestion FILE STATUS
```cobol
           READ input-file
               AT END MOVE 'Y' TO WS-EOF-FLAG
               NOT AT END PERFORM PROCESS
           END-READ.
           
           IF FILE-STATUS-CODE NOT = "00"
               EVALUATE FILE-STATUS-CODE
                   WHEN "10"
                       DISPLAY "Fin de fichier atteinte"
                   WHEN "23"
                       DISPLAY "Enregistrement non trouvé"
                   WHEN "92"
                       DISPLAY "Erreur d'E/S fichier"
                   WHEN OTHER
                       DISPLAY "Erreur fichier: " FILE-STATUS-CODE
               END-EVALUATE
               MOVE 8 TO WS-RETURN-CODE
           END-IF.
```

## 7. Copybooks réutilisables

### cp-error-codes.cpy
```cobol
       *> Codes d'erreur standard
       01  ERROR-CODES.
           05  ERR-SUCCESS                PIC 9(4) VALUE 0.
           05  ERR-FILE-NOT-FOUND         PIC 9(4) VALUE 2001.
           05  ERR-INVALID-RECORD         PIC 9(4) VALUE 2002.
           05  ERR-DB2-ERROR              PIC 9(4) VALUE 3001.
           05  ERR-CALCULATION-ERROR      PIC 9(4) VALUE 4001.
```

### cp-employee-record.cpy
```cobol
       01  EMPLOYEE-RECORD.
           05  emp-id                     PIC 9(7).
           05  emp-first-name             PIC X(20).
           05  emp-last-name              PIC X(20).
           05  emp-hire-date              PIC 9(8).
           05  emp-salary                 PIC 9(9)V99 COMP-3.
           05  emp-department             PIC X(6).
```

## 8. Patterns courants

### Pattern : Accumulateur
```cobol
       01  WS-TOTAL-SALES                PIC 9(11)V99 COMP-3 VALUE 0.
       01  WS-RECORD-COUNT               PIC 9(8) VALUE 0.
       
           PROCESS-RECORD.
               ADD sales-amount TO WS-TOTAL-SALES.
               ADD 1 TO WS-RECORD-COUNT.
```

### Pattern : Boucle conditionnelle
```cobol
       PERFORM PROCESS UNTIL WS-EOF-FLAG = 'Y'
           OR WS-ERROR-FLAG = 1.
```

### Pattern : Validation
```cobc
       VALIDATE-EMPLOYEE-ID.
           IF employee-id NOT NUMERIC
               MOVE 8 TO WS-RETURN-CODE
               MOVE "ID employé invalide" TO WS-ERROR-MSG
               PERFORM LOG-ERROR
           ELSE IF employee-id = 0
               MOVE 8 TO WS-RETURN-CODE
               MOVE "ID employé = 0" TO WS-ERROR-MSG
               PERFORM LOG-ERROR
           END-IF.
```

## 9. CICS (si applicable)

Pour applications CICS pseudo-conversationnelles:

```cobol
       IDENTIFICATION DIVISION.
           PROGRAM-ID. pgm-cics-screen.
       
       PROCEDURE DIVISION.
           MAIN-PROCEDURE.
               EVALUATE EIBCALEN
                   WHEN 0
                       PERFORM SEND-INITIAL-SCREEN
                   WHEN OTHER
                       PERFORM RECEIVE-SCREEN-INPUT
                       PERFORM VALIDATE-INPUT
                       IF WS-ERROR-FLAG = 0
                           PERFORM PROCESS-REQUEST
                           PERFORM SEND-SUCCESS-SCREEN
                       ELSE
                           PERFORM SEND-ERROR-SCREEN
                       END-IF
               END-EVALUATE.
               EXEC CICS RETURN END-EXEC.
       
           SEND-INITIAL-SCREEN.
               EXEC CICS SEND MAP('EMPMAP')
                   MAPSET('EMPMAPSET')
                   FROM(screen-data)
                   ERASE END-EXEC.
       
           RECEIVE-SCREEN-INPUT.
               EXEC CICS RECEIVE MAP('EMPMAP')
                   MAPSET('EMPMAPSET')
                   INTO(input-data)
                   END-EXEC.
```

## 10. DB2 SQL/COBOL

Pour requêtes embarquées:

```cobol
       DATA DIVISION.
           SQL SECTION.
           EXEC SQL
               DECLARE emp-cursor CURSOR FOR
               SELECT emp-id, emp-name, salary
               FROM employees
               WHERE department = :dept-id
               ORDER BY emp-id
           END-EXEC.
       
       PROCEDURE DIVISION.
           FETCH-EMPLOYEES.
               EXEC SQL
                   OPEN emp-cursor
               END-EXEC.
               
               PERFORM UNTIL sqlcode NOT = 0
                   EXEC SQL
                       FETCH emp-cursor
                       INTO :emp-id, :emp-name, :salary
                   END-EXEC
                   
                   IF sqlcode = 0
                       PERFORM PROCESS-EMPLOYEE
                   ELSE IF sqlcode = 100
                       MOVE 'Y' TO WS-EOF-FLAG
                   ELSE
                       MOVE sqlcode TO WS-SQL-CODE
                       PERFORM LOG-SQL-ERROR
                   END-IF
               END-PERFORM.
               
               EXEC SQL CLOSE emp-cursor END-EXEC.
```

## 11. Commentaires et documentation

**Requis** :
- Chaque section/paragraphe : commenter l'objectif
- Logiques complexes : expliquer le "pourquoi"
- Variables obscures : expliquer l'usage

**Format** :
```cobol
       *> Commentaire sur ligne entière (colonne 7)
           MOVE 0 TO counter.  *> Réinitialiser compteur
```

## 12. Performances

- Utiliser COMP-3 pour nombres si critiques en stockage
- Utiliser MOVE au lieu ACCEPT/DISPLAY en volumes élevés
- INDEXED sequential (VSAM) > sequential pour lookups
- Éviter boucles imbriquées profondes
- PERFORM avec paramètres plutôt que copier code

## 13. Outils et environnements

- **IBM COBOL for z/OS** : compilateur IGYCRCTL
- **GnuCOBOL** : open-source, libre (Linux, Windows, macOS)
- **Éditeurs** : VS Code avec extensions COBOL, Micro Focus COBOL
- **Compilation** : `cobc -x pgm.cbl -o pgm` (GnuCOBOL)
- **Débogage** : GDB + GnuCOBOL, ou CA Debugger (mainframe)
