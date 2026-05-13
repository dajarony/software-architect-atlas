# The Software Architect Atlas v2.1

A prompt framework that turns any app idea into a complete technical
blueprint — with risk analysis, phased roadmap, and execution contract.

## What it does

Paste your idea in 2-3 sentences. Get back:

- Full technical architecture (stack, database, auth, infrastructure)
- Every screen and component defined
- What NOT to build in the MVP (Anti-Features)
- The risk that will kill your project in Week 2 — before you write code
- A phased roadmap with verifiable Definition of Done per phase
- The exact first 10 commands to start building

## How to use

1. Copy the full prompt block below
2. Paste it into a new Claude conversation
3. Replace `[DESCRIBE TU IDEA AQUÍ]` with your app idea in 2-3 sentences
4. Claude returns the complete blueprint
5. Execute each phase in a separate conversation

### Workflow Post-Blueprint

1. **Save it** — It's your reference document for the entire project
2. **Phase 1** — New chat: "Execute Phase 1. [paste Phase 1 + Definition of Done]"
3. **Phase 2** — New chat: "Execute Phase 2. Context: [Phase 1 summary + Phase 2]"
4. **Repeat** — Each phase in its own chat with necessary context
5. **Consult** — Reference any section by number when in doubt

### Tips

- Review the blueprint BEFORE coding — changing architecture on paper is free
- Use Anti-Features as a filter every time you want to add something to the MVP
- Update the blueprint when you make decisions that differ from the original
- If the blueprint is too long, ask Claude to split it into 2 responses

---

## The Prompt

> Copy everything between the ═══ lines and paste into a new Claude chat.

