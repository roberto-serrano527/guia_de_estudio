# ☕ Conceptos Técnicos en Desarrollo Java

## 🔍 Programación Orientada a Objetos (POO)

### Definición
Paradigma de programación basado en el concepto de "objetos" como unidad fundamental.

### 4 Pilares de la POO

#### 1. Abstracción
- Capacidad de obtener información relevante para resolver un problema
- Permite representar características esenciales de un objeto

#### 2. Encapsulamiento
- Habilidad de decidir qué partes de una clase se expondrán a otras entidades
- Oculta o publica atributos y métodos según sea necesario
- Protege la integridad de los datos

#### 3. Polimorfismo
Construcción de métodos con el mismo nombre pero comportamiento diferente.

**Tipos de Polimorfismo:**
1. **Sobrecarga**
   - Métodos con mismo nombre en clases independientes
   - Diferenciados por número o tipo de parámetros

2. **Polimorfismo Paramétrico**
   - Métodos con mismo nombre 
   - Se selecciona según tipo de datos enviados

3. **Polimorfismo de Inclusión**
   - Permite llamar métodos sin conocer el tipo específico
   - Utiliza una interfaz común

#### 4. Herencia
- Capacidad de transferir características (atributos y métodos) de una clase a otra
- Permite reutilización de código
- Establece relaciones entre clases

### Modificadores de Acceso

| Modificador | Clase Propia | Paquete | Subclase | Público |
|------------|--------------|---------|----------|---------|
| Private    | ✔️           | ❌       | ❌        | ❌       |
| Default    | ✔️           | ✔️       | ❌        | ❌       |
| Protected  | ✔️           | ✔️       | ✔️/❌     | ❌       |
| Public     | ✔️           | ✔️       | ✔️        | ✔️       |

## 🧩 Colecciones en Java

### Tipos Principales
1. **List**: 
   - Lista ordenada de objetos
   - Permite elementos duplicados
   - Ejemplos: ArrayList, LinkedList

2. **Set**:
   - Colección desordenada de objetos únicos
   - No permite duplicados
   - Ejemplos: HashSet, TreeSet

3. **Map**:
   - Colección de pares clave-valor
   - Cada clave es única
   - Ejemplos: HashMap, TreeMap

## 🚀 Características Funcionales (Java 8+)

### Lambdas
- Funciones anónimas
- Simplifican la escritura de código
- Introducidas en Java 8
- Permiten tratamiento funcional de colecciones

### Interfaces Funcionales

#### Supplier
- No recibe argumentos
- Devuelve un resultado
- Método principal: `get()`
- Útil para generación perezosa de valores

#### Consumer
- Recibe un argumento
- No devuelve resultado
- Método principal: `accept(T t)`
- Ejemplo de uso: `forEach()` para realizar acciones

#### Predicate
- Recibe un argumento
- Devuelve un valor booleano
- Método principal: `test(T t)`
- Ejemplo de uso: `filter()` en Streams

#### Function
- Recibe un argumento de tipo T
- Devuelve un resultado de tipo R
- Método principal: `apply(T t)`
- Ejemplo de uso: `map()` para transformaciones

## 🌊 Java Streams (Java 8)

### Definición
API que facilita el trabajo con colecciones

### Operaciones Principales
- Buscar
- Filtrar
- Reordenar
- Reducir
- Transformar

## 🆕 Novedades por Versión

### Java 8
- Lambdas
- Stream API
- Paquete java.time

### Java 11
- Inferencia de tipos en datos primitivos
- Método estático `of` en colecciones

### Java 17
- Records (similar a Lombok)
  - Genera automáticamente:
    - Getters
    - `equals()`
    - `toString()`
    - `hashCode()`

- Sealed Classes
  - Restringen qué clases pueden extender o implementar

- Mejora en `instanceof`
  - Eliminación de casting explícito

```java
// Antes
if (obj instanceof String) {
    String str = (String) obj;  // casting manual
    System.out.println(str.toUpperCase());
}

// Después (Java 17)
if (obj instanceof String str) {  // Pattern Matching
    System.out.println(str.toUpperCase());
}
```

## 📌 Conceptos Adicionales

### Palabra Clave `static`
- Permite que un método/atributo pertenezca a la clase, no a las instancias.
- Permite acceso a métodos y variables de clase
- No requiere instanciar un objeto

### Palabra Clave `final`
- Impide modificación de variables, métodos o clases
- Usado para constantes y prevenir herencia/sobreescritura
