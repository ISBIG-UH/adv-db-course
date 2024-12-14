

# Complementos de Bases de Datos: Propuesta de plan de asignatura

## Información básica

- **Objetivo**: Complementar los contenidos de la asignatura de Bases de Datos I y Bases de Datos II de la Licenciatura en Ciencia de la Computación. Incluyendo temas de amplia utilización en el panorama actual de base de datos como es la utilización de plataformas de virtualización y orquestración, escalabilidad y alta disponibilidad, optimización y NoSQL.
- **Requisitos de acceso al curso**:
  - Haber culminado 2do año de la Licenciatura de Ciencia de la Computación o Licenciatura en Ciencia de Datos.
- **Evaluación**: Implementación de alguno de los escenarios de uso de los distintos modelos de datos vistos durante el curso
- **Objetivos ocultos**: Utilización de proyectos finales para mejorar los ejemplos del curso de Bases de Datos en LCD y como punto de partida para trabajos de investigación. Implementar repositorios de código con la infraestructura para el curso de data warehousing.

## Plan de la Asignatura

El plan de la asignatura se divide en 3 temas principales: infraestructura (2 clases), optimización (1 clase) y NoSQL (5 clases). El plan se encuentra detallado a continuación.

## C1: Introducción a Docker. Despliegue de sistemas de bases de datos

### Objetivos

- Introducción a la herramienta de virtualización **Docker**
- Los componentes básicos de un sistema de base de datos: sistema gestor de base de datos, administrador de base de datos y sistema de monitoreo.
- Despliegue de un sistema de ejemplo utilizando **PostgreSQL**, **pgAdmin**, **Prometheus** y **Grafana**.

### Estructura 

1. **Introducción a Docker** (20 mins)
   - Conceptos básicos (contenedores, imágenes, volúmenes y redes)
   - Comandos básicos y ficheros (dockerfile y compose)
   - Ventajas de utilizar Docker para el despliegue de bases de datos (aislamiento, utilización de distintas versiones, despliegue en paralelo)
2. **Presentación del proyecto de clase** (10 mins)
   - Exposición de la arquitectura básica para despleguar un sistema de bases de datos básico consistente en un sistema gestore de bases de datos, un administrador y un sistema de monitoreo
3. **Implementación del proyecto de clase** (50 mins)
   -  Creación de una red en docker para conectar componentes
   - Despliegue de una instancia de PostgreSQL: parámetros, volúmenes, ejecución de código durante el despliegue.
   - Despliegue de una instancia de pgAdmin: conexión entre contenedores, administración de credenciales.
   - Despliegue de una instancia de Prometheus y Grafana: instalación de exportador de métricas, definición de métricas  personalizadas, creación de un panel de control, definición de alertas

### Requisitos de software

