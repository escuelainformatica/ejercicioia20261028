# Seguridad informatica

* El sistema debe cumplir con pruebas de seguridad del codigo.
* OWASP top 10 vulnerabilidades de seguridad en aplicaciones web.
* Para ello, se deben hacer pruebas automaticas, de integracion, unitarias y de interface.

## governación de datos
* Se debe definir un plan de seguridad para el desarrollo del sistema contable.
* Se debe cumplir con las normativas chilenas.
  *	Normas Técnicas de la Ley N° 21.180
  * Ley N° 21.719 (Protección de Datos Personales)

## listado de pruebas de seguridad obligatorias

### pruebas de autenticacion y autorizacion
* Verificar bloqueo o limitacion por intentos fallidos de login.
* Validar politicas de contrasena (largo minimo, complejidad, expiracion si aplica).
* Comprobar que usuarios sin rol no pueden acceder a modulos restringidos.
* Validar cierre de sesion y expiracion de sesion por inactividad.

### pruebas de OWASP Top 10
* Inyeccion SQL: probar entradas en formularios y query strings.
* XSS reflejado/almacenado: probar campos de texto y vistas de detalle.
* CSRF: validar uso de anti-forgery tokens en formularios POST.
* Control de acceso roto: probar acceso directo a URLs de administracion.
* Fallos criptograficos: validar cifrado de datos sensibles y uso de HTTPS.
* Configuracion insegura: revisar cabeceras de seguridad y errores expuestos.
* Componentes vulnerables: ejecutar escaneo de dependencias (NuGet).

### pruebas de API y capa de datos
* Validar que no se expongan datos sensibles en respuestas y logs.
* Verificar parametrizacion de consultas en acceso a datos (EF/SQL).
* Probar manejo seguro de errores sin filtrar stack traces al cliente.

### pruebas automatizadas en pipeline (CI)
* Analisis estatico de seguridad del codigo (SAST).
* Escaneo de dependencias y CVEs en paquetes.
* Ejecucion de pruebas unitarias e integracion con escenarios de seguridad.
* Ejecucion de pruebas E2E de seguridad basicas con Playwright.

### pruebas de cumplimiento y datos personales
* Verificar minimizacion de datos personales recolectados.
* Validar trazabilidad de consentimientos y cambios de datos.
* Comprobar anonimizado/mascarado en ambientes no productivos.
* Revisar politicas de retencion y eliminacion de datos segun normativa.


	 
