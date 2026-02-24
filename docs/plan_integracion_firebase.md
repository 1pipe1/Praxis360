# Plan de integración con Firebase

## Resumen

Este documento describe los pasos, configuraciones y reglas mínimas para integrar la app con Firebase (Auth, Firestore, Storage y Hosting). Incluye ejemplos de reglas y comandos de despliegue.

## Pasos de configuración inicial

1. Crear un proyecto en Firebase Console.
2. Habilitar Google Sign-In en la sección Authentication > Sign-in method.
3. Crear una base de datos Firestore en modo nativo (o modo bloqueado y luego abrir reglas según necesidades).
4. Habilitar Firebase Storage para recibos.
5. (Opcional) Habilitar Firebase Hosting para publicar la PWA.

## Variables de entorno

- `VITE_FIREBASE_API_KEY`
- `VITE_FIREBASE_AUTH_DOMAIN`
- `VITE_FIREBASE_PROJECT_ID`
- `VITE_FIREBASE_STORAGE_BUCKET`
- `VITE_FIREBASE_MESSAGING_SENDER_ID`
- `VITE_FIREBASE_APP_ID`

Guardar en un archivo `.env.local` (no commitear) y acceder desde `import.meta.env.VITE_FIREBASE_*`.

## Estructura recomendada en Firestore

- `users/{userId}`
- `users/{userId}/accounts/{accountId}` (opcional: subcolección)
- `transactions/{transactionId}` con campo `userId` o `transactions` como subcolección en `users/{userId}`.
- `alerts/{alertId}` o subcolección en `users/{userId}`

Nota: elegir entre subcolecciones o colecciones planas según necesidades de consultas y seguridad.

## Reglas de seguridad (ejemplos)

Archivo de ejemplo: `firestore.rules` (ver en la raíz del repo).

- Principios:
  - Solo usuarios autenticados pueden leer/escribir sus datos.
  - Validaciones básicas de esquema (tipos y rangos).

Ejemplo básico incluido en `firestore.rules`.

## Reglas de Storage (ejemplo)

Archivo de ejemplo: `storage.rules` (ver en la raíz del repo).

- Principio: solo el usuario propietario puede subir/leer sus recibos en `receipts/{userId}/{file}`.

## Emuladores y pruebas locales

- Instalar `firebase-tools` globalmente: `npm i -g firebase-tools`.
- Usar `firebase init emulators` para iniciar emuladores de Auth, Firestore y Storage.
- Ejecutar `firebase emulators:start` para pruebas locales.

## Despliegue

- Comandos habituales:

```bash
firebase login
firebase init hosting firestore storage
firebase deploy --only hosting,firestore,storage
```

Para CI/CD usar `firebase-tools` en pipeline con las mismas credenciales/secretos.

## Buenas prácticas y consideraciones

- Mantener lógica sensible validada tanto en frontend como en reglas de Firestore.
- Hacer backups periódicos de Firestore (export) si los datos son críticos.
- Implementar límites y cuotas para evitar abusos (firestore rules + límites de uso).
- Documentar las decisiones de modelo de datos en `docs/arquitectura_del_proyecto.md`.
