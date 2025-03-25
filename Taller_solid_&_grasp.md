# Práctica: Diseño de una solución aplicando SOLID y GRASP

## Contexto

Una empresa de logística desea desarrollar un **Sistema de Gestión de Entregas** para optimizar el seguimiento de pedidos desde su recogida en el almacén hasta su entrega al cliente. Actualmente, la empresa maneja distintos tipos de envíos: **estándar**, **express** y **programada**, cada uno con reglas y restricciones específicas.

Los transportistas pueden ser **empleados internos** o **servicios externos tercerizados**, y la asignación de pedidos debe ser eficiente. El sistema debe permitir:

- Consultar entregas.
- Asignar pedidos a transportistas.
- Generar reportes.
- Garantizar el almacenamiento de pedidos para consultas posteriores.

La empresa requiere una **aplicación web** con una interfaz que permita a los usuarios consultar y administrar las entregas. Se espera que el sistema sea **extensible** y tenga una **buena organización del código** para facilitar futuras modificaciones sin alterar su estructura principal.

---

## Objetivo

Diseñar la **arquitectura de clases** del sistema aplicando los principios de diseño **SOLID** y **GRASP**. El diseño debe incluir:

- Un **diagrama de clases UML**.
- Una **justificación clara** de las decisiones de diseño.

El diseño debe garantizar una **separación clara de responsabilidades**, considerando las distintas partes del sistema y sus interacciones.

---

## Requerimientos del sistema

### Gestión de Pedidos

- Cada pedido tiene:
  - Un **ID**.
  - Una **dirección de entrega**.
  - Un **estado**: pendiente, en tránsito, entregado.
  - Un **tipo de envío**.
- Se debe calcular el **costo del envío** según su tipo.
- Los pedidos deben poder asignarse a un transportista disponible.

### Gestión de Transportistas

- Existen dos tipos de transportistas:
  - **Empleados internos**.
  - **Servicios externos**.
- Cada transportista tiene una **capacidad máxima** de pedidos asignables.
- Los transportistas pueden:
  - Actualizar el estado del pedido.
  - Marcar pedidos como entregados.

### Generación de Reportes

- Generar un **reporte de pedidos entregados**.
- Crear un **ranking de transportistas más eficientes**.

### Interacción con el Usuario

- Los usuarios deben poder:
  - Consultar pedidos.
  - Modificar pedidos.
- La interacción con el sistema debe estar **separada de la lógica de negocio**.

### Persistencia de Datos

- Los pedidos y transportistas deben almacenarse en:
  - Una **base de datos relacional** o en **archivos**.
- La persistencia debe estar **desacoplada** de la lógica de negocio.

### Extensibilidad y Flexibilidad

- Permitir la adición de **nuevos tipos de envíos** sin modificar el código existente.
- Separar responsabilidades para garantizar:
  - **Bajo acoplamiento**.
  - **Alta cohesión**.

---

## Restricciones

- El diseño debe permitir la interacción con el usuario, asegurando una **distribución adecuada de responsabilidades**.
- Aplicar los principios **SOLID** y **GRASP** de forma clara y justificable.
- Las clases de persistencia deben estar **desacopladas** de la lógica de negocio.
- Encapsular las reglas de negocio en **clases especializadas**.
- Las clases de interacción con el usuario no deben acceder directamente a la base de datos o lógica de negocio.
- Diseñar un mecanismo flexible para la **asignación de pedidos a transportistas**.

---

## Criterios de Evaluación

### Aplicación de Principios SOLID

- **SRP**: ¿Se evita que las clases tengan múltiples responsabilidades?
- **OCP**: ¿Es fácil extender el sistema sin modificar el código existente?
- **LSP**: ¿Se respeta el principio en las jerarquías de clases?
- **DIP**: ¿Se evita la dependencia rígida entre clases?

### Aplicación de Principios GRASP

- ¿Las responsabilidades están bien distribuidas según:
  - **Creator**.
  - **Expert**.
  - **Controller**.
  - **Polymorphism**.
  - **Low Coupling**.
  - **High Cohesion**?
- ¿Se utiliza **Indirection** y **Pure Fabrication** cuando corresponde?

### Calidad del Diagrama de Clases

- Claridad en las relaciones y asociaciones entre clases.
- Uso correcto de:
  - **Herencia**.
  - **Composición**.
  - **Agregación**.
- Implementación de interfaces y patrones de diseño si es necesario.

### Justificación del Diseño

- Explicación del uso de cada principio en el diseño.
- Argumentación sobre cómo las decisiones mejoran la **mantenibilidad** y **extensibilidad** del sistema.

---

## Entregables

1. **Diagrama de clases UML** detallado con todas las entidades relevantes y sus relaciones.
2. **Justificación** explicando cómo se aplicaron **SOLID** y **GRASP** en el diseño.
3. **Esbozo de la estructura del código** (opcional, por bonificación).
4. Explicación de la interacción entre las distintas partes del sistema, destacando la **separación de responsabilidades**.