- [Docker engine](https://docs.docker.com/engine/install/) o [Docker desktop](https://www.docker.com/products/docker-desktop/)
- [PostgreSQL](https://hub.docker.com/_/postgres)
- [pgAdmin4](https://hub.docker.com/r/dpage/pgadmin4/)
- [Prometheus](https://hub.docker.com/r/prom/prometheus)
- [Grafana](https://hub.docker.com/r/grafana/grafana)
- [Postgres-Exporter](https://hub.docker.com/layers/prometheuscommunity/postgres-exporter/v0.13.1/images/sha256-0798230747f6e4881a50c2907322bd5994a7501459c2e46664b3e49a592befa1)
- [Python](https://hub.docker.com/_/python)

### Referencias

- [Documentación de Docker](https://docs.docker.com/)
- [Documentación de PostgreSQL](https://www.postgresql.org/docs/)
- [Documentación de Prometheus](https://prometheus.io/docs/introduction/overview/)
- [Documentación de Grafana](https://grafana.com/docs/)



## C2: Replicación y arquitecturas de alta disponibilidad (PostgreSQL)

### Objetivos

- Introducir los conceptos básicos relacionados con la escalabilidad y alta disponibilidad de sistemas
- Explicar y ejemplificar las dos formas de replicación en PostgreSQL: replicación lógica y replicación física
- Exponer y ejemplificar la arquitectura de alta disponibilidad (Patroni) para PostgreSQL

### Estructura

1. **Introducción** (10 mins)
   - Conceptos básicos: escalabilidad, alta disponibilidad, distribución y replicación
   - Casos de uso
2. **Replicación en PostgreSQL** (30 mins)
   - Replicación lógica. Unificación de bases de datos participadas. Proyecto de ejemplo.
   - Replicación física. Copias de seguridad. Proyecto de ejemplo.
3. **Alta disponibilidad en PostgreSQL** (40 mins)
   - Explicación de la arquitectura Patroni. Configuración distribuida y balance de cargas. 
   - Implementación de un proyecto de ejemplo

### Requisitos de software

- [Docker engine](https://docs.docker.com/engine/install/) o [Docker desktop](https://www.docker.com/products/docker-desktop/)
- [PostgreSQL](timescale/timescaledb-ha:pg15-all)
- [pgAdmin4](https://hub.docker.com/r/dpage/pgadmin4/)
- [Prometheus](https://hub.docker.com/r/prom/prometheus)
- [Grafana](https://hub.docker.com/r/grafana/grafana)
- [Postgres-Exporter](https://hub.docker.com/layers/prometheuscommunity/postgres-exporter/v0.13.1/images/sha256-0798230747f6e4881a50c2907322bd5994a7501459c2e46664b3e49a592befa1)
- [Python](https://hub.docker.com/_/python)
- [Etcd](https://quay.io/repository/coreos/etcd?tab=tags&tag=latest)
- [HAProxy](https://hub.docker.com/_/haproxy/)

### Referencias

- [Replicación en PostgreSQL](https://www.postgresql.org/docs/current/runtime-config-replication.html)
- [Patroni](https://patroni.readthedocs.io/en/latest/)



## C3: Introducción a la optimización en bases de datos

### Objetivos

- Definir las estructuras básicas y métodos esenciales para la optimización de consultas
- Métodos de optimización de infraestructura. Optimización de conexiones, balanceo de carga
- Desafíos para la optimización en bases de datos relacionales. Introducción a otros modelos de datos

### Estructura

1. **Optimización de consultas** (40 mins)
   - Índices, multiplicidad, plan de ejecución
2. **Optimización de infraestructura** (25 mins)
   - Connection pool, tablas particionadas, vistas materializadas
3. **Introducción a otros modelos de datos** (15 mins)
   - Trailer del curso de data warehousing con la ejemplificación de cómo el modelo multidimensional y bases de datos columnares mejoran la eficiencia de las consultas.
   - Mencionar los otros modelos NoSQL que se darán durante el curso

### Requisitos de software

- [Docker engine](https://docs.docker.com/engine/install/) o [Docker desktop](https://www.docker.com/products/docker-desktop/)
- [PostgreSQL](timescale/timescaledb-ha:pg15-all)
- [pgAdmin4](https://hub.docker.com/r/dpage/pgadmin4/)

### Referencias

- [Documentación de Docker](https://docs.docker.com/)
- [Documentación de PostgreSQL](https://www.postgresql.org/docs/)



## C4: Modelo de datos: llave-valor

### Objetivos

- Definir las características y ventajas principales del modelo
- Casos de uso 
- Proyectos de ejemplo

### Estructura

1. **Definir las características y ventajas principales del modelo** (por definir)
2. **Análisis de casos de uso** (por definir)
3. **Implementación de un proyecto de ejemplo** (por definir)

### Requisitos de software

Por definir

### Referencias

Por definir



## C5: Modelo de datos: documental

### Objetivos

- Definir las características y ventajas principales del modelo
- Casos de uso 
- Proyectos de ejemplo

### Estructura

1. **Definir las características y ventajas principales del modelo** (por definir)
2. **Análisis de casos de uso** (por definir)
3. **Implementación de un proyecto de ejemplo** (por definir)

### Requisitos de software

Por definir

### Referencias

Por definir



## C6: Modelo de datos: orientado a grafos

### Objetivos

- Definir las características y ventajas principales del modelo
- Casos de uso 
- Proyectos de ejemplo

### Estructura

1. **Definir las características y ventajas principales del modelo** (por definir)
2. **Análisis de casos de uso** (por definir)
3. **Implementación de un proyecto de ejemplo** (por definir)

### Requisitos de software

Por definir

### Referencias

Por definir



## C7: Modelo de datos: serie de tiempo

### Objetivos

- Definir las características y ventajas principales del modelo
- Casos de uso 
- Proyectos de ejemplo

### Estructura

1. **Definir las características y ventajas principales del modelo** (por definir)
2. **Análisis de casos de uso** (por definir)
3. **Implementación de un proyecto de ejemplo** (por definir)

### Requisitos de software

Por definir

### Referencias

Por definir



## C8: Modelo de datos: vectores

### Objetivos

- Definir las características y ventajas principales del modelo
- Casos de uso 
- Proyectos de ejemplo

### Estructura

1. **Definir las características y ventajas principales del modelo** (por definir)
2. **Análisis de casos de uso** (por definir)
3. **Implementación de un proyecto de ejemplo** (por definir)

### Requisitos de software

Por definir

### Referencias

Por definir
