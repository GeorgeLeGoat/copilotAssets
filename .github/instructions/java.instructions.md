---
description: Instructions pour développer des programmes Java modernes et applications d'entreprise
applyTo: '**/*.java, **/pom.xml, **/build.gradle, **/*.jcl'
---

# Guide de développement Java

## 1. Structure générale d'une classe Java

Convention de base pour tout fichier `.java`:

```java
package com.example.payroll;

import java.time.LocalDate;
import java.util.Objects;
import java.util.Optional;

/**
 * Représente un employé de l'entreprise.
 * 
 * Cette classe encapsule les informations personnelles et professionnelles
 * d'un employé, avec validation des données.
 * 
 * @author Jean Dupont
 * @version 1.0
 * @since 2026-02-07
 */
public class Employee {
    
    private final long employeeId;
    private final String firstName;
    private final String lastName;
    private final LocalDate hireDate;
    private BigDecimal salary;
    private Department department;
    
    /**
     * Construit un employé avec identifiant et nom.
     * 
     * @param employeeId l'ID unique de l'employé (> 0)
     * @param firstName  le prénom (non-null, non-vide)
     * @param lastName   le nom de famille (non-null, non-vide)
     * @param hireDate   la date d'embauche (non-null)
     * @throws IllegalArgumentException si un paramètre requiert est invalide
     * @throws NullPointerException si un paramètre requis est null
     */
    public Employee(long employeeId, String firstName, String lastName, LocalDate hireDate) {
        this.employeeId = validateEmployeeId(employeeId);
        this.firstName = Objects.requireNonNull(firstName, "firstName cannot be null");
        this.lastName = Objects.requireNonNull(lastName, "lastName cannot be null");
        this.hireDate = Objects.requireNonNull(hireDate, "hireDate cannot be null");
        
        if (firstName.isBlank()) {
            throw new IllegalArgumentException("firstName cannot be empty");
        }
        if (lastName.isBlank()) {
            throw new IllegalArgumentException("lastName cannot be empty");
        }
    }
    
    // Getters
    public long getEmployeeId() {
        return employeeId;
    }
    
    public String getFirstName() {
        return firstName;
    }
    
    public String getLastName() {
        return lastName;
    }
    
    public LocalDate getHireDate() {
        return hireDate;
    }
    
    public Optional<BigDecimal> getSalary() {
        return Optional.ofNullable(salary);
    }
    
    // Setters
    public void setSalary(BigDecimal salary) {
        if (salary != null && salary.signum() < 0) {
            throw new IllegalArgumentException("Salary cannot be negative");
        }
        this.salary = salary;
    }
    
    public void setDepartment(Department department) {
        this.department = Objects.requireNonNull(department, "department cannot be null");
    }
    
    // Méthodes métier
    /**
     * Calcule le nombre d'années d'ancienneté.
     * 
     * @return le nombre d'années depuis l'embauche
     */
    public int getYearsOfService() {
        return (int) ChronoUnit.YEARS.between(hireDate, LocalDate.now());
    }
    
    // Equals, Hashcode, ToString
    @Override
    public boolean equals(Object o) {
        if (this == o) return true;
        if (!(o instanceof Employee)) return false;
        Employee employee = (Employee) o;
        return employeeId == employee.employeeId &&
               firstName.equals(employee.firstName) &&
               lastName.equals(employee.lastName);
    }
    
    @Override
    public int hashCode() {
        return Objects.hash(employeeId, firstName, lastName);
    }
    
    @Override
    public String toString() {
        return "Employee{" +
                "employeeId=" + employeeId +
                ", firstName='" + firstName + '\'' +
                ", lastName='" + lastName + '\'' +
                ", hireDate=" + hireDate +
                ", salary=" + salary +
                '}';
    }
    
    // Méthodes privées
    private long validateEmployeeId(long id) {
        if (id <= 0) {
            throw new IllegalArgumentException("Employee ID must be > 0");
        }
        return id;
    }
}
```

