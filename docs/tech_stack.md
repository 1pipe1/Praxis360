# Tech Stack

## Resumen

Stack elegido para el proyecto:

- Frontend: React + TypeScript
- Estilos: CSS (modular o CSS Modules / CSS-in-JS opcional)
- Backend: Firebase (Authentication, Firestore, Storage, Hosting)
- PWA: Service Worker (Workbox u otra estrategia) para soporte offline

## Justificación

- React + TypeScript: productivo, fuerte tipado, ecosistema para PWA.
- Firebase: acelera autenticación, almacenamiento y sincronización en tiempo real; manejo sencillo de hosting y reglas de seguridad.
- CSS: control total del diseño y rendimiento; posibilidad de usar variables CSS para tokens de diseño.

## Herramientas de desarrollo

- Node.js (LTS)
- Vite o Create React App (preferencia: Vite por rapidez)
- ESLint + Prettier
- Husky (ganchos pre-commit) opcional

## Dependencias clave (ejemplo)

- react, react-dom, typescript
- firebase
- workbox-window (para registrar service worker)

## Notas de configuración

- Configurar Firebase project y exportar variables de configuración en `.env`.
- Habilitar Google Sign-In en la consola de Firebase.
