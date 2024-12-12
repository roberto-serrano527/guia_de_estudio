### 4. Patrones de Microservicios

#### Circuit Breaker
- **Concepto**: Previene llamadas continuas a servicios que están fallando.
- **Beneficios**: 
  - Mejora la resiliencia del sistema
  - Evita sobrecarga en servicios caídos
  - Permite implementar mecanismos de recuperación

#### Saga
- **Concepto**: Manejo de transacciones distribuidas en sistemas de microservicios.
- **Características**:
  - Coordina transacciones entre múltiples servicios
  - Implementa acciones compensatorias en caso de fallo
  - Garantiza la consistencia en sistemas distribuidos

## Consejos para Entrevistas
- Conocer no solo la definición, sino también casos prácticos de uso
- Estar preparado para explicar pros y contras de cada patrón
- Mostrar cómo estos patrones resuelven problemas de diseño específicos

## Preguntas Frecuentes
- ¿Cuándo usarías un Singleton?
- ¿Qué diferencia hay entre Strategy y State?
- ¿Cómo implementarías un Circuit Breaker en un microservicio?