## 2. Conventions de nommage

### Packages
- **Format** : `com.{organization}.{domain}.{module}`
- **Exemples** :
  - `com.example.payroll` (domaine paie)
  - `com.example.payroll.service` (services métier)
  - `com.example.payroll.repository` (accès données)
  - `com.example.payroll.dto` (Data Transfer Objects)
  - `com.example.payroll.exception` (exceptions custom)
  - `com.example.payroll.util` (utilitaires)

### Classes
- **Format** : `PascalCase` (CapitalizedWords)
- **Suffix significatif** :
  - `Controller` : classes contrôleur REST/Web
  - `Service` : logique métier
  - `Repository` : accès données (DAO/Data Access)
  - `Dto` : Data Transfer Objects
  - `Exception` : exceptions custom
  - `Util` : utilitaires
  - `Test` : tests unitaires/intégration

**Exemples** :
```java
public class PayrollCalculator { }
public class EmployeeService { }
public class EmployeeRepository { }
public class EmployeeDto { }
public class EmployeeNotFoundException extends Exception { }
```

### Interfaces
- **Format** : `PascalCase`, souvent avec préfixe `I` (optionnel) ou suffixe
- **Exemples** :
  ```java
  public interface EmployeeRepository { }
  public interface PaymentProcessor { }
  public interface ILogger { }  // Optionnel
  ```

### Variables et constantes
- **Variables locales** : `camelCase`
- **Constantes publiques** : `UPPER_SNAKE_CASE`
- **Constantes privées** : `UPPER_SNAKE_CASE` ou `camelCase`

**Exemples** :
```java
private String employeeName;           // camelCase
private final int MAX_RETRIES = 3;     // UPPER_SNAKE_CASE
public static final String API_URL = "https://api.example.com";
```

### Méthodes
- **Format** : `camelCase`, verbe en premier
- **Conventions** :
  - `get*()` : getter (propriété accessible)
  - `set*()` : setter (propriété modifiable)
  - `is*()` ou `has*()` : booléen
  - `create*()`, `build*()` : factory methods
  - `calculate*()`, `compute*()` : calculs
  - `validate*()`, `check*()` : validations
  - `process*()`, `handle*()` : traitement
  - `find*()`, `search*()` : recherche données

**Exemples** :
```java
public String getEmployeeName() { }
public void setEmployeeName(String name) { }
public boolean isActive() { }
public boolean hasValidEmail() { }
public Employee createEmployeeFromDto(EmployeeDto dto) { }
public BigDecimal calculateBonus() { }
public void validateInput(String input) { }
```

## 3. Types et Null-Safety

### NeverNull guarantees
```java
// ✅ BON : Toujours vérifier null ou utiliser Optional
public void processEmployee(Employee emp) {
    Objects.requireNonNull(emp, "emp cannot be null");
    // ... traitement
}

// ✅ BON : Utiliser Optional
public Optional<Employee> findEmployeeById(long id) {
    return employeeRepository.findById(id);
}

// Consommateur
var emp = findEmployeeById(123);
if (emp.isPresent()) {
    emp.get().setDepartment(...);
}

// ✅ BON : ifPresentOrElse
emp.ifPresentOrElse(
    e -> System.out.println("Trouvé: " + e),
    () -> System.out.println("Non trouvé")
);

// ✅ BON : map chain
emp.map(Employee::getSalary)
   .ifPresent(salary -> System.out.println("Salaire: " + salary));
```

