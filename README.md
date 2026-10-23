# PruebaAppFacturas — Control de pagos Efast

Aplicación web estática para llevar registro de pagos a cuenta del proyecto de Forrajería Efast y emitir constancias **no fiscales**.

## Uso

Abrir `index.html` en un navegador moderno o publicarlo en un servidor web estático. No requiere instalación, compilación, backend, servicios pagos ni cuentas externas.

1. Verificar los datos precargados: presupuesto total ARS 700.000, primer pago ARS 50.000 (17/10/2026) y segundo pago ARS 50.000 (20/10/2026). **El importe del segundo pago se dedujo del saldo indicado y su fecha se infirió del martes de esa semana: confirmar ambos antes de emitir o enviar documentos.**
2. Para corregir un pago: eliminar el registro erróneo y volver a cargarlo.
3. Registrar nuevos pagos con fecha, importe y medio de pago. El saldo se recalcula automáticamente.
4. Seleccionar un pago del historial y usar **Imprimir / Guardar PDF** (destino: «Guardar como PDF»).
5. Ingresar el número de Salomón en formato internacional, por ejemplo Argentina: 549 + código de área + número. Pulsar **Preparar WhatsApp**. Se abrirá un mensaje precompletado, que **debe enviarse manualmente**. El PDF debe adjuntarse manualmente si se desea compartir el documento.

## Datos y privacidad

- Almacenamiento: `localStorage` del navegador y dispositivo en uso. No hay sincronización entre equipos, autenticación ni copias automáticas.
- Generar y conservar **Exportar respaldo JSON** luego de actualizar pagos. Se incluye función de importación que reemplaza los registros solo con confirmación.
- El teléfono del destinatario se guarda localmente; no está preconfigurado.
- Abrir WhatsApp no demuestra que el mensaje haya sido enviado o recibido.
- **No registrar pagos no verificados.** El sistema no consulta bancos ni Mercado Pago.
- Los comprobantes muestran el saldo cronológico *según fecha del pago y número interno*, y no el saldo presente si se selecciona uno antiguo.

## Alcance fiscal

El documento es una **constancia privada de pago, no una factura fiscal**. No tiene CAE, no está autorizado por ARCA y no reemplaza una factura electrónica legal. Para emitir facturas fiscales reales debe desarrollarse otro flujo con los datos tributarios y la autorización pertinente.

## Limitaciones conocidas

Esta es una primera versión de uso individual en un solo navegador. No es apropiada como registro contable principal ni para uso simultáneo en múltiples dispositivos. La numeración de comprobantes es interna y puede repetirse si se eliminan registros antiguos.

## Seguridad

No subir respaldos JSON con datos personales a repositorios públicos. Revisar cuidadosamente fecha, importe y destinatario antes de enviar cualquier comprobante.
