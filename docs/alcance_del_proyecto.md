# Alcance del proyecto

## Propósito

Crear una PWA que permita a usuarios registrar y controlar su balance personal mediante transacciones (gastos e ingresos), gestionar múltiples cuentas (ej. caja, tarjeta, banco) y recibir alertas cuando los saldos alcancen umbrales definidos.

## Objetivos del MVP

- Permitir registro e inicio de sesión con Google Sign-In.
- Registrar transacciones (fecha, monto, categoría, cuenta, tienda opcional, foto opcional).
- Visualizar saldos por cuenta y balance total.
- Definir alertas/presupuestos por cuenta y recibir notificaciones in-app cuando se alcancen umbrales.
- Soporte offline con sincronización cuando haya conexión.

## Entregables

- Interfaz maquetada en HTML/CSS (fase 1).
- Frontend en React + TypeScript con estilos CSS.
- Integración con Firebase para autenticación y almacenamiento (fase 2).
- Documentación técnica y de diseño en `docs/`.

## Exclusiones (fuera del alcance inicial)

- Integración con pasarelas de pago.
- Publicación nativa en tiendas móviles (a menos que se decida wrapper).
- Módulos avanzados de contabilidad fiscal.

## Criterios de aceptación

- Usuario puede autenticarse con Google y ver su dashboard.
- Usuario puede crear cuentas y registrar transacciones con éxito.
- Alertas se disparan según umbrales configurados y se muestran en la UI.

## Riesgos y dependencias

- Dependencia de Firebase para autenticación y sincronización.
- Gestión de datos offline requiere estrategia de sincronización y conflicto.