### Types de données
```java
// Nombres entiers
int age;              // 32-bit (-2.1B à +2.1B)
long employeeId;      // 64-bit (-9.2E18 à +9.2E18)
byte status;          // 8-bit (-128 à 127)

// Nombres décimaux
BigDecimal salary;    // Précision arbitraire, paiement/finances
double percentage;    // Précision 64-bit, calcs approximatifs

// Chaînes
String name;          // Immuable, UTF-16
String description;

// Collections
List<Employee> employees;         // ArrayList par défaut
Set<String> departments;          // HashSet pour unicité
Map<Long, Employee> employeeMap;  // HashMap pour clé→valeur

// Énumérations
public enum Status {
    ACTIVE("A", "Actif"),
    INACTIVE("I", "Inactif"),
    SUSPENDED("S", "Suspendu");
    
    private final String code;
    private final String label;
    
    Status(String code, String label) {
        this.code = code;
        this.label = label;
    }
}
```

## 4. Gestion d'erreurs et exceptions

### Custom Exceptions
```java
public abstract class ApplicationException extends RuntimeException {
    private final String errorCode;
    private final String message;
    
    public ApplicationException(String errorCode, String message) {
        super(message);
        this.errorCode = errorCode;
        this.message = message;
    }
    
    public String getErrorCode() {
        return errorCode;
    }
}

// Exception spécifique métier
public class EmployeeNotFoundException extends ApplicationException {
    public EmployeeNotFoundException(long employeeId) {
        super("EMP_NOT_FOUND", "Employee " + employeeId + " not found");
    }
}

public class InvalidSalaryException extends ApplicationException {
    public InvalidSalaryException(BigDecimal salary) {
        super("INVALID_SALARY", "Salary must be positive, got: " + salary);
    }
}
```

### Try-Catch avec récupération
```java
public Employee findAndUpdateEmployee(long id, BigDecimal newSalary) {
    try {
        Employee emp = employeeRepository.findById(id)
            .orElseThrow(() -> new EmployeeNotFoundException(id));
        
        if (newSalary.signum() < 0) {
            throw new InvalidSalaryException(newSalary);
        }
        
        emp.setSalary(newSalary);
        return employeeRepository.save(emp);
        
    } catch (EmployeeNotFoundException e) {
        logger.warn("Employee {} not found", id);
        throw e;
    } catch (DatabaseException e) {
        logger.error("Database error while updating employee {}", id, e);
        throw new ApplicationException("DB_ERROR", "Cannot update employee", e);
    } catch (Exception e) {
        logger.error("Unexpected error", e);
        throw new ApplicationException("UNEXPECTED", "Unexpected error occurred", e);
    }
}
```

## 5. Patterns et architectures

### Service/Repository Pattern
```java
// Repository Interface
public interface EmployeeRepository {
    Optional<Employee> findById(long id);
    List<Employee> findByDepartment(String dept);
    Employee save(Employee emp);
    void delete(long id);
}

// Service métier
public class EmployeeService {
    private final EmployeeRepository repository;
    private final SalaryCalculator calculator;
    private final Logger logger;
    
    public EmployeeService(EmployeeRepository repo, SalaryCalculator calc) {
        this.repository = Objects.requireNonNull(repo);
        this.calculator = Objects.requireNonNull(calc);
    }
    
    public Employee giveRaise(long employeeId, BigDecimal raisePercent) {
        Employee emp = repository.findById(employeeId)
            .orElseThrow(() -> new EmployeeNotFoundException(employeeId));
        
        BigDecimal newSalary = calculator.applyRaise(
            emp.getSalary().orElse(BigDecimal.ZERO),
            raisePercent
        );
        
        emp.setSalary(newSalary);
        Employee updated = repository.save(emp);
        
        logger.info("Raised salary for employee {}", employeeId);
        return updated;
    }
}
```

