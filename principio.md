# principios de diseño

* OOP, programacion orientada a objetos para modelar entidades y relaciones del dominio contable
* SRP, responsabilidad unica para cada clase y metodo
* KISS, mantener el codigo simple y facil de entender
* DRY, no repetir codigo, abstraer logica comun en servicios y repositorios
* YAGNI, no implementar funcionalidades que no se necesiten actualmente
* SOLID, aplicar principios de diseño orientado a objetos para mantener el codigo flexible y mantenible,
siempre y cuando no tenga problemas con los otros principios de diseño

## recomendaciones adicionales
* Use clase de modelos o entidades cuando corresponda.
* Use servicios para encapsular logica de negocio y repositorios para acceso a datos.
* Priorice composicion sobre herencia para reducir acoplamiento.
* Mantenga bajo acoplamiento y alta cohesion entre clases y modulos.
* Defina contratos claros (interfaces) en capas de aplicacion e infraestructura.
* Agregue pruebas unitarias para reglas de negocio criticas antes de refactorizar.

