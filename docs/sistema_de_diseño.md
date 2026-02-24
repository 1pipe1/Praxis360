# Sistema de diseño (borrador)

## Tokens básicos

- Colores:
  - Primario: #6a81ac
  - Secundario: #0f3f31
  - Fondo: #FFFFFF
  - Superficie: #F4F6F8
  - Texto principal: #111827
  - Texto secundario: #6B7280

- Tipografía:
  - Familia principal: Inter, system-ui, sans-serif
  - Escalas: H1 32px, H2 24px, H3 18px, Body 16px, Small 14px

## Componentes principales

- `Button`: variantes primary/secondary/ghost
- `Input`: text, number, date, selector de categoría
- `Card`: para mostrar cuentas y transacciones
- `TopBar` / `BottomNav`: navegación principal (PWA móvil)
- `TransactionForm`: formulario para nueva transacción (monto, cuenta, categoría, tienda, foto)

## Layout

- Grid principal de 1 columna para móvil; contenedor con max-width para pantallas grandes.

## Accesibilidad

- Contraste de color mínimo 4.5:1 para texto importante.
- Soporte para navegación por teclado y labels en formularios.

## Entregables del sistema de diseño

- Paleta de colores y tokens (CSS variables)
- Kit de componentes básicos en React (documentados)
- Guía de uso (espacings, iconografía, patrones de interacción)