### Builder Pattern
```java
public class Employee {
    // ... champs privés ...
    
    public static class Builder {
        private final long employeeId;
        private final String firstName;
        private final String lastName;
        private final LocalDate hireDate;
        private BigDecimal salary;
        private Department department;
        
        public Builder(long id, String first, String last, LocalDate hired) {
            this.employeeId = id;
            this.firstName = first;
            this.lastName = last;
            this.hireDate = hired;
        }
        
        public Builder salary(BigDecimal sal) {
            this.salary = sal;
            return this;
        }
        
        public Builder department(Department dept) {
            this.department = dept;
            return this;
        }
        
        public Employee build() {
            Employee emp = new Employee(employeeId, firstName, lastName, hireDate);
            emp.salary = this.salary;
            emp.department = this.department;
            return emp;
        }
    }
    
    // Utilisation
    Employee emp = new Employee.Builder(1L, "Jean", "Dupont", LocalDate.now())
        .salary(new BigDecimal("50000"))
        .department(Department.IT)
        .build();
}
```

### Singleton Pattern (ThreadSafe)
```java
public class ConfigurationManager {
    private static volatile ConfigurationManager instance;
    private final Properties config;
    
    private ConfigurationManager() {
        config = new Properties();
        loadConfiguration();
    }
    
    public static ConfigurationManager getInstance() {
        if (instance == null) {
            synchronized (ConfigurationManager.class) {
                if (instance == null) {
                    instance = new ConfigurationManager();
                }
            }
        }
        return instance;
    }
    
    private void loadConfiguration() {
        // Charger config
    }
}

// Alternative modernes (Effective Java 3rd edition):
public enum ConfigurationManager {
    INSTANCE;
    
    private final Properties config;
    
    ConfigurationManager() {
        config = new Properties();
        loadConfiguration();
    }
    
    public Properties getConfig() {
        return config;
    }
}
```

## 6. Spring Boot (si applicable)

### Structure projet Maven
```xml
<project>
    <modelVersion>4.0.0</modelVersion>
    <groupId>com.example</groupId>
    <artifactId>payroll-app</artifactId>
    <version>1.0.0</version>
    
    <parent>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-parent</artifactId>
        <version>3.2.0</version>
    </parent>
    
    <dependencies>
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-web</artifactId>
        </dependency>
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-data-jpa</artifactId>
        </dependency>
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-test</artifactId>
            <scope>test</scope>
        </dependency>
    </dependencies>
</project>
```

### Contrôleur REST
```java
@RestController
@RequestMapping("/api/v1/employees")
public class EmployeeController {
    private final EmployeeService service;
    private static final Logger logger = LoggerFactory.getLogger(EmployeeController.class);
    
    public EmployeeController(EmployeeService service) {
        this.service = Objects.requireNonNull(service);
    }
    
    @GetMapping("/{id}")
    public ResponseEntity<EmployeeDto> getEmployee(@PathVariable long id) {
        try {
            EmployeeDto emp = service.findEmployeeById(id);
            return ResponseEntity.ok(emp);
        } catch (EmployeeNotFoundException e) {
            logger.warn("Employee {} not found", id);
            return ResponseEntity.notFound().build();
        }
    }
    
    @PostMapping
    public ResponseEntity<EmployeeDto> createEmployee(@RequestBody @Valid EmployeeDto dto) {
        EmployeeDto created = service.createEmployee(dto);
        return ResponseEntity
            .status(HttpStatus.CREATED)
            .body(created);
    }
    
    @PutMapping("/{id}")
    public ResponseEntity<EmployeeDto> updateEmployee(
            @PathVariable long id,
            @RequestBody @Valid EmployeeDto dto) {
        EmployeeDto updated = service.updateEmployee(id, dto);
        return ResponseEntity.ok(updated);
    }
    
    @DeleteMapping("/{id}")
    public ResponseEntity<Void> deleteEmployee(@PathVariable long id) {
        service.deleteEmployee(id);
        return ResponseEntity.noContent().build();
    }
}
```

### Configuration & Properties
```properties
# application.properties
spring.application.name=payroll-app
spring.profiles.active=production

# Database
spring.datasource.url=jdbc:mysql://localhost:3306/payroll
spring.datasource.username=root
spring.datasource.password=${DB_PASSWORD}
spring.jpa.hibernate.ddl-auto=validate
spring.jpa.show-sql=false

# Logging
logging.level.root=INFO
logging.level.com.example=DEBUG
logging.file.name=logs/payroll.log
logging.file.max-size=10MB
logging.file.max-history=10
```

