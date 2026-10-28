# pruebas de código.
Es necesario crear uno o mas proyectos para la revisión del codigo.

## pruebas unitarias

### ClienteService
* CrearClienteAsync: crea cliente valido.
* CrearClienteAsync: rechaza RUT duplicado.
* ActualizarClienteAsync: actualiza campos permitidos.
* EliminarClienteAsync: elimina cliente existente.
* ValidarRutUnicoAsync: retorna false cuando existe duplicado.

### ProductoService
* CrearProductoAsync: crea producto valido.
* CrearProductoAsync: rechaza codigo duplicado.
* ActualizarProductoAsync: mantiene reglas de negocio.
* EliminarProductoAsync: elimina producto existente.
* ValidarCodigoUnicoAsync: valida unicidad de codigo.

### FacturaService
* CrearFacturaAsync: crea factura en estado Borrador.
* AgregarItemAsync: agrega item y recalcula totales.
* QuitarItemAsync: elimina item y recalcula totales.
* RecalcularTotalesAsync: calcula Subtotal, Iva y Total correctamente.
* EmitirFacturaAsync: cambia estado de Borrador a Emitida.
* AnularFacturaAsync: cambia estado a Anulada y registra motivo.

### UsuarioService
* CrearUsuarioAsync: crea usuario con rol valido.
* ValidarCredencialesAsync: acepta credenciales correctas.
* ValidarCredencialesAsync: rechaza password incorrecta.
* CambiarPasswordAsync: actualiza hash de password.
* DesactivarUsuarioAsync: deja usuario en estado inactivo.

### LogService
* RegistrarInfoAsync: guarda log nivel Info.
* RegistrarWarningAsync: guarda log nivel Warning.
* RegistrarErrorAsync: guarda log nivel Error con detalle tecnico.
* BuscarLogsAsync: filtra por fecha, nivel y modulo.

## pruebas de integracion

### FacturasController
* Create (POST): persiste factura con detalle en base de datos.
* Edit (POST): actualiza encabezado y mantiene consistencia de totales.
* Delete (POST): elimina factura o aplica anulacion segun regla de negocio.

### ClientesController
* Create (POST): crea cliente y redirige a Index.
* Edit (POST): actualiza cliente existente.
* Delete (POST): elimina cliente sin dependencias activas.

### ProductosController
* Create/Edit/Delete: ejecutan CRUD completo contra SQLite de pruebas.

### Repositorios (Infrastructure)
* ClienteRepository: consultas por Id y filtros.
* ProductoRepository: busqueda por codigo.
* FacturaRepository: carga factura con detalle (Include).

### Persistencia EF Core + SQLite
* Aplicacion de migraciones en base de datos de pruebas.
* Restricciones de FK entre Cliente, Factura y DetalleFactura.
* Restricciones de unicidad (Email usuario, Rut cliente, Codigo producto, Folio factura).

## pruebas de interfaz de usuario

### Playwright - autenticacion
* Login exitoso con usuario valido.
* Login fallido con credenciales invalidas.
* Redireccion a login para usuario no autenticado.

### Playwright - clientes
* Crear cliente desde formulario MVC.
* Validaciones de campos requeridos en cliente.
* Edicion y eliminacion de cliente desde grilla.

### Playwright - productos
* Crear producto con precio valido.
* Mensajes de error al ingresar datos invalidos.

### Playwright - facturacion
* Crear factura, agregar items y verificar total en pantalla.
* Emitir factura y verificar cambio de estado.
* Anular factura y verificar estado final.

### Playwright - navegacion y errores
* Navegacion entre modulos principales (Clientes, Productos, Facturas).
* Visualizacion de mensajes de error controlados ante fallas esperadas.
