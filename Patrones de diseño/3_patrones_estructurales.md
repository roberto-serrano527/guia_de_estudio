### 2. Patrones Estructurales

Estos patrones se centran en cómo ensamblar clases y objetos para formar estructuras más grandes, permitiendo que el software sea más flexible y fácil de modificar.

#### Adapter
- **Concepto**: Con este patrón conseguimos que interfaces incompatibles trabajen juntas, convirtiendo una interfaz en otra que el cliente espera.
- **Caso de Uso**: Cuando necesitamos integrar un sistema externo, cuyas clases tienen estructuras muy diferentes a las nuestras
- **Ejemplo**: Integrar a tu proyecto un sistema de pagos externo como PayPal.
```java
public interface PaymentGateway {
    void pay(double amount);
}

public class PayPalAdapter implements PaymentGateway {
    private PayPal payPal;

    public PayPalAdapter(PayPal payPal) {
        this.payPal = payPal;
    }

    @Override
    public void pay(double amount) {
        payPal.sendPayment(amount);
    }
}
```

#### Composite
- **Concepto**: Permite tratar objetos individuales y compuestos de manera uniforme, facilitando el uso de estructuras jerárquicas.
- **Caso de Uso**: Facilita la ejecución de grupos de operaciones como si fueran una sola
```java
import java.util.ArrayList;
import java.util.List;

public interface Transaction {
    void execute();
}

public class SimpleTransaction implements Transaction {
    private String description;

    public SimpleTransaction(String description) {
        this.description = description;
    }

    @Override
    public void execute() {
        System.out.println("Executing: " + description);
    }
}

public class CompositeTransaction implements Transaction {
    private List<Transaction> transactions = new ArrayList<>();

    public void addTransaction(Transaction transaction) {
        transactions.add(transaction);
    }

    @Override
    public void execute() {
        for (Transaction t : transactions) {
            t.execute();
        }
    }
}
```

#### Proxy
- **Concepto**: Proporciona un sustituto o marcador de posición para controlar el acceso a otro objeto.
- **Caso de Uso**: Control de acceso, logging, cacheo.
```java
interface Image {
    void display();
}

class RealImage implements Image {
    public void display() {
        System.out.println("Displaying image");
    }
}

class ProxyImage implements Image {
    private RealImage realImage;

    public void display() {
        if (realImage == null) {
            realImage = new RealImage();
        }
        realImage.display();
    }
}
```