## 7. Tests unitaires (JUnit 5 + Mockito)

```java
@DisplayName("Employee Service Tests")
class EmployeeServiceTest {
    
    private EmployeeService service;
    private EmployeeRepository mockRepository;
    private SalaryCalculator mockCalculator;
    
    @BeforeEach
    void setUp() {
        mockRepository = mock(EmployeeRepository.class);
        mockCalculator = mock(SalaryCalculator.class);
        service = new EmployeeService(mockRepository, mockCalculator);
    }
    
    @Test
    @DisplayName("should find employee by id")
    void testFindEmployeeSuccess() {
        // Arrange
        Employee emp = new Employee(1L, "Jean", "Dupont", LocalDate.now());
        when(mockRepository.findById(1L)).thenReturn(Optional.of(emp));
        
        // Act
        Optional<Employee> result = service.findEmployeeById(1L);
        
        // Assert
        assertTrue(result.isPresent());
        assertEquals("Jean", result.get().getFirstName());
        verify(mockRepository, times(1)).findById(1L);
    }
    
    @Test
    @DisplayName("should throw exception when employee not found")
    void testFindEmployeeNotFound() {
        // Arrange
        when(mockRepository.findById(999L)).thenReturn(Optional.empty());
        
        // Act & Assert
        assertThrows(EmployeeNotFoundException.class, 
            () -> service.findEmployeeById(999L));
        verify(mockRepository, times(1)).findById(999L);
    }
    
    @Test
    @DisplayName("should apply raise correctly")
    void testGiveRaise() {
        // Arrange
        Employee emp = new Employee(1L, "Jean", "Dupont", LocalDate.now());
        emp.setSalary(new BigDecimal("50000"));
        
        when(mockRepository.findById(1L)).thenReturn(Optional.of(emp));
        when(mockCalculator.applyRaise(any(), any()))
            .thenReturn(new BigDecimal("55000"));
        when(mockRepository.save(any())).thenReturn(emp);
        
        // Act
        Employee updated = service.giveRaise(1L, new BigDecimal("10"));
        
        // Assert
        assertNotNull(updated);
        verify(mockRepository, times(1)).save(any());
    }
}
```

## 8. Logging (SLF4J + Logback)

```java
public class EmployeeService {
    private static final Logger logger = LoggerFactory.getLogger(EmployeeService.class);
    
    public void processEmployee(long id) {
        logger.debug("Starting to process employee: {}", id);
        
        try {
            Employee emp = findEmployee(id);
            logger.info("Found employee: {} {}", emp.getFirstName(), emp.getLastName());
            
            // Traitement
            
        } catch (EmployeeNotFoundException e) {
            logger.warn("Employee {} not found", id);
        } catch (Exception e) {
            logger.error("Error processing employee {}", id, e);
            throw e;
        }
    }
}
```

**logback.xml**:
```xml
<configuration>
    <property name="LOG_FILE" value="logs/app.log" />
    
    <appender name="STDOUT" class="ch.qos.logback.core.ConsoleAppender">
        <encoder>
            <pattern>%d{yyyy-MM-dd HH:mm:ss} [%thread] %-5level %logger{36} - %msg%n</pattern>
        </encoder>
    </appender>
    
    <appender name="FILE" class="ch.qos.logback.core.rolling.RollingFileAppender">
        <file>${LOG_FILE}</file>
        <encoder>
            <pattern>%d{yyyy-MM-dd HH:mm:ss} [%thread] %-5level %logger{36} - %msg%n</pattern>
        </encoder>
        <rollingPolicy class="ch.qos.logback.core.rolling.SizeAndTimeBasedRollingPolicy">
            <fileNamePattern>${LOG_FILE}.%d{yyyy-MM-dd}.%i.gz</fileNamePattern>
            <maxFileSize>10MB</maxFileSize>
            <maxHistory>10</maxHistory>
        </rollingPolicy>
    </appender>
    
    <root level="INFO">
        <appender-ref ref="STDOUT" />
        <appender-ref ref="FILE" />
    </root>
</configuration>
```

