# UNIDAD-4-BASE-DE-DATOS-EJERCICIO-10
1. Entidades Principales
vehiculo: Almacena el parque automotor disponible para las operaciones logísticas. Sus campos principales son la patente (clave primaria), numero_chasis, anio_fabricacion, marca, modelo y kilometraje.

chofer: Registra la información personal y legal de los conductores de la flota. Contiene id_chofer (clave primaria), nombre, apellido, dni, fecha_vencimiento_licencia y categoria_licencia.

taller: Administra los talleres mecánicos o proveedores de servicios de mantenimiento externos. Sus atributos son cuit (clave primaria), nombre y direccion.

2. Tablas de Operaciones y Control
viajes: Gestiona los trayectos y envíos realizados por la flota. Sus campos son id_viaje (clave primaria), fecha, origen, destino, carga_kg y patente (clave foránea que indica qué vehículo realizó el viaje).

carga_combustible: Controla el consumo de combustible de los vehículos. Posee los atributos id_carga (clave primaria), fecha, litros_cargados, costo_litro, lectura_odometro y patente (clave foránea).

mantenimiento: Registra las reparaciones, servicios mecánicos e intervenciones técnicas realizadas a los vehículos. Sus campos incluyen id_mantenimiento (clave primaria), fecha_ingreso, costo, descripcion, repuestos_utilizados, cuit (clave foránea hacia el taller) y patente (clave foránea hacia el vehículo).

3. Tablas Intermedias (Relaciones Muchos a Muchos)
asignacion_chofer: Tabla asociativa que vincula los viajes con los choferes asignados, permitiendo registrar qué rol desempeña cada conductor en un determinado trayecto. Su clave primaria es compuesta por (id_viaje, id_chofer) e incluye el campo rol.

4. Restricciones e Integridad Referencial (Foreign Keys)
El script configura de manera estricta las reglas de validación para asegurar la consistencia relacional mediante las siguientes restricciones:

fk_asignacion_chofer y fk_asignacion_viaje: Conectan la asignación de choferes con las tablas correspondientes de conductores y viajes.

fk_carga_vehiculo: Relaciona los registros de carga de combustible con el vehículo respectivo.

fk_mantenimiento_taller y fk_mantenimiento_vehiculo: Aseguran que cada mantenimiento esté asociado a un taller registrado y a un vehículo de la flota.

fk_viaje_vehiculo: Garantiza que todo viaje se realice con un vehículo válido existente en el sistema.

IMAGEN DE EJEMPLO DE UNA CONSULTA:
<img width="1206" height="367" alt="image" src="https://github.com/user-attachments/assets/650a85d4-e042-4ecf-aa1b-9b4904f5ee33" />
