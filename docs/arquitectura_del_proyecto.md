# Arquitectura del proyecto

## Visión general

Arquitectura cliente-público: PWA (frontend en React + TypeScript) que consume Firebase (Authentication, Firestore / Realtime DB, Storage) para datos y recursos. Soporte offline mediante cache y almacenamiento local con sincronización.

## Componentes principales

- Frontend (React + TypeScript)
  - Páginas: Login, Dashboard, Cuentas, Nueva Transacción, Historial, Ajustes/Alertas
  - UI: sistema de diseño (colores, tipografías, componentes reutilizables)
- Backend gestionado: Firebase
  - Auth: Google Sign-In
  - DB: Firestore (colecciones: users, accounts, transactions, alerts)
  - Storage: fotos de comprobantes
  - Reglas de seguridad: reglas por documento basadas en `uid`

## Modelo de datos (resumen)

- users/{userId}
  - displayName, email, createdAt
- accounts/{accountId}
  - userId, name, type, currency, balance
- transactions/{transactionId}
  - accountId, userId, amount, type (expense/income), category, date, merchant, receiptUrl, createdAt
- alerts/{alertId}
  - userId, accountId, threshold, direction, enabled

## Sincronización y offline

- Usar IndexedDB (por ejemplo, mediante Workbox o librería local) para cache y colas de sincronización.
- Conflictos: estrategia "last-write-wins" inicialmente; documentar mejora a futuro.

## Seguridad y permisos

- Reglas Firestore limitando lectura/escritura solo a documentos con `userId` igual al `request.auth.uid`.
- Validaciones básicas en frontend y reglas de servidor.

## Despliegue

- PWA servida desde hosting estático (Firebase Hosting o similar).
- Integración CI/CD opcional para deploy automático en entorno de staging/producción.

## Consideraciones futuras

- Soporte multiusuario/compartir cuentas.
- Exportar/importar CSV y conectores bancarios.
