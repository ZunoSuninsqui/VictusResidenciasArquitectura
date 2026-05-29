# VictusResidenciasArquitectura
## 👥 Integrantes del Proyecto

| Nombre | Rol | Programa Académico | Institución |
|---------|------|--------------------|--------------|
| **Andrés Vélez** | Desarrollador Full Stack / Documentación Técnica | Ingeniería de Sistemas | Universidad Católica de Oriente |
| **Juan Pablo Avendaño** | Desarrollador Frontend / UI y Diseño de Componentes | Ingeniería de Sistemas | Universidad Católica de Oriente |
| **Tomás Gómez Cifuentes** | Desarrollador Backend / Integración con Spring Boot | Ingeniería de Sistemas | Universidad Católica de Oriente |

---
# 🏠 Victus Residencias  

![Logo Victus Residencias](https://raw.githubusercontent.com/andrias01/UcoChallengeVictus/master/imagenes/logo.png)

## 📘 Presentación General

**Victus Residencias** es una plataforma integral para la **gestión de conjuntos residenciales**, desarrollada por estudiantes de la **Universidad Católica de Oriente (UCO)**.  
El proyecto implementa una **arquitectura distribuida basada en microservicios** desplegada en **Microsoft Azure**, con un enfoque en **seguridad, disponibilidad y escalabilidad**.

### 🌐 Arquitectura General

- **Frontend:** React (Vite + Tailwind + ShadCN/UI)
- **Backend:** Spring Boot 3.5.x (Java 21)
- **Base de Datos:** PostgreSQL (persistencia principal)
- **Infraestructura:** Azure App Service, Azure Database for PostgreSQL
- **Seguridad:** OAuth2 + JWT, Azure Key Vault, Web Application Firewall
- **Observabilidad:** Azure Monitor + Application Insights
- **Control de versiones:** GitHub
- **Despliegue:** CI/CD con GitHub Actions

---

## 🧩 Modelo de Clases

![Modelo de Clases](https://raw.githubusercontent.com/andrias01/UcoChallengeVictus/master/imagenes/modeloClases.png)

Representa las entidades principales del dominio: `ConjuntoResidencial`, `Residente`, `Reserva`, `Administrador`, `ZonaComún`, y sus relaciones. Define la base estructural del sistema y sus asociaciones.

---

## 🧮 Modelo MER (Entidad–Relación)

![Modelo MER](https://raw.githubusercontent.com/andrias01/UcoChallengeVictus/master/imagenes/modeloMER.png)

Este modelo refleja el esquema físico de la base de datos en PostgreSQL, definiendo llaves primarias, foráneas y relaciones 1:N y N:M entre las tablas del sistema.

---

## 🔄 Modelo de Actividades

![Modelo de Actividades](https://raw.githubusercontent.com/andrias01/UcoChallengeVictus/master/imagenes/DiagramaActividades.png)

El diagrama de actividades representa el flujo de negocio para los procesos clave:
- Registro de conjuntos residenciales
- Registro y validación de residentes
- Reservas en zonas comunes
- Confirmación y seguimiento de turnos

---

## 🧱 Modelo de Objetos

![Modelo de Objetos](https://raw.githubusercontent.com/andrias01/UcoChallengeVictus/master/imagenes/ModeloObjetos.png)

Describe instancias específicas de clases y cómo interactúan en tiempo de ejecución dentro de un escenario concreto de gestión residencial.

---

## ⚙️ Modelo de Estados

![Modelo de Estados](https://raw.githubusercontent.com/andrias01/UcoChallengeVictus/master/imagenes/DiagramaEstados.png)

Muestra los estados posibles de una **Reserva**:
- Pendiente  
- Confirmada  
- En uso  
- Finalizada  
- Cancelada  

---

## ☁️ Modelo de Despliegue

### 🧭 Arquitectura de referencia

![Arquitectura](https://raw.githubusercontent.com/andrias01/UcoChallengeVictus/master/imagenes/Arquitectura.png)

### 🧭 Arquetipo de referencia

![Arquetipo](https://raw.githubusercontent.com/andrias01/UcoChallengeVictus/master/imagenes/Arquetipo.png)

### 🧭 Arquitectura Distribuida
Victus Residencias adopta una **arquitectura distribuida con microservicios**, donde cada módulo (Usuarios, Reservas, Administración) se despliega en contenedores independientes dentro del entorno **Azure App Service**.

### 🧱 Bloques de Construcción Adoptados
- Spring Boot Framework  
- PostgreSQL JDBC Driver  
- Azure Key Vault Connector  
- React Frontend SPA  
- OAuth2 / JWT Authentication  

### 🧩 Bloques de Construcción Desarrollados

**Backend:**

![Backend Components](https://raw.githubusercontent.com/andrias01/UcoChallengeVictus/master/imagenes/bloqConstDesaBack.png)

**Frontend:**

![Frontend Components](https://raw.githubusercontent.com/andrias01/UcoChallengeVictus/master/imagenes/bloqConstDesaFront.png)

---

## 🧮 Modelo de Paquetes

![Modelo de Paquetes](https://raw.githubusercontent.com/andrias01/UcoChallengeVictus/master/imagenes/ModeloPaquetes.png)

### 📄 Documentación del Modelo de Paquetes

![Documentación de Paquetes](https://raw.githubusercontent.com/andrias01/UcoChallengeVictus/master/imagenes/DocPaquetes.png)

El modelo de paquetes organiza la aplicación siguiendo una arquitectura **Hexagonal (Ports & Adapters)**, garantizando separación clara entre capas:
- **Domain:** lógica de negocio
- **Application:** casos de uso
- **Infrastructure:** persistencia, API REST, seguridad

En base del lenguaje de programación JAVA

---

## ⚙️ Modelo de Componentes

![Modelo de Componentes](https://raw.githubusercontent.com/andrias01/UcoChallengeVictus/master/imagenes/ModeloComponentes.png)

### 📄 Documentación de Componentes

![Documentación de Componentes](https://raw.githubusercontent.com/andrias01/UcoChallengeVictus/master/imagenes/DocComponentes.png)

Se identifican:
- Componentes **externos**: Java 21, Spring Boot, PostgreSQL JDBC.  
- Componentes **propios**: Microservicio VictusResidencias, CrossCutting, ApplicationCore.

---

## 🔁 Modelo de Secuencia

![Modelo de Secuencia](https://raw.githubusercontent.com/andrias01/UcoChallengeVictus/master/imagenes/ModeloSecuencias.png)

El flujo describe la interacción entre los actores del sistema para el caso de uso: **Registrar Conjunto Residencial**

1. El administrador ingresa los datos (nombre, dirección, ciudad, administrador).  
2. El frontend React envía un `POST /api/conjuntos-residenciales`.  
3. El backend verifica la existencia de ciudad y administrador.  
4. Se persiste el nuevo conjunto residencial en PostgreSQL.  
5. Se retorna una respuesta HTTP `200 OK`.

### 📄 Documentación del Modelo de Secuencia

![Documentación de Secuencia](https://raw.githubusercontent.com/andrias01/UcoChallengeVictus/master/imagenes/DocSecuencia.png)

---

## ⚖️ Trade-Off

![Trade-Off](https://raw.githubusercontent.com/andrias01/UcoChallengeVictus/master/imagenes/trade-Off.png)

Este modelo compara las decisiones arquitectónicas en términos de **seguridad, rendimiento, disponibilidad y mantenibilidad**, priorizando la integración en Azure y la modularidad del código.

---

## 🧠 Mapa de Empatía

![Mapa de Empatía](https://raw.githubusercontent.com/andrias01/UcoChallengeVictus/master/imagenes/MapaEmpatia.png)

El mapa identifica las percepciones, frustraciones y necesidades de los **residentes**, **administradores** y **personal de portería**, garantizando una experiencia centrada en el usuario.

---

## 🎯 Escenarios de Calidad

> **Nota:** Para mejor visualización de la tabla completa, consulta el [documento completo de escenarios](https://shorturl.at/IEAS5)

### Seguridad

#### SEG-CAL_0001: Control de Acceso Basado en Roles
- **Tipo:** Preventivo
- **Objetivo:** Garantizar que solo los usuarios tengan los privilegios apropiados para acceder a funciones administrativas críticas
- **Táctica:** Uso de JWT + OAuth 2.0
- **Criterio de éxito:** Solo usuarios con roles apropiados pueden ejecutar acciones administrativas críticas
- **Medida:** Tiempo de validación < 200 ms; tasa de error = 0%

#### SEG-CAL_0002: Validación Continua de Cumplimiento Regulatorio
- **Tipo:** Detectivo
- **Objetivo:** Asegurar el cumplimiento continuo de regulaciones y normas de protección de datos
- **Táctica:** Bitácoras de Auditoría
- **Criterio de éxito:** Cumplimiento regulatorio ≥ 100%
- **Medida:** Frecuencia de verificación automática cada hora

#### SEG-CAL_0003: Protección de Información Personal de Residentes
- **Tipo:** Preventivo
- **Objetivo:** Garantizar que los datos de los residentes estén cifrados y protegidos contra accesos no autorizados
- **Táctica:** Cifrado de Tránsito
- **Criterio de éxito:** Los intentos de acceso no autorizados se registran y bloquean
- **Medida:** Tiempo de detección ≤ 2 s; tasa de bloqueos 100%

#### SEG-CAL_0004: Gestión Segura de Sesiones de Usuario
- **Tipo:** Detectivo
- **Objetivo:** Proteger las sesiones activas ante comportamientos sospechosos
- **Táctica:** Detección de Anomalías
- **Criterio de éxito:** Sesiones comprometidas se terminan y notifican
- **Medida:** Tiempo de detección < 10 s; tasa de falsos positivos < 2%

#### SEG-CAL_0005: Identificación Temprana de Amenazas Emergentes
- **Tipo:** Proactivo
- **Objetivo:** Detectar amenazas nuevas y responder automáticamente
- **Táctica:** Web Application Firewall
- **Criterio de éxito:** Sistema mitiga amenaza antes de impacto
- **Medida:** Precisión ≥ 85%

### Disponibilidad

#### DISP-CAL_0013: Estabilidad bajo Carga Máxima de Reservas
- **Tipo:** Preventivo
- **Objetivo:** Garantizar rendimiento y respuesta bajo alta demanda
- **Táctica:** Gestión de Rendimiento
- **Criterio de éxito:** 99,5% de solicitudes procesadas sin error
- **Medida:** Latencia < 4 s; disponibilidad del 100%

#### DISP-CAL_0014: Resiliencia de la Sesión ante Inestabilidad de Red
- **Tipo:** Detectivo
- **Objetivo:** Asegurar continuidad del servicio ante fallos de red
- **Táctica:** Tolerancia a Fallos
- **Criterio de éxito:** Reanudación automática
- **Medida:** Reanudación en < 30 s

#### DISP-CAL_0015: Gestión de Agotamiento del Pool de Conexiones
- **Tipo:** Reactivo
- **Objetivo:** Evitar bloqueos por agotamiento de recursos
- **Táctica:** Tolerancia a Fallos
- **Criterio de éxito:** Sin bloqueos HTTP 503
- **Medida:** Tiempo de recuperación ≤ 5 s

#### DISP-CAL_0016: Disponibilidad durante Eliminación Forzada de Entidad
- **Tipo:** Preventivo
- **Objetivo:** Mantener integridad durante operaciones críticas
- **Táctica:** Concurrencia
- **Criterio de éxito:** No se pierden datos ni registros
- **Medida:** Duración < 5 s

#### DISP-CAL_0017: Impacto del Mantenimiento Programado
- **Tipo:** Reactivo
- **Objetivo:** Minimizar tiempo fuera de servicio
- **Táctica:** Mantenimiento con Mínima Interrupción
- **Criterio de éxito:** Disponibilidad ≥ 99%
- **Medida:** Tiempo total de parada < 15 min

---

---

## 🧱 Modelo de Paquetes – Frontend Victus Residencias

![Modelo de Paquetes Frontend](./imagenes/paquetesFront.png)

El modelo de paquetes del **Frontend Victus Residencias** representa la organización modular del sistema React, estructurado para mantener una **arquitectura limpia y escalable**.  
Cada paquete agrupa elementos relacionados según su **rol funcional** en la interfaz de usuario y la lógica del cliente.

### 📦 Descripción de los Paquetes

| Paquete | Descripción | Relaciones principales |
|----------|-------------|-------------------------|
| **assets/** | Contiene íconos, imágenes y recursos gráficos utilizados por el sistema. | Importado por `components/` y `pages/`. |
| **components/** | Contiene los componentes funcionales reutilizables que conforman la interfaz (ej. `Header`, `Dashboard`, `LoginAdmin`, `Property`). | Importa `contexts/`, `cssComponents/`, `loaders/`. |
| **contexts/** | Define los contextos de React (`AdminContext`, `CommonZoneContext`, `PropertyContext`, `PorteroContext`) que gestionan estados globales y comunicación entre vistas. | Usado por `components/` y `pages/`. |
| **cssComponents/** | Contiene las hojas de estilo de cada componente y los estilos globales de la aplicación. | Importado por `components/` y `loaders/`. |
| **loaders/** | Contiene componentes visuales de carga (`LoadingCircle`, `LoadingText`) que proporcionan retroalimentación al usuario. | Usado por `components/` y `pages/`. |
| **pages/** | Define las vistas principales del sistema (ej. `HomePage`, `LoginAdminPage`), donde se integran los componentes y se controlan las rutas del sistema. | Importa `components/`, `contexts/`, `assets/`. |
| **resources/** | Contiene documentación interna, videos e imágenes de referencia del proyecto. | Sin dependencias directas en tiempo de ejecución. |

---

## 🧩 Modelo de Componentes – Frontend Victus Residencias

![Modelo de Componentes Frontend](./imagenes/componentesFront.png)

El modelo de componentes del **Frontend Victus Residencias** muestra la interacción entre las distintas piezas del sistema React y sus dependencias externas.  
Cada componente cumple una función específica dentro del flujo **Vista → Lógica → Comunicación → Backend**.

### ⚙️ Descripción de los Componentes

| Componente | Tipo | Función principal | Dependencias |
|-------------|------|-------------------|---------------|
| **React 19** | Framework base | Motor principal del frontend que gestiona el ciclo de vida de los componentes y el DOM virtual. | `vite`, `react-dom` |
| **Vite** | Bundler | Herramienta de construcción y servidor de desarrollo ultrarrápido. | — |
| **React Router DOM 7.4.x** | Librería | Controla la navegación SPA y la gestión de rutas (`/home`, `/login-admin`, etc.). | `react` |
| **React Icons** | Librería | Provee íconos vectoriales reutilizables para la interfaz. | `react` |
| **Componentes UI (propios)** | Propio | Elementos visuales del sistema (`Dashboard`, `Header`, `NavBurguer`, `AdminManagement`, etc.). | `contexts`, `cssComponents` |
| **Contextos Globales** | Propio | Gestionan el estado global y la comunicación entre componentes React. | `react` |
| **CSS Components / Tailwind** | Propio | Controla la apariencia, diseño y coherencia visual del frontend. | — |
| **Loaders** | Propio | Proveen animaciones y retroalimentación visual durante procesos asíncronos. | `cssComponents` |
| **API Backend (VictusResidencias)** | Externo | Realiza la comunicación con el backend Spring Boot mediante llamadas HTTP (fetch o axios). | `react` |
| **GitHub Pages / Azure Static Web Apps** | Externo | Infraestructura de despliegue para el frontend React. | `vite build` |

---

## 🧠 Resumen Técnico

| Categoría | Propósito | Tecnología |
|------------|------------|-------------|
| **Framework base** | Construcción modular de la interfaz de usuario | React 19 + Vite |
| **Arquitectura de presentación** | Componentes funcionales, Context API y Hooks | React Context + Hooks |
| **Diseño visual** | Estilos desacoplados y componentes reutilizables | Tailwind / CSS |
| **Navegación** | Rutas SPA y manejo de estado entre vistas | React Router DOM |
| **Comunicación backend** | Consumo de servicios REST del backend VictusResidencias | Fetch API / Axios |
| **Infraestructura** | Despliegue estático y CI/CD | GitHub Pages / Azure Static Web Apps |

---

## 👥 Integrantes del Proyecto

| Nombre | Rol | Programa Académico | Institución |
|---------|------|--------------------|--------------|
| **Andrés Vélez** | Desarrollador Full Stack / Documentación Técnica | Ingeniería de Sistemas | Universidad Católica de Oriente |
| **Juan Pablo Avendaño** | Desarrollador Frontend / UI y Diseño de Componentes | Ingeniería de Sistemas | Universidad Católica de Oriente |
| **Tomás Gómez Cifuentes** | Desarrollador Backend / Integración con Spring Boot | Ingeniería de Sistemas | Universidad Católica de Oriente |

---

📘 *Proyecto académico desarrollado como parte del curso de Ingenieria de Software 2 — Universidad Católica de Oriente (2025).*

---


## 🧾 Autoría

**Universidad Católica de Oriente (UCO)**  
Proyecto desarrollado por estudiantes del programa **Ingeniería de Sistemas**

**Especificaciones Técnicas:**
- **Año:** 2025  
- **Arquitectura:** Microservicios distribuidos en Azure  
- **Lenguaje principal:** Java 21  
- **Framework:** Spring Boot 3.5.x  
- **Base de datos:** PostgreSQL  
- **Frontend:** React + Vite  
- **Infraestructura:** Azure Cloud Services  
