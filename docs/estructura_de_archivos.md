# Estructura de archivos propuesta

## Estructura raíz (sugerida)

- `package.json` - dependencias y scripts
- `tsconfig.json` - configuración TypeScript
- `.env` - variables de entorno (no subir a VCS)
- `firebase.json` - configuración de Firebase Hosting / Functions
- `public/` - assets públicos
- `src/` - código fuente
- `docs/` - documentación (ya existente)

## `src/` (detalle)

- `src/main.tsx` - entrada de la app
- `src/App.tsx` - router principal / layout
- `src/pages/` - pages (Login, Dashboard, Accounts, TransactionForm, History, Settings)
- `src/components/` - componentes reutilizables (Button, Input, Card, Nav, Modal)
- `src/styles/` - tokens CSS, variables, estilos globales
- `src/assets/` - imágenes, iconos
- `src/services/` - integraciones con APIs (ej. `firebase.ts`)
- `src/hooks/` - hooks personalizados (`useAuth`, `useOfflineSync`)
- `src/context/` - providers de contexto (AuthContext, UIContext)
- `src/models/` - definiciones de tipos e interfaces (Transaction, Account, User)
- `src/utils/` - utilidades y helpers
- `src/routes/` - configuración de rutas y guards
- `src/sw/` - service worker / Workbox hooks
- `src/tests/` - pruebas unitarias / e2e

## Archivos de configuración recomendados

- `.eslintrc`, `.prettierrc`, `vite.config.ts`, `jest.config.ts` (si se usan tests)

## Buenas prácticas

- Separar lógica de presentación (components) de la lógica de datos (services/hooks).
- Mantener `services/firebase.ts` como único punto de entrada para llamadas a Firebase.
- Versionar `docs/` y actualizar `README.md` con cambios importantes.
