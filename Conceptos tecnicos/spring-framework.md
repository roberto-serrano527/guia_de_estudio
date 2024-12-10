# 🍃 Spring Framework

## 🌐 Introducción

### ¿Qué es Spring?
- Framework de Java para delegar tareas repetitivas
- Utiliza anotaciones para simplificar el desarrollo
- Promueve la modularidad y la programación desacoplada

## 🔑 Proyectos Core de Spring

### Spring Framework
- Núcleo del ecosistema Spring
- Proporciona funcionalidades base para desarrollo de aplicaciones Java

### Spring Boot
- Proyecto para crear aplicaciones autocontenidas
- Características principales:
  - Servidor de aplicaciones embebido
  - Gestor de dependencias (Gradle, Maven)
  - Configuración automática
  - Desarrollo rápido de microservicios

### Spring Data
- Proyecto para gestión de bases de datos
- Simplifica la interacción con diferentes tipos de almacenamiento
- Proyectos relacionados:
  - Spring Data JPA
  - Spring Data MongoDB
  - Spring Data Redis

### Spring Security
- Módulo para gestión de seguridad
- Funcionalidades:
  - Autenticación
  - Autorización
  - Gestión de sesiones
  - Seguridad por JWT (JSON Web Token)

## 🧩 Conceptos Fundamentales

### Inyección de Dependencias
#### Definición
- Principio de diseño para lograr:
  - Alta cohesión
  - Bajo acoplamiento
- Evita instanciación prematura de objetos
- Desacopla objetos mediante interfaces
- Respeta el principio SOLID Open/Close

#### Formas de Inyección
1. **Por Anotaciones**
   - `@Autowired`
   - `@Inject`
   - `@Qualifier`

2. **Por Constructor**
   ```java
   @Service
   public class MiServicio {
       private final OtraDependencia dependencia;

       @Autowired
       public MiServicio(OtraDependencia dependencia) {
           this.dependencia = dependencia;
       }
   }
   ```

### Inversión de Control (IoC)
- Principio donde el control del flujo lo toma el framework
- Spring maneja el ciclo de vida de los objetos
- Contenedor IoC gestiona la creación y configuración de beans

### Bean
- Objeto administrado por el contenedor IoC de Spring
- Ciclo de vida gestionado por Spring
- Pueden ser configurados mediante anotaciones o XML

## 📝 Anotaciones Principales

### Estereotipos
- `@Component`: Anotación general para componentes genéricos
- `@Controller`: Representa la capa de presentación (métodos HTTP)
  - `@RestController`: Especialización para servicios REST que devuelven JSON
- `@Service`: Indica lógica de negocio
- `@Repository`: Indica interacción con base de datos

### JPA (Java Persistence API)
- `@Entity`: Representa una tabla de base de datos
- `@Table`: Mapeo personalizado de nombre de tabla
- `@Column`: Configuración de columnas
- `@Id`: Indica clave primaria
- `@GeneratedValue`: Generación automática de valores de clave primaria
- `@OneToMany`, `@ManyToOne`: Relaciones entre entidades

### Spring Boot
- `@SpringBootApplication`: Anotación principal de configuración
- Mapeo de Endpoints
  - `@RequestMapping`: Path base
  - `@GetMapping`: Método HTTP GET
  - `@PostMapping`: Método HTTP POST
  - `@PutMapping`: Método HTTP PUT
  - `@DeleteMapping`: Método HTTP DELETE
- Parámetros
  - `@RequestBody`: Cuerpo de la solicitud
  - `@PathVariable`: Variables en la URL
  - `@RequestParam`: Parámetros de consulta

## 🔒 Seguridad

### Autenticación JWT
- JSON Web Token para autenticación
- Compuesto por:
  1. Header: Algoritmo de cifrado
  2. Payload: Información del usuario
  3. Signature: Firma de seguridad

### Implementación Básica
1. Generar token JWT
2. Validar credenciales
3. Crear filtro de seguridad
4. Configurar Spring Security

## 🚀 Buenas Prácticas

### Arquitectura de Microservicios
- Servicios independientes
- Comunicación mediante APIs
- Escalabilidad
- Tolerancia a fallos

### Principios SOLID en Spring
- Single Responsibility
- Open/Closed
- Liskov Substitution
- Interface Segregation
- Dependency Inversion

## 🛠️ Herramientas Complementarias
- Maven/Gradle: Gestión de dependencias
- JUnit: Pruebas unitarias
- Swagger: Documentación de APIs
- Docker: Contenerización
