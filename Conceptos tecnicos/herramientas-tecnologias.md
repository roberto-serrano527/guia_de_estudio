# 🛠️ Herramientas y Tecnologías

## 📋 Gestión de Proyectos

### Git
#### Conceptos Fundamentales
- Control de versiones distribuido
- Seguimiento de cambios en código fuente

#### Comandos Principales
```bash
# Configuración inicial
git config --global user.name "Tu Nombre"
git config --global user.email "tu.email@ejemplo.com"

# Flujo básico
git init             # Inicializar repositorio
git clone [url]      # Clonar repositorio
git add .            # Preparar cambios
git commit -m "Mensaje"  # Confirmar cambios
git push             # Subir cambios al repositorio remoto
git pull             # Actualizar repositorio local
```

#### Estrategias de Branching
- **Gitflow**: 
  - `main`: Versión estable
  - `develop`: Integración de características
  - `feature/`: Ramas para nuevas funcionalidades
  - `hotfix/`: Correcciones críticas
  - `release/`: Preparación de nueva versión

### Maven
#### Características
- Gestión de dependencias
- Construcción de proyectos
- Estandarización de estructura

#### Estructura de Proyecto
```
mi-proyecto/
├── pom.xml
├── src/
│   ├── main/
│   │   └── java/
│   └── test/
│       └── java/
```

#### Ciclo de Vida
- `compile`: Compilar código fuente
- `test`: Ejecutar pruebas
- `package`: Empaquetar en JAR/WAR
- `install`: Instalar en repositorio local

## 🐳 Contenerización

### Docker
#### Conceptos Clave
- Contenedorización de aplicaciones
- Aislamiento de entornos
- Portabilidad

#### Comandos Principales
```bash
# Construcción de imagen
docker build . -t mi-imagen:v1

# Crear y ejecutar contenedor
docker run -p 8080:8081 mi-imagen:v1

# Gestión de contenedores
docker ps              # Listar contenedores
docker stop [id]       # Detener contenedor
docker rm [id]         # Eliminar contenedor
```

#### Dockerfile Ejemplo
```dockerfile
FROM openjdk:17-jdk-slim
COPY target/app.jar app.jar
ENTRYPOINT ["java", "-jar", "/app.jar"]
```

## 🧪 Testing

### JUnit
#### Anotaciones Principales
- `@Test`: Método de prueba
- `@Before`: Preparación antes de cada prueba
- `@After`: Limpieza después de cada prueba
- `@BeforeClass`: Configuración inicial de clase
- `@AfterClass`: Limpieza final de clase

#### Ejemplo de Prueba
```java
public class CalculadoraTest {
    @Test
    public void testSuma() {
        Calculadora calc = new Calculadora();
        assertEquals(5, calc.suma(2, 3));
    }
}
```

### JMeter
#### Uso en Pruebas de Rendimiento
- Pruebas de carga
- Pruebas de estrés
- Medición de tiempos de respuesta
- Simulación de múltiples usuarios

## 📊 Documentación de APIs

### Swagger
#### Características
- Documentación interactiva de APIs
- Generación de documentación desde código
- Pruebas de endpoints

#### Anotaciones Principales
- `@ApiOperation`: Descripción de operación
- `@ApiResponse`: Códigos de respuesta
- `@ApiParam`: Descripción de parámetros

## 📡 Mensajería

### Apache Kafka
#### Conceptos Fundamentales
- Sistema de mensajería distribuido
- Procesamiento de streams
- Alta escalabilidad

#### Componentes
- **Producers**: Envían mensajes
- **Consumers**: Reciben mensajes
- **Brokers**: Servidores de Kafka
- **Topics**: Canales de mensajes

#### Caso de Uso
```java
// Ejemplo simplificado de productor
Producer<String, String> producer = new KafkaProducer<>(props);
producer.send(new ProducerRecord<>("mi-topic", "clave", "valor"));
```

## 🔐 Seguridad

### JWT (JSON Web Token)
#### Estructura
- **Header**: Algoritmo de cifrado
- **Payload**: Información del usuario
- **Signature**: Firma de seguridad

#### Ejemplo de Generación
```java
String token = Jwts.builder()
    .setSubject(username)
    .setIssuedAt(new Date())
    .setExpiration(new Date(System.currentTimeMillis() + expiration))
    .signWith(SignatureAlgorithm.HS512, secret)
    .compact();
```

## 📈 Monitoreo

### Herramientas
- **Prometheus**: Métricas y monitoreo
- **Grafana**: Visualización de datos
- **ELK Stack**: 
  - Elasticsearch: Búsqueda y análisis
  - Logstash: Procesamiento de logs
  - Kibana: Visualización

## 🌐 Protocolos de Comunicación

### REST vs gRPC
#### REST
- Basado en HTTP
- Formato JSON
- Fácil de implementar
- Menos eficiente

#### gRPC
- Basado en Protocol Buffers
- Alto rendimiento
- Tipado fuerte
- Ideal para microservicios
