### 3. Patrones de Comportamiento
Tratan con algoritmos y asignación de responsabilidades entre objetos.

#### Strategy
- **Concepto**: Permite definir una familia de algoritmos, encapsular cada uno y hacerlos intercambiables.
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