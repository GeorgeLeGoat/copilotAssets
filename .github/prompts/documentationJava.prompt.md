---
name: documentationJava
description: Générer une documentation développeur complète et professionnelle pour un fichier ou projet Java
---

# Prompt : Documentation Développeur Java

## Objectif
Générer une documentation technique et développeur de qualité professionnelle pour un fichier Java ou projet donné. La documentation doit être exploitable par des développeurs Java, faciliter la maintenance, la collaboration et l'onboarding.

## Instructions

### 1. Analyser le code Java

#### Pour une classe/interface unique
- Identifier le package
- Lister tous les imports
- Analyser la hiérarchie (extends, implements)
- Identifier fields (privés, publics, constants)
- Lister toutes les méthodes publiques/protégées
- Relever les dépendances (injections, collaborateurs)
- Identifier patterns utilisés (Singleton, Builder, Factory, etc.)
- Relever les annotations importantes (@Override, @Deprecated, etc.)

#### Pour un projet/module complet
- Arborescence packages et responsabilités
- Points d'entrée (main, API endpoints, listeners)
- Flux de données (requête → traitement → réponse)
- Intégrations externes (BD, APIs tierces, files d'attente)
- Configuration (properties, variables d'environnement)

### 2. Sections obligatoires

#### 2.1 En-tête et résumé (50-100 mots)
- **Nom complet** : package.ClassName
- **Objectif** : description du rôle de cette classe/module
- **Type** : Service, Controller, Repository, DTO, Utility, etc.
- **Version** : numéro de version (ex: 2.3.1)
- **Date de dernière modification** : [date]
- **Auteur(s)** : [noms]
- **Status** : Production / Beta / Deprecated / Archivé

#### 2.2 Vue d'ensemble architecturale
- Position dans l'architecture globale
- Diagramme relationnel (classe parente, interfaces, composants collaborateurs)
- Patterns utilisés (MVC, Service Layer, Repository, etc.)
- Responsabilités principales

#### 2.3 Description détaillée de la classe/interface

**Pour une classe** :
- Raison d'être et problème résolu
- Exemple d'utilisation simple (2-3 lignes)
- Cas d'usage nominaux et exceptionnels
- Contraintes/limitations
- Thread-safety (si pertinent)
- Immuabilité (si applicable)

**Pour une interface** :
- Contract défini
- Implémentations connues
- Responsabilités du implémenteur

#### 2.4 Fields/Propriétés documentées

Tableau avec:
- **Field Name** (ex: employeeRepository)
- **Type** (ex: EmployeeRepository)
- **Visibility** (private, protected, public)
- **Mutability** (final, mutable)
- **Description** : rôle et usage
- **Default Value** : si pertinent

**Exemple**:
```markdown
| Field | Type | Visibility | Mutability | Description |
|-------|------|------------|-----------|-------------|
| employeeRepository | EmployeeRepository | private | final | Service d'accès aux employés (injected) |
| logger | Logger | private | final | Logger SLF4J pour traçage |
| cacheTimeout | Duration | private | final | Timeout du cache (3600 secondes) |
```

#### 2.5 Constructeurs

Pour chaque constructeur:
- **Signature** avec paramètres
- **Description** : quand utiliser ce constructeur
- **Parameters** : tableau description de chaque paramètre
- **Throws** : exceptions possibles
- **Exemple** : snippet d'utilisation

**Exemple** :
```markdown
### Constructeur principal
```java
public EmployeeService(EmployeeRepository repository, SalaryCalculator calculator)
```
Constructeur d'injection de dépendances. À utiliser pour instanciation normale en Spring.
- repository : service d'accès aux données (non-null)
- calculator : moteur de calcul salaire (non-null)
```

#### 2.6 Méthodes publiques/protégées

Pour chaque méthode importante:
- **Signature** complète
- **Description** : objective et bref
- **Parameters** : tableau avec type, nom, description
- **Return** : type et description du résultat
- **Throws** : exceptions possibles et quand
- **Side Effects** : modifications d'état, I/O, etc.
- **Example** : snippet d'utilisation réaliste
- **Performance** : complexité O(n), attention si > O(n²)
- **Thread-Safety** : si applicable
- **Deprecated** : indication si obsolète (utiliser à la place)

**Exemple** :
```markdown
### findEmployeeById(long id)
```java
public Optional<Employee> findEmployeeById(long id)
```

Recherche un employé par son ID.

**Parameters:**
- id : identifiant unique (> 0)

**Returns:**
- Optional<Employee> : employé si trouvé, Optional vide sinon

**Throws:**
- IllegalArgumentException : si id <= 0
- DatabaseException : si erreur d'accès BD

**Example:**
```java
long empId = 12345L;
var emp = employeeService.findEmployeeById(empId);
if (emp.isPresent()) {
    System.out.println("Trouvé: " + emp.get().getName());
}
```

**Performance:** O(1) lookup (indexed)
```

#### 2.7 Dépendances et injections

Lister:
- **Dépendances injectées** (constructeur, setters)
- **Dépendances optionnelles** (si pertinent)
- **Configuration externe** : properties, env variables
- **Frameworks utilisés** : Spring, Guice, etc.
- **Versions requises** si critiques

#### 2.8 Intégrations externes

### Pour BD/ORM
- Tables accédées
- Requêtes SQL/JPQL clés
- Index utilisés (performance)
- Transaction handling

### Pour APIs REST
- Endpoints fournis (GET /api/employees, etc.)
- Paramètres d'entrée
- Codes HTTP attendus (200, 400, 404, 500, etc.)
- Format réponses (JSON example)

### Pour cache/queue/external services
- Services appelés
- Format données échangées
- Timeouts configurés
- Retry policy

#### 2.9 Gestion d'erreurs et exceptions

Tableau:
- **Exception** (ex: EmployeeNotFoundException)
- **When** : circonstance d'occurrence
- **Cause** : raison technique
- **Recovery** : comment gérer (log level, retry, fallback)

#### 2.10 Configuration et paramètres

Liste structurée:
- **Property Name** (ex: employee.cache.timeout)
- **Type** (String, Integer, Boolean)
- **Default** : valeur par défaut
- **Description** : rôle
- **Environment Variable** : surcharge possible

**Exemple** :
```properties
# application.properties
employee.cache.timeout=3600
employee.max.retries=3
employee.api.baseUrl=${EMPLOYEE_API_URL}
```

#### 2.11 Patterns et design utilisés

Lister les patterns présents:
- **Singleton** : si applicable
- **Builder** : construction complexe
- **Factory** : création d'instances
- **Strategy** : comportements interchangeables
- **Observer** : listeners événements
- **Decorator** : enrichissement comportement
- Etc.

Avec brève explication et localisation dans le code.

#### 2.12 Tests et couverture

- **Framework** : JUnit 5, JUnit 4, etc.
- **Mock framework** : Mockito, etc.
- **Coverage** : % de couverture (si connu)
- **Test classes** : noms et localisation
- **Test fixtures** : données de test réutilisables

**Exemple** :
```markdown
## Tests unitaires

- **Framework** : JUnit 5 + Mockito 4.x
- **Classe test** : EmployeeServiceTest
- **Coverage** : 87% (ligne), 92% (branche)
- **Test factory** : EmployeeTestFactory.createTestEmployee()

Principaux tests:
- findEmployeeById_success() : cas nominal
- findEmployeeById_notFound() : employé inexistant
- findEmployeeById_invalidId() : ID invalide (≤ 0)
- giveRaise_success() : augmentation appliquée
- giveRaise_invalidRaise() : montant négatif rejeté
```

#### 2.13 Logging et tracing

- **Logger utilisé** : SLF4J, Log4j, etc.
- **Log levels** : DEBUG, INFO, WARN, ERROR (exemples)
- **Structured logging** : MDC keys si pertinents
- **Output** : console, fichier, centralisé
- **Example logs** :
  ```
  [2026-02-07 14:23:15] INFO EmployeeService - Raised salary for employee 12345
  [2026-02-07 14:23:16] WARN EmployeeService - Employee 99999 not found
  ```

#### 2.14 Performance et scalabilité

- Complexité algorithmique des méthodes critiques
- Bottlenecks connus
- Caching stratégies utiliserées
- Connection pooling (BD)
- Batch processing (si applicable)
- Limite de charge/throughput

#### 2.15 Limitations et dépendances

Documenter:
- Versions Java minimum requises
- Versions dépendances critiques
- Plates-formes supportées (Linux, Windows, etc.)
- Taille maximale de données supportée
- Dépendances vers autres services/composants
- Problèmes connus (bugs ouverts, workarounds)

#### 2.16 Exemples d'utilisation

Fournir 3-5 exemples réalistes:

**Exemple 1 : Usage simple**
```java
EmployeeService service = new EmployeeService(repo, calculator);
Optional<Employee> emp = service.findEmployeeById(123L);
```

**Exemple 2 : Avec gestion d'erreur**
```java
try {
    Employee emp = service.findEmployeeById(empId)
        .orElseThrow(() -> new EmployeeNotFoundException(empId));
    emp.setSalary(newSalary);
    service.updateEmployee(emp);
} catch (EmployeeNotFoundException e) {
    logger.warn("Employee not found: {}", empId);
}
```

**Exemple 3 : Pattern stream/lambda**
```java
List<Employee> highEarners = employees.stream()
    .filter(e -> e.getSalary().isPresent())
    .filter(e -> e.getSalary().get().compareTo(threshold) > 0)
    .collect(Collectors.toList());
```

#### 2.17 Intégration Spring Boot (si applicable)

- **Annotation** (@Service, @Repository, @Component)
- **Lifecycle** (singleton, prototype, etc.)
- **Configuration class** : où configuré
- **Properties prefix** : si auto-configuration
- **Conditional beans** (@ConditionalOnProperty, etc.)

#### 2.18 Migration depuis versions antérieures

- Changements API d'une version à la suivante
- Breaking changes & impact
- Deprecations et timeline
- Guide de migration

#### 2.19 Historique des modifications (Changelog)

Tableau:
- **Version** | **Date** | **Auteur** | **Modification** | **Impact** | **Raison**

**Exemple** :
```markdown
| Version | Date | Modification | Impact |
|---------|------|--------------|--------|
| 2.3.1 | 2026-02-01 | Fix NullPointerException dans calculateBonus() | Medium-High | Regression HOTFIX |
| 2.3.0 | 2026-01-15 | Ajout cache employés, Optional refactor | Medium | Performance |
| 2.2.0 | 2025-12-10 | Migration JUnit 4→5, Mockito upgrade | Low | Tech debt |
```

#### 2.20 Notes pour la maintenance

Liste:
- Points critiques à surveiller (memory leaks, concurrency issues)
- Problèmes connus avec workarounds
- TODOs/améliorations futures
- Contacts mainteneur
- Environnement de test/reproduction

#### 2.21 Références et ressources

- Javadoc généré (lien)
- Spécifications métier (wiki, Jira)
- Documentation dépendances (Spring, Hibernate, etc.)
- Articles techniques pertinents

### 3. Format et style

**Langage**
- Français en-US approprié
- Clair, concis, pas de jargon sans définition
- Ton professionnel et technique
- Exemples concrets systématiquement fournis

**Mise en forme**
- Titres hiérarchisés (# ## ### ####)
- Listes à puces/numérotées pour énumérations
- Tableaux Markdown pour données structurées
- Code blocks avec ```java pour snippets (avec syntax highlight)
- Gras **important**, italique _terme technique_
- Listes imbriquées pour clarté

**Métrique**
- Documentation globale : 1000-3000 mots (selon complexité)
- Exemples : minimum 5
- Pas de copier-coller : toujours paraphraser/interpréter

### 4. Exemple de sortie structurée

```markdown
---
Class-Name: com.example.payroll.service.EmployeeService
Version: 2.3.1
Type: Service
Status: Production
---

# Documentation - EmployeeService

## 1. Résumé
Service métier assurant la gestion des employés (recherche, mise à jour, calculs salaire). 
Utilise le pattern Service avec requête BD via EmployeeRepository. 
Offre une API thread-safe et intégré dans Spring.

## 2. Vue d'ensemble
```
EmployeeController (REST)
         ↓
  EmployeeService (logique métier)
         ↓
  EmployeeRepository (BD)
         ↓
    Database (MySQL/PostgreSQL)
```

## 3. Utilisation simple
```java
@Service
public class EmployeeService {
    private EmployeeRepository repository;
    
    public Optional<Employee> findById(long id) {
        return repository.findById(id);
    }
}
```

(... suite détaillée)
```

### 5. Checklist de complétude

Avant de soumettre la documentation, vérifier:
- [ ] Résumé clair et court (< 100 mots)
- [ ] Architecture et diagrammes expliqués
- [ ] Tous les champs/propriétés documentés
- [ ] Tous les constructeurs et méthodes publiques listés
- [ ] Dépendances et injections expliquées
- [ ] Exceptions et gestion d'erreurs couverts
- [ ] Minimum 5 exemples d'utilisation
- [ ] Intégrations externes documentées
- [ ] Configuration (properties, env vars) expliquée
- [ ] Performance et limitations connues notées
- [ ] Historique modifications (changelog) fourni
- [ ] Pas de jargon sans définition
- [ ] Tous les liens/références actifs
- [ ] Formatage Markdown cohérent

### 6. En cas de projet/module complexe

Pour les projets avec multiples classes:
- Ajouter table des matières (TOC)
- Créer fichier doc par package/module principal
- Fournir diagramme global (Mermaid ou autre)
- Documenter workflows croisant plusieurs classes
- Annexes pour détails (SQL complets, configs, etc.)

### 7. Pour documentations Spring Boot

Ajouter section:
- **Auto-configuration** : props detectées
- **Starter dependency** : si fourni comme starter
- **Conditional features** : fonctionnalités optionnelles
- **Actuator endpoints** : si integration

Exemple:
```properties
# Application intégrant EmployeeService
spring.application.name=payroll-service
employee.service.cache-timeout=3600
employee.service.max-retries=3
```

---

## Comment utiliser ce prompt

**Utilisateur fournit** :
- Code source Java (classe unique ou projet complet)
- Contexte métier (paie? inventaire? ecommerce?)
- Build tool (Maven pom.xml ou Gradle build.gradle)
- Frameworks utilisés (Spring, Hibernate, etc.)

**Réponse attendue** :
- Documentation professionnelle Markdown selon structure ci-dessus
- Prête à intégrer dans wiki d'entreprise, Confluence, GitHub Wiki, ou Javadoc custom
- Exploitable par développeurs Java sans effort supplémentaire
- Facilite onboarding et maintenance long terme
