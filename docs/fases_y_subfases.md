# Fases y subfases del proyecto

## Fase 1 — Documentación y maquetación (HTML/CSS)

1.1 Requisitos y alcance

- Objetivo: completar `docs/alcance_del_proyecto.md` con requisitos funcionales y no funcionales.
- Entregable: documento de alcance aprobado.

  1.2 Wireframes y sistema de diseño

- Objetivo: definir wireframes móviles y el `sistema_de_diseño.md` con tokens y componentes.
- Entregable: kit de diseño y wireframes en PNG/SVG.

  1.3 Maquetación estática

- Objetivo: maquetar las páginas clave en HTML/CSS responsivo (sin React aún).
- Entregable: prototipos HTML/CSS para Login, Dashboard, Cuentas, Transacción.

  1.4 Revisión y aceptación

- Criterio: maquetación aprobada y accesible (contraste, labels, responsive).

## Fase 2 — Frontend y PWA (React + TypeScript) + Firebase

2.1 Inicialización del proyecto

- Objetivo: scaffold con Vite + React + TypeScript, configuraciones (ESLint, Prettier).
- Entregable: repo inicial con `npm run dev` funcionando.

  2.2 Componentización y UI

- Objetivo: implementar componentes del `sistema_de_diseño.md` y páginas principales.
- Entregable: componentes reutilizables, layout y navegación.

  2.3 Soporte PWA y offline

- Objetivo: añadir Service Worker (Workbox o similar) y estrategias de cache.
- Entregable: app instalable y funcionalidades básicas offline.

  2.4 Integración Firebase

- Objetivo: conectar Firebase Auth (Google Sign-In), Firestore, y Storage.
- Entregable: autenticación funcional, lectura/escritura de transacciones y subida de recibos.

  2.5 Sincronización y manejo de conflictos

- Objetivo: implementar cola de sincronización e IndexedDB para datos offline.
- Criterio: cambios offline se sincronizan al reconectar; documentar estrategia de conflictos.

  2.6 Pruebas básicas

- Objetivo: pruebas unitarias para lógica crítica y pruebas manuales de flujo.

## Fase 3 — QA, despliegue y mantenimiento

3.1 Pruebas de usuario y correcciones

- Objetivo: pruebas funcionales y ajuste de UX.

  3.2 Configuración CI/CD y despliegue

- Objetivo: pipeline para deploy a Firebase Hosting (opcional: staging/production).

  3.3 Monitorización y mejoras

- Objetivo: métricas básicas (errores, uso) y roadmap de features (compartir cuentas, export CSV).

## Notas sobre entregables y criterios

- Cada subfase debe incluir en `docs/` los artefactos generados (wireframes, decisiones de diseño, scripts de deploy, reglas de seguridad de Firestore).
