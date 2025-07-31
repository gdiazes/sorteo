# 1. Especificación de Requisitos del Software (SRS)

**Versión:** 1.0
**Fecha:** 24/10/2023

## 1.1 Introducción

### Propósito del Software
> Ofrecer una herramienta online, gratuita y fácil de usar, diseñada específicamente para el entorno educativo. Busca facilitar a los docentes y educadores la creación de actividades lúdicas, como sorteos para asignar grupos, elegir participantes para una actividad, o realizar concursos de manera transparente, justa y motivadora para los estudiantes.

### Alcance del Proyecto
> La primera versión del sistema (MVP) se centrará en dos funcionalidades esenciales para el uso en clase:
> 1.  **Sorteo de Listas:** Permitirá al personal docente introducir una lista de estudiantes para seleccionar aleatoriamente uno o varios participantes.
> 2.  **Sorteo de Números:** Permitirá definir un rango numérico para elegir preguntas de una evaluación, temas de exposición o cualquier otra actividad numerada.

## 1.2 Descripción General del Sistema

### Interfaces del Usuario
> La interfaz web será minimalista y de una sola página (Single Page Application) para maximizar la velocidad y la facilidad de uso. El diseño evitará cualquier paso innecesario y se centrará en permitir al docente realizar un sorteo en el menor número de clics posible.

## 1.3 Requisitos Funcionales (RF)

-   **RF1: Sorteo de Lista:** El sistema permitirá al usuario introducir una lista de participantes. Al procesar el sorteo, el sistema deberá **eliminar automáticamente cualquier nombre duplicado** para asegurar que cada participante tenga una única oportunidad. El sistema también **normalizará las entradas** (ignorando mayúsculas/minúsculas y espacios extra) para tratar "ana", " Ana " y "ANA" como el mismo participante.

-   **RF2: Sorteo de Números:** El sistema permitirá al usuario especificar un rango numérico (mínimo y máximo). Si se solicita más de un número ganador, el sistema deberá asegurar que todos los números seleccionados sean únicos (**selección sin repetición**).

-   **RF3: Configuración de Ganadores y Suplentes:** El sistema deberá permitir al usuario especificar el número de "Ganadores" y, opcionalmente, el número de "Suplentes" para cada sorteo.

-   **RF4: Certificado de Validez:** Tras realizar un sorteo, se generará una página web pública con una URL única que servirá como certificado. Dicha página mostrará la fecha, configuración, participantes y resultados del sorteo.

## 1.4 Requisitos No Funcionales (RFN)

-   **RFN1: Desempeño:** El sistema debe ser capaz de gestionar y procesar sorteos con **hasta 5,000 participantes**. La generación del resultado para el escenario de carga máxima deberá completarse en menos de 5 segundos.

-   **RFN2: Usabilidad:** La interfaz debe ser intuitiva y el flujo principal debe ser autoexplicativo, sin requerir un manual de usuario.

-   **RFN3: Seguridad e Imparcialidad:** Para garantizar la equidad, el sistema deberá implementar un algoritmo de generación de números pseudoaleatorios (PRNG) de alta calidad, preferiblemente uno criptográficamente seguro (CSPRNG).
```

