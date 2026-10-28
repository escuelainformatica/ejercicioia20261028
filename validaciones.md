# validaciones

## modelos

### Usuario
* Nombre: requerido, largo entre 3 y 120.
* Email: requerido, formato valido, unico.
* PasswordHash: requerido.
* Rol: requerido, valores permitidos `Administrador` o `Operador`.
* FechaCreacion: requerido, no mayor a fecha actual.

### Cliente
* Rut: requerido, formato valido, unico.
* RazonSocial: requerido, largo entre 3 y 200.
* Direccion: requerido.
* ComunaId: requerido, debe existir en tabla Comuna.
* Email: opcional, si viene debe tener formato valido.

### Comuna
* Codigo: requerido, unico.
* Nombre: requerido.

### Producto
* Codigo: requerido, unico.
* Nombre: requerido.
* PrecioUnitario: requerido, mayor que 0.

### Factura
* Folio: requerido, unico.
* FechaEmision: requerido, no futura.
* ClienteId: requerido, debe existir.
* Estado: requerido, valores `Borrador`, `Emitida`, `Anulada`.
* Subtotal/Iva/Total: mayores o iguales a 0.

### DetalleFactura
* FacturaId: requerido.
* ProductoId: requerido, debe existir.
* DescripcionItem: requerido.
* Cantidad: requerido, mayor que 0.
* PrecioUnitario: requerido, mayor que 0.
* PorcentajeDescuento: entre 0 y 100.
* MontoDescuento: mayor o igual a 0.
* SubtotalLinea/IvaLinea/TotalLinea: mayores o iguales a 0.

### LogSistema
* Fecha: requerido.
* Nivel: requerido, valores `Info`, `Warning`, `Error`.
* Modulo: requerido.
* Mensaje: requerido.

## servicios

### reglas generales
* Validar existencia de entidades relacionadas antes de guardar.
* Validar unicidad en campos de negocio (email, rut, codigo, folio).
* Rechazar cambios de estado no permitidos en facturas.
* Centralizar mensajes de error de negocio.

