### 1. Patrones Creacionales
Estos patrones proporcionan mecanismos de creación de objetos que incrementan la flexibilidad y la reutilización del código.

#### Builder
- **Concepto**: Permite construir objetos complejos paso a paso.
- **Caso de Uso**: Útil cuando se tienen constructores con múltiples parámetros opcionales.
- **Ejemplo de Implementación**:
```java
class Pizza {
    private int size;
    private boolean cheese;
    private boolean pepperoni;

    private Pizza(PizzaBuilder builder) {
        this.size = builder.size;
        this.cheese = builder.cheese;
        this.pepperoni = builder.pepperoni;
    }

    static class PizzaBuilder {
        private int size;
        private boolean cheese = false;
        private boolean pepperoni = false;

        PizzaBuilder(int size) {
            this.size = size;
        }

        PizzaBuilder addCheese() {
            this.cheese = true;
            return this;
        }

        PizzaBuilder addPepperoni() {
            this.pepperoni = true;
            return this;
        }

        Pizza build() {
            return new Pizza(this);
        }
    }
}
```

#### Singleton
- **Concepto**: Asegura que una clase tenga una única instancia y proporciona un punto de acceso global.
- **Caso de Uso**: Gestión de configuraciones, conexiones a bases de datos.
- **Ejemplo**:
```java
public class SingletonExample {
    private static SingletonExample instance;

    private SingletonExample() {}

    public static synchronized SingletonExample getInstance() {
        if (instance == null) {
            instance = new SingletonExample();
        }
        return instance;
    }
}
```