[as esto y solo  esto Abre un chat nuevo con Claude, pega el prompt del Atlas completo, y donde dice [DESCRIBE TU IDEA AQUÍ] pon exactamente la descripción que escribiste:

## Instrucciones de Uso

1. Copia todo el bloque de prompt de abajo (desde ═══ hasta ═══ final)
2. Pégalo en una conversación nueva de Claude
3. Rellena `[DESCRIBE TU IDEA AQUÍ]` con tu app en 2-3 frases
4. Claude te devuelve el blueprint completo
5. Toma cada fase del ASSEMBLY LOGIC y ejecútala en conversaciones separadas

### Workflow Post-Blueprint

1. **Guárdalo** — Es tu documento de referencia para todo el proyecto
2. **Fase 1** — Chat nuevo: "Ejecuta la Fase 1 del blueprint. [pega la Fase 1 + Definition of Done]"
3. **Fase 2** — Chat nuevo: "Ejecuta la Fase 2. Contexto: [resumen Fase 1 + Fase 2 completa]"
4. **Repite** — Cada fase en su propio chat con el contexto necesario
5. **Consulta** — Si tienes dudas, referencia la sección del blueprint por número

### Tips

- Si el blueprint es demasiado largo, pide que lo divida en 2 respuestas
- Revisa el blueprint ANTES de codear — cambiar arquitectura en papel es gratis
- Actualiza el blueprint cuando tomes decisiones que difieran del original
- Usa las Anti-Features como filtro cada vez que quieras añadir algo al MVP

---

## PROMPT — Copiar desde aquí

```
Actúa como un arquitecto de software senior con 15 años de experiencia
diseñando sistemas SaaS, apps móviles y plataformas de alto tráfico.

Tu tarea es deconstruir la siguiente idea de aplicación en un blueprint
técnico completo, accionable y listo para ejecutar fase por fase.

══════════════════════════════════════════════════════════════
REGLAS DE PRECISIÓN v2.1
══════════════════════════════════════════════════════════════
- No diseñes una app perfecta: diseña una app CONSTRUIBLE.
- Prioriza MVP funcional sobre arquitectura excesiva.
- Toda decisión técnica debe tener una justificación práctica.
- Si algo no es necesario para validar el producto, muévelo a V2 o V3.
- Identifica explícitamente lo que NO se hará en el MVP (Anti-Features).
- Señala el mayor riesgo técnico que podría matar el proyecto en Semana 2.
- Elige UNA librería visual y mantenla en todas las pantallas. No mezcles.
- Cada fase debe tener Definition of Done verificable y concreta.
- Si una estimación es incierta, indica:
  * Suposición tomada
  * Nivel de confianza: alto/medio/bajo
  * Qué dato faltaría para decidir mejor
- No inventes costes, límites o restricciones como si fueran exactos.
- Elige tecnologías concretas y justifica cada decisión.
- No des opciones abiertas — decide como si fueras el CTO del proyecto.
- Responde en español.
- Usa tablas para listas de features y modelos de datos.
- Señala riesgos técnicos donde los veas.

══════════════════════════════════════════════════════════════
IDEA DE APP:
[DESCRIBE TU IDEA AQUÍ EN 2-3 FRASES. Incluye: qué hace, para quién,
y cómo genera valor o ingresos]
══════════════════════════════════════════════════════════════


══════════════════════════════════════════════════════════════
01 — HERO OBJECT (Identidad del Producto)
══════════════════════════════════════════════════════════════
Define:
- Nombre propuesto para la app
- Propuesta de valor en UNA frase (máx 15 palabras)
- Problema concreto que resuelve
- Usuario objetivo (perfil demográfico y técnico)
- Modelo de negocio (freemium, SaaS, one-time, marketplace, etc.)
- Competidores directos y qué harías diferente
- Métrica norte (la única métrica que define el éxito)


══════════════════════════════════════════════════════════════
02 — THE SHELL (Capa de Presentación)
══════════════════════════════════════════════════════════════
Define:
- Framework frontend elegido y por qué (elige uno, no listes opciones)
- Librería de componentes UI elegida:
  * Elige UNA sola (shadcn/ui, Mantine, Headless UI, NativeWind, etc.)
  * Justifica la elección según el tipo de app
  * Regla: esta librería se usa en TODAS las pantallas. No mezclar.
- Sistema de diseño:
  * Paleta de colores (hex codes)
  * Tipografía principal y secundaria
  * Componentes base reutilizables (botones, cards, modals, inputs)
- Lista de TODAS las pantallas/vistas con:
  * Nombre de la pantalla
  * Propósito en una línea
  * Componentes principales que contiene
- Plataformas objetivo (web, iOS, Android, desktop)
  * Si es multiplataforma: estrategia (PWA, React Native, Capacitor, nativo)
- UX Patterns críticos:
  * Navegación principal
  * Onboarding flow
  * Estados vacíos, loading, error
  * Accesibilidad mínima requerida


══════════════════════════════════════════════════════════════
03 — CORE COMPONENTS (Motor Interno)
══════════════════════════════════════════════════════════════
Define:
- Backend: lenguaje y framework (elige uno, justifica)
- Base de datos principal:
  * Tipo (SQL/NoSQL/Graph) y motor específico
  * Justificación basada en el tipo de datos de la app
- Base de datos secundaria (si aplica):
  * Para caché, sesiones, colas, búsqueda, etc.
- Sistema de autenticación:
  * Método (JWT, sessions, OAuth, magic links)
  * Proveedores (Google, GitHub, email/password)
  * Gestión de roles y permisos (RBAC, ABAC)
- APIs externas necesarias:
  * Servicio → propósito → coste estimado
- Servicios internos (módulos o microservicios):
  * Nombre → responsabilidad → dependencias
- Sistema de colas/workers (si aplica):
  * Para qué tareas asíncronas
  * Tecnología elegida
- Almacenamiento de archivos:
  * Dónde (S3, GCS, local) y para qué tipo de archivos
- Notificaciones:
  * Canales (email, push, SMS, in-app)
  * Servicio elegido para cada canal


══════════════════════════════════════════════════════════════
04 — STACK & FASTENERS (Infraestructura)
══════════════════════════════════════════════════════════════
Define:
- Hosting/Deploy:
  * Proveedor elegido y por qué
  * Arquitectura (serverless, containers, VPS, PaaS)
  * Regiones/zonas
- CI/CD Pipeline:
  * Herramienta (GitHub Actions, GitLab CI, etc.)
  * Pasos del pipeline: lint → test → build → deploy
  * Estrategia de branching (trunk-based, gitflow, etc.)
- Entornos:
  * Development → Staging → Production
  * Cómo se promueve código entre ellos
- Dominio, DNS, SSL:
  * Registrador recomendado
  * CDN (si aplica)
- Costes estimados mensuales (indica nivel de confianza):
  * Tier MVP (0-100 usuarios): $___/mes
  * Tier Growth (100-1K usuarios): $___/mes
  * Tier Scale (1K-10K usuarios): $___/mes
  Desglose por servicio.


══════════════════════════════════════════════════════════════
05 — EXPLODED VIEW (Arquitectura en 5 Capas)
══════════════════════════════════════════════════════════════
Descompón la app en exactamente 5 capas verticales.
Para CADA capa indica: tecnología, responsabilidades exactas,
y cómo se comunica con la capa superior e inferior.

Capa 1 — PRESENTACIÓN
  Lo que ve y toca el usuario.
  * Tecnología:
  * Responsabilidades:
  * Se comunica con Capa 2 mediante:

Capa 2 — API GATEWAY
  Punto de entrada de todas las peticiones.
  * Tecnología:
  * Endpoints principales (agrupar por recurso):
  * Autenticación/autorización en esta capa:
  * Versionado de API:

Capa 3 — LÓGICA DE NEGOCIO
  Reglas, validaciones, procesos, workflows.
  * Módulos principales:
  * Reglas de negocio críticas:
  * Validaciones que NO dependen del frontend:

Capa 4 — DATOS
  Persistencia, modelos, migraciones.
  * ORM/Query builder:
  * Modelos principales:
  * Estrategia de migraciones:
  * Seeds/datos iniciales necesarios:

Capa 5 — INFRAESTRUCTURA
  Servers, cache, CDN, storage, networking.
  * Servicios cloud utilizados:
  * Configuración de red:
  * Estrategia de backups:


══════════════════════════════════════════════════════════════
06 — COMPONENT MAP (Mapa de Features)
══════════════════════════════════════════════════════════════
Lista CADA feature/módulo necesario clasificado en:

[MVP] — Imprescindible para el primer lanzamiento funcional
[V2]  — Segunda iteración (primer mes post-launch)
[V3]  — Futuro / nice-to-have (3-6 meses post-launch)

Para cada feature:
| Prioridad | Feature | Descripción (1 línea) | Complejidad | Depende de |
|-----------|---------|----------------------|-------------|------------|
| [MVP]     | ...     | ...                  | Baja/Media/Alta | ... |

Ordena por dependencias: las features sin dependencias primero.

ANTI-FEATURES DEL MVP:
Lista al menos 3 funcionalidades que NO se construirán en el MVP,
aunque parezcan útiles o tentadoras.

Para cada una:
| No entra en MVP | Por qué no entra | Riesgo que evita | Reconsiderar en |
|-----------------|------------------|------------------|-----------------|
| ...             | ...              | ...              | V2 / V3 / Nunca |

Regla: Si dudas entre meter algo en MVP o no, NO lo metas.


══════════════════════════════════════════════════════════════
07 — DATA BREAKDOWN (Modelos de Datos)
══════════════════════════════════════════════════════════════
Para CADA entidad principal:

Entidad: [Nombre]
  Campos:
    - nombre_campo: tipo (restricciones) — descripción
  Relaciones:
    - relación con [OtraEntidad]: tipo (1:1, 1:N, N:N)
  Índices recomendados:
    - campo(s) → justificación

Después de listar todas las entidades:

FLUJO DE DATOS PRINCIPAL:
Describe paso a paso cómo viaja la información en el flujo
más importante de la app:
  Usuario hace X → Frontend envía Y → API valida Z →
  Lógica procesa W → DB guarda V → Respuesta U

FLUJO DE DATOS SECUNDARIO:
Describe un segundo flujo importante (ej: notificaciones,
reportes, sincronización offline, etc.)


══════════════════════════════════════════════════════════════
08 — FAIL-FAST RISK (Riesgo que Mata el Proyecto)
══════════════════════════════════════════════════════════════
Antes de planificar las fases, identifica los riesgos letales.

RIESGO TÉCNICO PRINCIPAL:
  - Descripción del riesgo:
  - Por qué puede matar el proyecto:
  - Cómo detectarlo en menos de 7 días:
  - Prueba mínima para validarlo (prototipo, spike, PoC):
  - Criterio de éxito/fracaso de la prueba:
  - Plan B si el riesgo se confirma:

RIESGO DE PRODUCTO:
  - ¿Hay evidencia de que alguien quiere esto?
  - ¿Cómo validar demanda antes de construir todo?
  - Señal mínima que confirma que vale la pena seguir:

RIESGO DE NEGOCIO:
  - ¿El modelo de negocio funciona con los costes estimados?
  - ¿A partir de cuántos usuarios es rentable?
  - ¿Hay dependencia de un tercero que pueda cambiar términos?

Regla: Si el Riesgo Técnico Principal no se valida en Semana 1,
NO se avanza a Fase 2.


══════════════════════════════════════════════════════════════
09 — ASSEMBLY LOGIC (Roadmap de Construcción en 6 Fases)
══════════════════════════════════════════════════════════════
Divide el desarrollo completo en 6 fases secuenciales.
Cada fase debe ser ejecutable de forma independiente y producir
un entregable funcional.

FASE 1 — FUNDACIÓN (Semana 1-2)
  Objetivo:
  Tareas concretas:
    1.
    2.
    3.
  Entregable: [qué funciona al terminar esta fase]
  Definition of Done:
    - [ ] Backend levanta sin errores
    - [ ] Base de datos conecta y migraciones ejecutadas
    - [ ] Auth funcional (login/register/logout)
    - [ ] Deploy a staging funcional
    - [ ] Variables de entorno documentadas
    - [ ] Tests básicos de auth pasando
    - [ ] Fail-Fast Risk validado

FASE 2 — CORE FEATURES (Semana 3-5)
  Objetivo:
  Tareas concretas:
    1.
    2.
    3.
  Entregable:
  Definition of Done:
    - [ ] Endpoints core funcionando y documentados
    - [ ] Pantallas principales navegables y conectadas al backend
    - [ ] CRUD completo de las entidades principales
    - [ ] Tests de los flujos críticos pasando
    - [ ] Datos de prueba (seeds) funcionales

FASE 3 — UI/UX POLISH (Semana 6-7)
  Objetivo:
  Tareas concretas:
    1.
    2.
    3.
  Entregable:
  Definition of Done:
    - [ ] Todas las pantallas con diseño final aplicado
    - [ ] Responsive verificado en móvil y desktop
    - [ ] Estados vacíos, loading y error implementados
    - [ ] Navegación principal fluida y sin bugs
    - [ ] Onboarding flow completo

FASE 4 — INTEGRACIONES (Semana 8-9)
  Objetivo:
  Tareas concretas (APIs externas, pagos, notificaciones):
    1.
    2.
    3.
  Entregable:
  Definition of Done:
    - [ ] Cada integración externa funcional en staging
    - [ ] Fallbacks implementados si la API externa falla
    - [ ] Pagos procesando correctamente en modo test
    - [ ] Notificaciones enviándose y recibiéndose
    - [ ] Tests de integración pasando

FASE 5 — TESTING & SECURITY (Semana 10-11)
  Objetivo:
  Tareas concretas:
    1.
    2.
    3.
  Entregable:
  Definition of Done:
    - [ ] Cobertura de tests mínima alcanzada (indicar %)
    - [ ] CORS configurado por entorno
    - [ ] Rate limiting activo en endpoints sensibles
    - [ ] Headers de seguridad configurados
    - [ ] Validación de inputs en backend verificada
    - [ ] Secrets en variables de entorno, no en código
    - [ ] Auditoría básica de seguridad pasada

FASE 6 — LAUNCH & GROWTH (Semana 12+)
  Objetivo:
  Tareas concretas:
    1.
    2.
    3.
  Entregable:
  Definition of Done:
    - [ ] App desplegada en producción
    - [ ] Dominio y SSL configurados
    - [ ] Analytics/tracking activo
    - [ ] Health checks respondiendo
    - [ ] Alertas configuradas
    - [ ] Primer usuario real registrado
    - [ ] Proceso de onboarding validado con usuario real


══════════════════════════════════════════════════════════════
10 — SECURITY & HARDENING
══════════════════════════════════════════════════════════════
Define configuración concreta para:

CORS:
  - Orígenes permitidos por entorno (dev, staging, prod)
  - Métodos permitidos
  - Headers expuestos
  - Credentials: sí/no y por qué

RATE LIMITING:
  - Estrategia global (requests/minuto por IP)
  - Rate limits específicos por tipo de endpoint:
    * Auth (login, register, reset): ___/minuto
    * API pública: ___/minuto
    * API autenticada: ___/minuto
    * Uploads: ___/minuto
  - Algoritmo (sliding window, token bucket, etc.)
  - Storage del rate limiter (Redis, memoria, etc.)
  - Respuesta cuando se excede (status code, headers, retry-after)

PROTECCIÓN CONTRA ATAQUES:
  - CSRF: estrategia (tokens, SameSite cookies, etc.)
  - XSS: sanitización de inputs, CSP headers
  - SQL Injection: cómo se previene en la capa de datos
  - Headers de seguridad (Helmet o equivalente):
    * X-Content-Type-Options
    * X-Frame-Options
    * Strict-Transport-Security
    * Content-Security-Policy

VALIDACIÓN DE INPUTS:
  - Frontend: librería y estrategia
  - Backend: librería y estrategia
  - Regla: NUNCA confiar en validación solo del frontend

GESTIÓN DE SECRETS:
  - Variables de entorno: cómo se gestionan por entorno
  - Secrets manager (si aplica)
  - Rotación de API keys
  - .env NUNCA en repositorio — alternativa elegida


══════════════════════════════════════════════════════════════
11 — MULTI-TENANCY (si la app lo requiere)
══════════════════════════════════════════════════════════════
Si la app NO requiere multi-tenancy, indica por qué y salta
esta sección. Si SÍ la requiere:

ESTRATEGIA DE AISLAMIENTO:
  - Tipo elegido:
    * [ ] Schema por tenant (un schema de DB por cliente)
    * [ ] Row-level security (misma tabla, filtro por tenant_id)
    * [ ] Base de datos separada por tenant
  - Justificación de la elección

RESOLUCIÓN DE TENANT:
  - ¿Cómo sabe el sistema a qué tenant pertenece cada request?
    * [ ] Subdominio (tenant1.miapp.com)
    * [ ] Header personalizado
    * [ ] Claim en el JWT token
    * [ ] Path parameter
  - Middleware de resolución: dónde se ejecuta en el pipeline

DATOS COMPARTIDOS vs AISLADOS:
  - Qué datos son globales (planes, configuraciones del sistema)
  - Qué datos son por tenant (usuarios, contenido, settings)
  - Cómo se manejan las migraciones multi-tenant

ONBOARDING DE NUEVOS TENANTS:
  - Proceso automatizado de provisioning
  - Seeds/datos iniciales por tenant
  - Configuración inicial requerida


══════════════════════════════════════════════════════════════
12 — PERFORMANCE & CACHING
══════════════════════════════════════════════════════════════

ESTRATEGIA DE CACHÉ:
  - Qué se cachea:
    * Datos que cambian poco: ___  (TTL: ___ minutos)
    * Datos computados: ___  (TTL: ___ minutos)
    * Assets estáticos: ___  (TTL: ___ horas)
  - Dónde se cachea:
    * Server-side: tecnología (Redis, in-memory, etc.)
    * Client-side: estrategia (SWR, React Query, service worker)
    * CDN: qué rutas/assets
  - Invalidación de caché:
    * Cuándo y cómo se invalida cada tipo de caché

BASE DE DATOS — PERFORMANCE:
  - Índices planificados (campo → tipo de query que optimiza)
  - Prevención de N+1 queries: estrategia
  - Connection pooling: configuración (min, max, idle timeout)
  - Queries lentas: cómo se detectan y optimizan
  - Paginación: estrategia (offset, cursor-based, keyset)

FRONTEND — PERFORMANCE:
  - Code splitting / lazy loading: estrategia
  - Compresión: gzip/brotli
  - Optimización de imágenes: formato (WebP, AVIF), lazy load
  - Bundle size objetivo: ___ KB (gzipped)

TARGETS DE PERFORMANCE:
  - Time to First Byte (TTFB): < ___ ms
  - Largest Contentful Paint (LCP): < ___ s
  - API response time p95: < ___ ms
  - Database query time p95: < ___ ms


══════════════════════════════════════════════════════════════
13 — OBSERVABILIDAD
══════════════════════════════════════════════════════════════

LOGGING:
  - Formato: estructurado (JSON) / texto
  - Niveles: cuándo usar debug, info, warn, error
  - Qué se loguea SIEMPRE:
    * Requests entrantes (método, ruta, status, duración)
    * Errores con stack trace
    * Eventos de autenticación (login, logout, fallos)
    * Operaciones de negocio críticas
  - Qué NUNCA se loguea:
    * Passwords, tokens, datos sensibles del usuario
  - Herramienta de agregación elegida

HEALTH CHECKS:
  - Endpoint /health: qué verifica (DB, Redis, APIs externas)
  - Endpoint /ready: diferencia con health
  - Frecuencia de verificación

ALERTAS:
  - Métricas que disparan alarma:
    * Error rate > ___% en ___ minutos
    * Response time p95 > ___ ms
    * CPU/Memory > ___%
    * Disco > ___%
    * Cola de jobs > ___ pendientes
  - Canal de alertas (Slack, email, PagerDuty)

ERROR TRACKING:
  - Herramienta elegida (Sentry, Bugsnag, etc.)
  - Source maps: sí/no

MÉTRICAS DE NEGOCIO:
  - Analytics elegido
  - Eventos clave a trackear:
    * Signup, Login, Acción principal, Conversión, Churn


══════════════════════════════════════════════════════════════
14 — MAINTENANCE & TECHNICAL DEBT
══════════════════════════════════════════════════════════════
- Top 5 puntos de deuda técnica previsibles:
  * Qué se va a acumular → cuándo atacarlo → cómo mitigarlo
- Estrategia de actualizaciones de dependencias
- Plan de backups y disaster recovery:
  * Frecuencia de backup
  * RTO (Recovery Time Objective)
  * RPO (Recovery Point Objective)
  * Procedimiento de restauración


══════════════════════════════════════════════════════════════
15 — SYSTEM CUTAWAY (Flujo Crítico — Deep Dive)
══════════════════════════════════════════════════════════════
Elige el flujo más complejo e importante de la app y haz un
deep dive completo:

FLUJO ELEGIDO: [nombre del flujo]

DIAGRAMA PASO A PASO:
  1. Usuario hace → ...
  2. Frontend envía → ...
  3. API Gateway recibe → valida → ...
  4. Lógica de negocio → ...
  5. Base de datos → ...
  6. Respuesta → ...
  7. Frontend actualiza → ...

EDGE CASES:
  - ¿Qué pasa si el usuario pierde conexión a mitad del flujo?
  - ¿Qué pasa si la API externa falla?
  - ¿Qué pasa si hay requests concurrentes/duplicados?
  - ¿Qué pasa si los datos son inválidos en paso N?

PUNTOS DE FALLO Y FALLBACKS:
  - Punto de fallo 1 → Fallback:
  - Punto de fallo 2 → Fallback:
  - Punto de fallo 3 → Fallback:

OPTIMIZACIONES:
  - ¿Se puede cachear algo de este flujo?
  - ¿Se puede hacer algo async (colas)?
  - ¿Hay operaciones que se pueden hacer en paralelo?


══════════════════════════════════════════════════════════════
16 — ARCHITECTURE OUTPUT CONTRACT
══════════════════════════════════════════════════════════════
Resume todo el blueprint en un bloque de ejecución directa:

STACK FINAL:
  - Frontend:
  - UI Components:
  - Backend:
  - Base de datos:
  - Auth:
  - Hosting:
  - Storage:
  - Pagos:
  - Analytics:
  - Error tracking:

PRIMEROS 10 ARCHIVOS/CARPETAS A CREAR:
  1.
  2.
  ...
  10.

PRIMEROS 10 COMANDOS DE SETUP:
  1.
  2.
  ...
  10.

ORDEN EXACTO DE CONSTRUCCIÓN:
  Primero → Segundo → Tercero → ...

RIESGOS BLOQUEANTES ANTES DE ESCRIBIR CÓDIGO:
  1.
  2.

Este output contract es la rampa directa del blueprint al código.
```

---

## Changelog v2.0 → v2.1

| Cambio | Sección | Impacto |
|--------|---------|---------|
| Anti-Features del MVP | 06 | Protege contra scope creep |
| Fail-Fast Risk | 08 (nueva) | Detecta riesgos letales antes de codear |
| Definition of Done por fase | 09 | Criterios verificables de progreso |
| Librería UI obligatoria | 02 | Consistencia visual en todo el código |
| Numeración secuencial | Todas | Limpieza y navegación más clara |
| Output Contract | 16 (nueva) | Transición directa de blueprint a código |
| Regla anti-alucinación | Reglas v2.1 | Estimaciones honestas |
| Riesgo de producto/negocio | 08 | No solo técnico, también validación |]

---

## Changelog

| Change | Section | Impact |
|--------|---------|--------|
| Anti-Features | 06 | Protects against scope creep |
| Fail-Fast Risk | 08 | Identifies lethal risks before coding |
| Definition of Done per phase | 09 | Verifiable progress criteria |
| Single mandatory UI library | 02 | Visual consistency across all screens |
| Output Contract | 16 | Direct bridge from blueprint to code |
| Anti-hallucination rules | All | Honest estimates with confidence levels |

---

## License

MIT — Use it freely. Credit appreciated, not required.

Created by [Dajarony Ysaac Guzmán Marmolejos](https://github.com/dajarony)
