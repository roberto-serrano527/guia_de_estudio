### 1. Patrones Creacionales
Estos patrones proporcionan mecanismos de creación de objetos que incrementan la flexibilidad y la reutilización del código.

Estos patrones se centran en cómo se instancian los objetos, evitando el uso directo del operador new para mayor flexibilidad. Facilitan la creación de objetos sin especificar el tipo exacto de objeto que se creará.

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
- **Concepto**: Asegura que una clase tenga una única instancia y proporciona un punto global de acceso a la misma.
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


#### Factory Method
- **Concepto**: Proporciona una interfaz para crear un objeto, pero deja que las subclases decidan qué clase instanciar.
- **Caso de Uso**:
  - Cuando no conoces de antemano los tipos exactos de objetos
  - Cuando quieres proporcionar una biblioteca de productos
  - Cuando necesitas extender funcionalidades de una clase sin modificarla
  - En frameworks y librerías que necesitan ser extensibles
- **Ejemplo de Implementación**:

```java
public abstract class AccountFactory {
    public abstract Account createAccount(String accountType);
}

public class ConcreteAccountFactory extends AccountFactory {
    @Override
    public Account createAccount(String accountType) {
        switch (accountType) {
            case "Savings":
                return new SavingsAccount();
            case "Checking":
                return new CheckingAccount();
            default:
                throw new IllegalArgumentException("Unknown account type");
        }
    }
}

```
