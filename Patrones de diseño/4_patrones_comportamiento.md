### 3. Patrones de Comportamiento
Tratan con algoritmos y asignación de responsabilidades entre objetos.

#### Strategy
- **Concepto**: Permite definir una familia de algoritmos y hacer que estos sean intercambiables en tiempo de ejecución.
- **Caso de Uso**: Cuando se requiere cambiar el comportamiento de un objeto dinámicamente.
```java
interface PaymentStrategy {
    void pay(int amount);
}

class CreditCardPayment implements PaymentStrategy {
    public void pay(int amount) {
        System.out.println("Paid " + amount + " using Credit Card");
    }
}

class PayPalPayment implements PaymentStrategy {
    public void pay(int amount) {
        System.out.println("Paid " + amount + " using PayPal");
    }
}

class PaymentContext {
    private PaymentStrategy strategy;

    public void setStrategy(PaymentStrategy strategy) {
        this.strategy = strategy;
    }

    public void executePayment(int amount) {
        strategy.pay(amount);
    }
}
```


#### Observer
- **Concepto**: Define una relación de dependencia uno a muchos, permitiendo a múltiples objetos recibir notificaciones de cambios.
- **Caso de Uso**: Cuando se requiere notificar a los clientes sobre cambios en su saldo a través de varios canales, como SMS y correo, cada vez que se realiza una transacción en su cuenta.
```java
import java.util.ArrayList;
import java.util.List;

public interface Observer {
    void update(double balance);
}

public class SMSNotifier implements Observer {
    @Override
    public void update(double balance) {
        System.out.println("SMS: Tu saldo es: " + balance);
    }
}

public class EmailNotifier implements Observer {
    @Override
    public void update(double balance) {
        System.out.println("Email: Tu saldo es: " + balance);
    }
}

public class Account {
    private List<Observer> observers = new ArrayList<>();
    private double balance;

    public void addObserver(Observer observer) {
        observers.add(observer);
    }

    public void deposit(double amount) {
        balance += amount;
        notifyObservers();
    }

    public void withdraw(double amount) {
        balance -= amount;
        notifyObservers();
    }

    private void notifyObservers() {
        for (Observer observer : observers) {
            observer.update(balance);
        }
    }
}
 
```
