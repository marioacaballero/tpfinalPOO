# Gestión Administrativa de un Club

## Objetivo del Sistema

Permitir la gestión de los socios y actividades que se realizan en un Club.

### Diseño

El sistema debe poseer un Administrador del Club, que tendrá como mínimo las siguientes responsabilidades:

1. Gestión de Personas
2. Gestión de Socios
3. Gestión de Cobros (si es una compra de entrada para un evento, hay que darlo de alta en la lista de
   participantes del evento. En ese caso hay que controlar que no supere la capacidad de la instalación)
4. Gestión de Actividades
5. Gestión de Eventos
6. Gestión de Instalaciones
7. Gestión de Inscripciones a actividades (controlar que no supere la capacidad)
8. Gestión de Gastos
9. Determinar si una instalación se encuentra libre para ser utilizada entre fechas y rango horario
10. Resumen de Ingresos y Gastos entre fechas, con totales
11. Socios activos que no han pagado un mes aún
12. Cantidad de inscriptos a cada actividad
13. Lista de inscriptos a un evento

Agregar AL MENOS 3 consultas más, definidas por ustedes, teniendo en cuenta lo que consideren
importante para el correcto funcionamiento de la aplicación.

### Clases Mínimas (se pueden adaptar/modificar)

**Persona**: mantiene información sobre las personas que gestiona el sistema, ya sean socios, asistentes a eventos, u otros (id, nombre, dni, fecha nacimiento, sexo, domicilio, email, celular).

**Socio**:(id, fechaAlta, idPersona, estado [activo, inactivo, suspendido]). Se considera que los socios tienen derecho a asistir a cualquier actividad con solo pagar su cuota. No obstante, deben estar inscriptos en esas actividades. La comprar de entradas a eventos tiene un descuento del 20% para los socios.

**Cobro**:(id, idPersona, fecha, descripción, monto) Representa la recepción de dinero por distintas razones, por ejemplo, por pago de la cuota social o por la compra de entradas para un evento.

- **CobroCuota**: (mes y año que paga)
- **CobroEvento**: (idEvento)
- **Donación**: (propósito)

**Actividad**:(id, nombre, descripción, capacidad, idInstalacion, idPersonaResponsable, estado [activa, inactiva], horario (el horario es una lista de dias de la semana y rango de horas en las cuales se desarrolla la actividad. Por ejemplo, lunes de 15 a 17hs y miercoles de 16 a 20hs), participantes (ésta es una lista de las personas que participan de la actividad. Todos ellos deben ser socios).

**Evento**:(id, nombre, descripción, idinstalación, idPersonaResponsable, fecha, duración, costo, participantes (lista de personas, pueden o no, ser socios))

**Instalación**: (id, nombre, descripción, largo, ancho, capacidad). Representa las instalaciones del Club. Puede ser una cancha de fútbol, una pileta, un salón, etc.

**Gasto**: (id, fecha, monto, descripción, tipo [impuesto, servicio, compra, otro])

Nota: Las clases CobroCuota, CobroEvento y Donación heredan de Cobro. De manera similar, se puede crear una superclase de Actividad y Evento que represente cualquier tipo de actividad, ya que el Evento es una actividad especial, mientras que la clase que está definida como Actividad representa una actividad regular o periodica.

### Actividades

1. Defina las clases necesarias para resolver la lógica del negocio, teniendo en cuenta que el software debe ser programado en Smalltalk y que las listas deben ser mantenidas en disco.
2. Defina la interfaz e integre todas las clases.
3. Cargue datos suficientes como para realizar pruebas sobre el funcionamiento del sistema.
