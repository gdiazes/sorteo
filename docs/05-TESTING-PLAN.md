# 5. Plan de Pruebas

## 5.1 Estrategia de Pruebas
> Se implementará una estrategia de pruebas automatizadas completa que abarcará tanto el backend como el frontend, complementada con pruebas manuales exploratorias antes de cada lanzamiento.

## 5.2 Caso de Prueba Detallado

**Caso de Prueba #1: Normalización de la Lista de Participantes**
-   **Funcionalidad:** Sorteo de Lista.
-   **Objetivo:** Verificar que el sistema normaliza correctamente las entradas para garantizar la equidad.
-   **Pasos:**
    1.  Ir a "Sorteo de Lista".
    2.  Introducir la lista: `[Pedro, MARÍA, pedro, " susana "]`
    3.  Configurar para 1 ganador.
    4.  Hacer clic en "Sortear".
-   **Salida Esperada:** El ganador debe ser uno de los 3 participantes únicos (`Pedro`, `MARÍA` o `susana`). El certificado debe reflejar solo 3 participantes.

## 5.3 Herramientas de Pruebas
-   **Backend (Laravel):** **PHPUnit** para pruebas unitarias y de integración.
-   **Frontend (Vue.js):** **Vitest** para pruebas de componentes.
-   **Integración Continua (CI):** **GitHub Actions** para ejecutar las pruebas automáticamente en cada `push`.
```
