# 3. Diseño del Sistema

## 3.1 Arquitectura Lógica

> Se adoptará una arquitectura **Monolítica Modular** para la versión inicial, compatible con entornos de hosting compartido. La aplicación se construirá como un único proyecto (backend Laravel), pero su código interno estará rigurosamente separado en módulos para facilitar su mantenimiento y una futura migración.

## 3.2 Diseño de Base de Datos

> Se utilizará una base de datos relacional (**MySQL** o **PostgreSQL**, según soporte del hosting) para asegurar la consistencia de los datos.

**Diagrama Entidad-Relación (conceptual):**

-   **Tabla `Sorteos`**:
    -   `id` (PK)
    -   `tipo_sorteo` (ENUM: 'lista', 'numeros')
    -   `configuracion` (JSON: para guardar detalles)
    -   `fecha_creacion` (Timestamp)
-   **Tabla `Certificados`**:
    -   `id_unico` (PK, UUID)
    -   `sorteo_id` (FK a `Sorteos.id`)
    -   `resultado` (JSON: para guardar ganadores y suplentes)
    -   `fecha_generacion` (Timestamp)

## 3.3 Prototipo de Interfaz de Usuario (Guía de Estilo)

> El diseño se basará en un estilo **lúdico y amigable**.
-   **Paleta de Colores:** Colores primarios vivos y alegres.
-   **Tipografía:** Fuentes sans-serif con bordes redondeados.
-   **Iconografía:** Iconos con estilo de ilustración "flat" o de dibujos animados.
-   **Animaciones:** Fluidas, rápidas y con un toque "elástico" (bouncy).

## 3.4 Arquitectura Física

> Para el lanzamiento inicial, la plataforma se desplegará en un entorno de **hosting compartido** que soporte **Node.js, PHP y bases de datos SQL**. Esta decisión prioriza la minimización de costos operativos.
```