## 9. Documentation & Javadoc

```java
/**
 * Calcule le bonus annuel d'un employé basé sur son salaire et performance.
 * 
 * <p>La formule de calcul est: <code>salaire * (1 + (performance_rating / 10))</code>
 * 
 * <p>Exemple d'utilisation:
 * <pre>
 *   BigDecimal bonus = calculator.calculateBonus(emp, 4.5);
 *   System.out.println("Bonus: " + bonus);
 * </pre>
 * 
 * @param employee l'employé pour lequel calculer le bonus (non-null)
 * @param performanceRating la note de performance (0.0 à 5.0)
 * @return le montant du bonus, ou {@link BigDecimal#ZERO} si salaire null
 * @throws IllegalArgumentException si performanceRating hors limites
 * @throws NullPointerException si employee est null
 * @since 1.0
 */
public BigDecimal calculateBonus(Employee employee, double performanceRating) {
    // ...
}
```

## 10. Bonnes pratiques SOLID

### Single Responsibility Principle
```java
// ❌ PAS BON : Classe faire trop de choses
public class EmployeeManager {
    public void calculateSalary() { }
    public void sendEmail() { }
    public void saveToDatabase() { }
    public void logActivity() { }
}

// ✅ BON : Chaque classe responsable d'une chose
public class SalaryCalculator {
    public BigDecimal calculate(Employee emp) { }
}

public class EmailNotifier {
    public void sendSalaryEmail(Employee emp, BigDecimal salary) { }
}

public class EmployeeRepository {
    public void save(Employee emp) { }
}

public class ActivityLogger {
    public void log(String activity) { }
}
```

### Open-Closed Principle
```java
// ✅ BON : Extensible sans modification
public interface PaymentProcessor {
    void process(Payment payment) throws PaymentException;
}

public class CreditCardProcessor implements PaymentProcessor {
    @Override
    public void process(Payment payment) throws PaymentException {
        // Implémentation spécifique carte crédit
    }
}

public class BankTransferProcessor implements PaymentProcessor {
    @Override
    public void process(Payment payment) throws PaymentException {
        // Implémentation spécifique virement
    }
}

public class PaymentService {
    private final PaymentProcessor processor;
    
    public void pay(Payment payment) throws PaymentException {
        processor.process(payment);  // Fonctionneras avec tout PaymentProcessor
    }
}
```

## 11. Performance

- Utiliser `StringBuilder` pour concaténation en boucles
- Éviter création objets inutiles dans boucles
- Pré-calculer/cacher valeurs constantes
- Connection pooling pour BD
- Lazy loading pour collections
- Monitor memory leaks avec profiler

## 12. Sécurité

- Valider TOUTES les entrées utilisateur
- Échapper outputs (XSS protection)
- Utiliser prepared statements (SQL injection)
- Hachage de passwords (bcrypt, scrypt)
- HTTPS en production
- Secrets management (env vars, vaults)
- Logging sensible (ne pas log passwords)

## 13. Outils et build

### Maven
```bash
mvn clean install          # Compiler et tester
mvn clean package          # Générer JAR
mvn clean deploy           # Déployer artefact
mvn test                   # Lancer tests
```

### Gradle
```bash
./gradlew clean build      # Compiler et tester
./gradlew bootRun          # Démarrer app Spring Boot
./gradlew test             # Tests
```

### IDE/Éditeurs
- **IntelliJ IDEA** : meilleur pour Java (paid/community)
- **Eclipse** : gratuit, solide
- **VS Code** + Extension Coding Pack for Java
- **NetBeans** : gratuit, complet
