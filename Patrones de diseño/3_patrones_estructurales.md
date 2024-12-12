### 2. Patrones Estructurales
Explican cómo ensamblar objetos y clases en estructuras más grandes.

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
