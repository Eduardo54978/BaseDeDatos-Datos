-- ============================================================
--   DATOS COMPLETOS - Sistema Empresa Constructora
--   Script unificado con grandes volumenes de datos
-- ============================================================

USE constructora;

SET SQL_SAFE_UPDATES = 0;
SET FOREIGN_KEY_CHECKS = 0;

-- ============================================================
-- GRUPO 1: CATALOGOS
-- ============================================================

INSERT INTO TipoCliente (nombreTipoCliente, descripcionTipoCliente) VALUES
('Persona Natural', 'Cliente individual, persona física'),
('Empresa',         'Cliente corporativo o jurídico');

INSERT INTO EstadoProyecto (nombreEstadoProyecto, descripcionEstadoProyecto) VALUES
('En planificación', 'El proyecto está en fase de diseño y planificación'),
('En ejecución',     'El proyecto está siendo construido activamente'),
('Finalizado',       'El proyecto ha sido completado y entregado'),
('Suspendido',       'El proyecto está temporalmente paralizado');

INSERT INTO TipoProyecto (nombreTipoProyecto, descripcionTipoProyecto) VALUES
('Casa',             'Construcción de vivienda unifamiliar'),
('Edificio',         'Construcción de edificio multifamiliar o comercial'),
('Carretera',        'Construcción o mejoramiento de vías'),
('Puente',           'Construcción de puentes y obras de arte'),
('Local Comercial',  'Construcción de espacios comerciales');

INSERT INTO EstadoContrato (nombreEstadoContrato, descripcionEstadoContrato) VALUES
('Vigente',    'Contrato activo y en cumplimiento'),
('Finalizado', 'Contrato cumplido y cerrado'),
('Rescindido', 'Contrato cancelado antes de su vencimiento');

INSERT INTO TipoContrato (nombreTipoContrato, descripcionTipoContrato) VALUES
('Obra completa',      'Se contrata la ejecución total de la obra'),
('Por etapas',         'La obra se ejecuta y paga por fases'),
('Por administración', 'La empresa administra recursos del cliente');

INSERT INTO EstadoCotizacion (nombreEstadoCotizacion, descripcionEstadoCotizacion) VALUES
('Pendiente', 'Cotización enviada, esperando respuesta'),
('Aprobado',  'Cotización aceptada por el cliente'),
('Rechazado', 'Cotización no aceptada por el cliente');

INSERT INTO Departamento (nombreDepartamento, descripcionDepartamento) VALUES
('Gerencia',     'Dirección y administración general'),
('Obras',        'Ejecución y supervisión de proyectos'),
('Diseño',       'Arquitectura e ingeniería de proyectos'),
('Contabilidad', 'Finanzas, pagos y contabilidad'),
('Logística',    'Compras, materiales y proveedores');

INSERT INTO EstadoOrden (nombreEstadoOrden, descripcionEstadoOrden) VALUES
('Pendiente', 'Orden realizada, esperando entrega'),
('Entregada', 'Materiales recibidos conforme'),
('Cancelada', 'Orden anulada antes de la entrega');

INSERT INTO TipoMaterial (nombreTipoMaterial, descripcionTipoMaterial) VALUES
('Cemento',   'Materiales cementantes y aglomerantes'),
('Acero',     'Varillas, mallas y perfiles de acero'),
('Madera',    'Tablones, vigas y madera en general'),
('Eléctrico', 'Cables, tuberías y accesorios eléctricos'),
('Áridos',    'Arena, grava y piedra triturada'),
('Pintura',   'Pinturas, barnices y selladores'),
('Cerámica',  'Pisos, azulejos y revestimientos');

INSERT INTO UnidadMedida (nombreUnidadMedida, descripcionUnidadMedida) VALUES
('kg',     'Kilogramo'),
('bolsa',  'Bolsa (50 kg)'),
('m',      'Metro lineal'),
('m²',     'Metro cuadrado'),
('m³',     'Metro cúbico'),
('unidad', 'Pieza o unidad'),
('rollo',  'Rollo de cable o manguera'),
('litro',  'Litro');

INSERT INTO EstadoEmpleado (nombreEstadoEmpleado, descripcionEstadoEmpleado) VALUES
('Activo',   'Empleado trabajando actualmente'),
('Inactivo', 'Empleado que ya no trabaja en la empresa');

INSERT INTO RolProyecto (nombreRolProyecto, descripcionRolProyecto) VALUES
('Director',   'Dirige y toma decisiones en el proyecto'),
('Supervisor', 'Supervisa el avance y calidad de la obra'),
('Técnico',    'Ejecuta tareas técnicas especializadas'),
('Operario',   'Realiza trabajos manuales en la obra');

INSERT INTO EstadoPago (nombreEstadoPago, descripcionEstadoPago) VALUES
('Pendiente',  'Pago aún no realizado'),
('Registrado', 'Pago registrado en el sistema'),
('Verificado', 'Pago confirmado y validado'),
('Anulado',    'Pago cancelado o revertido');

INSERT INTO MetodoPago (nombreMetodoPago, descripcionMetodoPago) VALUES
('Transferencia', 'Transferencia bancaria'),
('Cheque',        'Pago mediante cheque'),
('Efectivo',      'Pago en efectivo');

INSERT INTO Cargo (nombreCargo, descripcionCargo) VALUES
('Gerente General',          'Responsable de la dirección general'),
('Jefe de Obra',             'Supervisa la ejecución de obras en campo'),
('Arquitecto',               'Diseño y planificación de proyectos'),
('Ingeniero Civil',          'Cálculo estructural y supervisión técnica'),
('Electricista',             'Instalaciones eléctricas en obra'),
('Albañil',                  'Trabajos de mampostería y acabados'),
('Contador',                 'Gestión contable y financiera'),
('Asistente Administrativo', 'Apoyo en tareas administrativas'),
('Plomero',                  'Instalaciones sanitarias y tuberías'),
('Soldador',                 'Trabajos de soldadura y metalurgia'),
('Carpintero',               'Trabajos en madera y carpintería'),
('Pintor',                   'Trabajos de pintura y acabados');

-- ============================================================
-- GRUPO 2: CLIENTES (20 clientes)
-- ============================================================

INSERT INTO Cliente (nombre, idTipoCliente, documentoID, numCelular, email, direccion, fechaRegistro) VALUES
('Carlos Mendoza Ríos',          1, '7823451',    '70012345', 'carlos.mendoza@gmail.com',      'Av. Heroínas 123',        '2023-01-15'),
('María Fernández Vega',         1, '6541237',    '71023456', 'maria.fernandez@gmail.com',     'Calle Sucre 456',         '2023-03-22'),
('Constructora Horizonte SRL',   2, '1023456789', '72034567', 'contacto@horizonte.com.bo',     'Av. Blanco Galindo Km 5', '2022-11-10'),
('Inmobiliaria Los Andes SA',    2, '2034567890', '73045678', 'info@losandes.com.bo',          'Av. América 789',         '2022-08-05'),
('Roberto Salinas Peña',         1, '5312789',    '74056789', 'roberto.salinas@hotmail.com',   'Calle Baptista 321',      '2024-01-08'),
('Empresa Boliviana Const. SRL', 2, '3045678901', '75067890', 'info@bolivianacnst.com.bo',     'Av. Villazón 100',        '2023-05-20'),
('Ana Lucía Torres',             1, '4123456',    '76078901', 'ana.torres@gmail.com',          'Calle Hamiraya 200',      '2023-07-14'),
('Grupo Inmobiliario Norte SA',  2, '5156789012', '77089012', 'contacto@gruponorte.com.bo',    'Av. Oquendo 300',         '2022-06-30'),
('Pedro Vargas Condori',         1, '6234567',    '78090123', 'pedro.vargas@hotmail.com',      'Zona Norte Bloque 5',     '2024-02-18'),
('Inversiones del Sur Ltda',     2, '7267890123', '79001234', 'info@inversionesdelsur.com',    'Av. Tadeo Haenke 400',    '2023-09-05'),
('Luis Quispe Mamani',           1, '8345678',    '70112345', 'luis.quispe@gmail.com',         'Villa Pagador Zona A',    '2024-03-10'),
('Constructora Andina SA',       2, '9378901234', '71123456', 'info@constructoraandina.com',   'Parque Industrial Sur',   '2022-04-22'),
('Carmen Rosa Flores',           1, '1456789',    '72134567', 'carmen.flores@gmail.com',       'Calle Lanza 500',         '2023-11-30'),
('Desarrollo Urbano Cba SRL',    2, '2489012345', '73145678', 'contacto@desarrollourbano.com', 'Av. Ballivián 600',       '2023-02-14'),
('Jorge Mamani Quispe',          1, '3512345',    '74156789', 'jorge.mamani@gmail.com',        'Calle Punata 700',        '2024-04-05'),
('Edificaciones Modernas SA',    2, '4545678901', '75167890', 'info@edificacionesmod.com',     'Av. 6 de Agosto 800',     '2022-12-18'),
('Sofía Chávez Torrico',         1, '5623456',    '76178901', 'sofia.chavez@gmail.com',        'Calle Baptista 900',      '2024-05-22'),
('Proyectos y Obras Ltda',       2, '6656789012', '77189012', 'info@proyectosyobras.com',      'Zona Sur Calle 10',       '2023-06-08'),
('Miguel Torrico Vega',          1, '7734567',    '78190123', 'miguel.torrico@gmail.com',      'Av. Heroínas 1000',       '2024-06-15'),
('Constr. Familiar Norte SRL',   2, '8767890123', '79201234', 'info@constfamiliar.com',        'Zona Norte Av. Principal','2022-10-25');

-- ============================================================
-- GRUPO 3: PROVEEDORES (10 proveedores)
-- ============================================================

INSERT INTO Proveedor (nombreProveedor, numCelular, email, direccion, ciudad, pais) VALUES
('Cementos Fancesa',         '42201100', 'ventas@fancesa.com.bo',      'Av. Industrial 100',         'Sucre',       'Bolivia'),
('Aceros del Sur SRL',       '72100200', 'info@acerosdelsur.com',      'Parque Industrial Zona Sur', 'Cochabamba',  'Bolivia'),
('Maderería El Pino',        '71300400', 'elpino@gmail.com',           'Calle Comercio 55',          'Cochabamba',  'Bolivia'),
('Electro Materiales SA',    '70400500', 'ventas@electroma.com.bo',    'Av. 6 de Agosto 200',        'La Paz',      'Bolivia'),
('Áridos y Pétreos Norte',   '71500600', 'aridos.norte@gmail.com',     'Carretera al Norte Km 3',    'Cochabamba',  'Bolivia'),
('Pinturas Rex Bolivia',     '72600700', 'ventas@pinturesrex.com.bo',  'Av. América 300',            'Cochabamba',  'Bolivia'),
('Cerámicas del Valle SRL',  '73700800', 'info@ceramicasvalle.com',    'Zona Industrial Este',       'Cochabamba',  'Bolivia'),
('Ferretería Central SA',    '74800900', 'ventas@ferreteriacentral.com','Calle Comercio 100',         'Cochabamba',  'Bolivia'),
('Materiales Bolivia Ltda',  '75900001', 'info@materialesbolivia.com', 'Av. Blanco Galindo Km 8',    'Cochabamba',  'Bolivia'),
('Distribuidora Norte SRL',  '76001002', 'ventas@distribnorte.com',    'Zona Norte Av. Industrial',  'Cochabamba',  'Bolivia');

-- ============================================================
-- GRUPO 4: MATERIALES (15 materiales)
-- ============================================================

INSERT INTO Material (nombreMaterial, idTipoMaterial, idUnidadMedida, precioUnitario, descripcion) VALUES
('Cemento IP-30 Fancesa',    1, 2,  58.00, 'Cemento pórtland IP-30, bolsa 50kg'),
('Varilla de acero 12mm',    2, 1,   8.50, 'Varilla corrugada 12mm diámetro'),
('Varilla de acero 8mm',     2, 1,   5.20, 'Varilla corrugada 8mm diámetro'),
('Tablón de madera 2x8',     3, 3,  35.00, 'Tablón de madera pino 2x8 pulgadas'),
('Cable eléctrico 12AWG',    4, 7,  85.00, 'Cable THW 12 AWG rollo 100m'),
('Arena fina',               5, 5,  80.00, 'Arena fina para construcción m³'),
('Grava 3/4',                5, 5,  95.00, 'Grava triturada 3/4 pulgada m³'),
('Pintura látex blanca',     6, 8,  45.00, 'Pintura látex interior/exterior litro'),
('Piso cerámico 45x45',      7, 4,  65.00, 'Cerámica de piso 45x45 cm m²'),
('Cemento blanco',           1, 2,  90.00, 'Cemento blanco para juntas'),
('Ladrillo 6 huecos',        1, 6,   2.50, 'Ladrillo cerámico 6 huecos'),
('Fierro corrugado 10mm',    2, 1,   6.80, 'Varilla corrugada 10mm diámetro'),
('Madera tornillo 1x3',      3, 3,  18.00, 'Madera tornillo 1x3 pulgadas metro'),
('Tubería PVC 4 pulgadas',   4, 3,  25.00, 'Tubería PVC desagüe 4 pulgadas metro'),
('Pintura esmalte colores',  6, 8,  55.00, 'Esmalte sintético colores litro');

-- ============================================================
-- GRUPO 5: EMPLEADOS
-- 5 Gerentes, 10 Jefes de Obra, 30 Arquitectos,
-- 20 Ingenieros, 15 Electricistas, 40 Albañiles,
-- 5 Contadores, 5 Asistentes, 20 Plomeros,
-- 10 Soldadores, 10 Carpinteros, 10 Pintores
-- ============================================================

-- Gerentes (idCargo=1, idDepartamento=1)
INSERT INTO Empleado (nombre, apellido, ci, fechaNacimiento, especialidad, numCelular, email, direccion, salario, fechaContratacion, idEstadoEmpleado, idCargo, idDepartamento) VALUES
('Juan Pablo',    'Rojas Soria',      '4512378', '1975-05-12', 'Administración de Empresas', '70011111', 'jp.rojas@const.com',      'Av. Oquendo 100',    15000.00, '2010-03-01', 1, 1, 1),
('Marco Antonio', 'Villanueva Paz',   '4623489', '1972-08-20', 'Gestión Empresarial',        '70022222', 'ma.villanueva@const.com', 'Calle Sucre 200',    14500.00, '2011-06-15', 1, 1, 1),
('Rosa Elena',    'Gutierrez Vega',   '4734590', '1978-03-15', 'Administración',             '70033333', 're.gutierrez@const.com',  'Av. Ballivián 300',  14000.00, '2012-01-10', 1, 1, 1),
('Carlos',        'Mendez Flores',    '4845601', '1980-11-30', 'Dirección de Empresas',      '70044444', 'c.mendez@const.com',      'Calle Lanza 400',    15500.00, '2009-09-01', 1, 1, 1),
('Patricia',      'Rios Condori',     '4956712', '1976-07-22', 'Gestión y Dirección',        '70055555', 'p.rios@const.com',        'Av. América 500',    13500.00, '2013-04-20', 1, 1, 1);

-- Jefes de Obra (idCargo=2, idDepartamento=2)
INSERT INTO Empleado (nombre, apellido, ci, fechaNacimiento, especialidad, numCelular, email, direccion, salario, fechaContratacion, idEstadoEmpleado, idCargo, idDepartamento) VALUES
('Luis Alberto',  'Mamani Flores',    '5623489', '1985-08-20', 'Ingeniería Civil',      '71022222', 'l.mamani@const.com',     'Calle Lanza 200',     10000.00, '2017-06-15', 1, 2, 2),
('Pedro',         'Condori Quispe',   '5734590', '1978-11-30', 'Maestro de Obra',       '71033333', 'p.condori@const.com',    'Villa Pagador',         9500.00, '2016-09-01', 1, 2, 2),
('Ramiro',        'Torrico Mamani',   '5845601', '1982-04-15', 'Construcción Civil',    '71044444', 'r.torrico@const.com',    'Zona Sur Bloque 3',     9800.00, '2015-03-10', 1, 2, 2),
('Gonzalo',       'Pérez Vega',       '5956712', '1980-09-25', 'Ingeniería Civil',      '71055555', 'g.perez@const.com',      'Av. Tadeo Haenke 300',  9200.00, '2018-07-20', 1, 2, 2),
('Hernando',      'Flores Cruz',      '5067823', '1983-02-14', 'Construcción',          '71066666', 'h.flores@const.com',     'Calle Punata 400',      9600.00, '2016-11-05', 1, 2, 2),
('Renato',        'Quispe Tarqui',    '5178934', '1981-06-30', 'Obras Civiles',         '71077777', 'r.quispe@const.com',     'Zona Norte Bloque 2',   9400.00, '2017-02-28', 1, 2, 2),
('Freddy',        'Choque Marca',     '5289045', '1979-10-18', 'Maestro Mayor',         '71088888', 'f.choque@const.com',     'Av. Heroínas 600',      9700.00, '2015-08-15', 1, 2, 2),
('Nelson',        'Vargas Aguilar',   '5390156', '1984-03-05', 'Construcción Civil',    '71099999', 'n.vargas@const.com',     'Calle Baptista 700',    9300.00, '2018-01-22', 1, 2, 2),
('Walter',        'Lima Soria',       '5401267', '1977-07-12', 'Obras y Proyectos',     '71111110', 'w.lima@const.com',       'Av. Blanco Galindo 800',9800.00, '2014-05-30', 1, 2, 2),
('Alvaro',        'Salinas Torrez',   '5512378', '1986-12-08', 'Ingeniería Civil',      '71122221', 'a.salinas@const.com',    'Zona Sur Av. 2',        9100.00, '2019-03-17', 1, 2, 2);

-- Arquitectos (idCargo=3, idDepartamento=3)
INSERT INTO Empleado (nombre, apellido, ci, fechaNacimiento, especialidad, numCelular, email, direccion, salario, fechaContratacion, idEstadoEmpleado, idCargo, idDepartamento) VALUES
('Ana Cecilia',   'Torrico Vega',     '6734590', '1990-03-15', 'Arquitectura',                 '72033333', 'a.torrico@const.com',  'Av. Ballivián 300',   9000.00, '2018-01-10', 1, 3, 3),
('Daniela',       'Rojas Mamani',     '6845601', '1992-07-22', 'Diseño Arquitectónico',        '72044444', 'd.rojas@const.com',    'Calle Sucre 400',     8800.00, '2019-05-15', 1, 3, 3),
('Verónica',      'Paz Condori',      '6956712', '1988-11-08', 'Arquitectura y Urbanismo',     '72055555', 'v.paz@const.com',      'Av. América 500',     9200.00, '2017-08-20', 1, 3, 3),
('Claudia',       'Mendez Flores',    '6067823', '1991-04-30', 'Diseño Interior',              '72066666', 'c.mendez@const.com',   'Calle Lanza 600',     8600.00, '2020-02-10', 1, 3, 3),
('Fernando',      'Quispe Cruz',      '6178934', '1987-09-14', 'Arquitectura',                 '72077777', 'f.quispe@const.com',   'Zona Norte Bloque 3', 9100.00, '2018-06-25', 1, 3, 3),
('Gabriela',      'Vargas Torrico',   '6289045', '1993-01-28', 'Diseño y Construcción',        '72088888', 'g.vargas@const.com',   'Av. Tadeo Haenke 700',8400.00, '2021-03-08', 1, 3, 3),
('Ricardo',       'Choque Lima',      '6390156', '1986-06-15', 'Arquitectura Sostenible',      '72099999', 'r.choque@const.com',   'Calle Punata 800',    9300.00, '2017-09-30', 1, 3, 3),
('Mariana',       'Aguilar Soria',    '6401267', '1994-10-02', 'Diseño Arquitectónico',        '72111110', 'm.aguilar@const.com',  'Zona Sur Av. 3',      8200.00, '2022-01-17', 1, 3, 3),
('Sebastián',     'Torrez Mamani',    '6512378', '1989-02-19', 'Arquitectura',                 '72122221', 's.torrez@const.com',   'Av. Heroínas 900',    9000.00, '2018-11-04', 1, 3, 3),
('Natalia',       'Flores Vega',      '6623489', '1992-07-06', 'Diseño de Interiores',         '72133332', 'n.flores@const.com',   'Calle Baptista 1000', 8700.00, '2020-07-21', 1, 3, 3),
('Alejandro',     'Cruz Condori',     '6734502', '1985-11-23', 'Arquitectura y Diseño',        '72144443', 'al.cruz@const.com',    'Av. Ballivián 1100',  9400.00, '2016-04-08', 1, 3, 3),
('Patricia',      'Mamani Quispe',    '6845613', '1991-03-10', 'Diseño Urbano',                '72155554', 'pa.mamani@const.com',  'Calle Sucre 1200',    8500.00, '2020-10-25', 1, 3, 3),
('Eduardo',       'Rojas Torrico',    '6956724', '1988-08-27', 'Arquitectura',                 '72166665', 'e.rojas@const.com',    'Zona Norte Av. 4',    9100.00, '2018-02-12', 1, 3, 3),
('Valeria',       'Paz Flores',       '6067835', '1993-12-14', 'Diseño Arquitectónico',        '72177776', 'val.paz@const.com',    'Av. América 1300',    8300.00, '2021-08-29', 1, 3, 3),
('Christian',     'Mendez Cruz',      '6178946', '1987-04-01', 'Arquitectura Residencial',     '72188887', 'ch.mendez@const.com',  'Calle Lanza 1400',    9200.00, '2017-05-16', 1, 3, 3);

-- Ingenieros Civiles (idCargo=4, idDepartamento=2)
INSERT INTO Empleado (nombre, apellido, ci, fechaNacimiento, especialidad, numCelular, email, direccion, salario, fechaContratacion, idEstadoEmpleado, idCargo, idDepartamento) VALUES
('Luis',     'Castro Mamani',    '7512378', '1983-05-12', 'Ingeniería Civil',             '73011111', 'l.castro@const.com',   'Av. Oquendo 200',      10500.00, '2015-03-01', 1, 4, 2),
('Mario',    'Gutierrez Paz',    '7623489', '1986-08-20', 'Estructuras',                  '73022222', 'ma.gut@const.com',     'Calle Sucre 300',      10200.00, '2016-06-15', 1, 4, 2),
('Roberto',  'Torrico Flores',   '7734590', '1981-03-15', 'Ingeniería Estructural',       '73033333', 'r.torr@const.com',     'Av. América 400',      10800.00, '2014-01-10', 1, 4, 2),
('Claudio',  'Mendez Vega',      '7845601', '1984-11-30', 'Cálculo Estructural',          '73044444', 'cl.mend@const.com',    'Calle Lanza 500',       9900.00, '2017-09-01', 1, 4, 2),
('Sergio',   'Quispe Aguilar',   '7956712', '1979-07-22', 'Ingeniería Civil',             '73055555', 's.quisp@const.com',    'Zona Sur Bloque 4',    11000.00, '2013-04-20', 1, 4, 2),
('Rodrigo',  'Vargas Condori',   '7067823', '1988-02-14', 'Topografía',                   '73066666', 'ro.varg@const.com',    'Av. Tadeo Haenke 600', 10000.00, '2018-07-01', 1, 4, 2),
('Arturo',   'Choque Mamani',    '7178934', '1982-06-30', 'Ingeniería Civil',             '73077777', 'ar.choq@const.com',    'Zona Norte Bloque 5',  10300.00, '2016-02-28', 1, 4, 2),
('Nelson',   'Lima Torrico',     '7289045', '1985-10-18', 'Geotecnia',                    '73088888', 'ne.lima@const.com',    'Av. Heroínas 700',     10100.00, '2017-08-15', 1, 4, 2),
('Diego',    'Salinas Flores',   '7390156', '1980-03-05', 'Ingeniería Estructural',       '73099999', 'di.sal@const.com',     'Calle Baptista 800',   10600.00, '2015-05-30', 1, 4, 2),
('Alejandro','Rojas Cruz',       '7401267', '1987-07-12', 'Cálculo y Diseño',             '73111110', 'ale.roj@const.com',    'Zona Sur Av. 5',        9800.00, '2019-03-17', 1, 4, 2),
('Cristian', 'Paz Mamani',       '7512389', '1983-12-08', 'Ingeniería Civil',             '73122221', 'cr.paz@const.com',     'Av. Ballivián 900',    10400.00, '2016-10-22', 1, 4, 2),
('Danilo',   'Condori Vega',     '7623490', '1986-04-25', 'Estructuras Metálicas',        '73133332', 'da.cond@const.com',    'Calle Sucre 1000',      9700.00, '2018-01-09', 1, 4, 2),
('Esteban',  'Torrico Cruz',     '7734601', '1981-09-11', 'Ingeniería Civil',             '73144443', 'es.torr@const.com',    'Av. América 1100',     10700.00, '2014-07-26', 1, 4, 2),
('Fabian',   'Mendez Aguilar',   '7845712', '1984-01-28', 'Hidráulica',                   '73155554', 'fa.mend@const.com',    'Calle Lanza 1200',     10200.00, '2017-03-13', 1, 4, 2),
('German',   'Quispe Torrico',   '7956823', '1979-06-14', 'Ingeniería Sísmica',           '73166665', 'ge.quis@const.com',    'Zona Norte Bloque 6',  11200.00, '2013-09-30', 1, 4, 2),
('Hernan',   'Vargas Mamani',    '7067934', '1988-10-01', 'Ingeniería Civil',             '73177776', 'he.varg@const.com',    'Av. Tadeo Haenke 800',  9900.00, '2018-04-17', 1, 4, 2),
('Ivan',     'Choque Flores',    '7178045', '1982-02-18', 'Topografía y Geodesia',        '73188887', 'iv.choq@const.com',    'Zona Sur Bloque 6',    10300.00, '2016-11-04', 1, 4, 2),
('Julian',   'Lima Cruz',        '7289156', '1985-07-05', 'Ingeniería Civil',             '73199998', 'ju.lima@const.com',    'Av. Heroínas 900',     10000.00, '2017-06-21', 1, 4, 2),
('Kevin',    'Salinas Vega',     '7390267', '1980-11-22', 'Estructuras de Hormigón',      '73211109', 'ke.sal@const.com',     'Calle Baptista 1000',  10800.00, '2015-02-08', 1, 4, 2),
('Leonel',   'Rojas Condori',    '7401378', '1987-03-09', 'Ingeniería Civil',             '73222220', 'le.roj@const.com',     'Zona Sur Av. 7',        9600.00, '2019-08-25', 1, 4, 2);

-- Electricistas (idCargo=5, idDepartamento=2)
INSERT INTO Empleado (nombre, apellido, ci, fechaNacimiento, especialidad, numCelular, email, direccion, salario, fechaContratacion, idEstadoEmpleado, idCargo, idDepartamento) VALUES
('Marco',    'Villanueva Cruz',  '8067823', '1988-02-14', 'Electricidad Industrial',  '74066666', 'm.vill@const.com',   'Av. Tadeo Haenke 500', 6500.00, '2020-07-01', 1, 5, 2),
('Pablo',    'Torrez Mamani',    '8178934', '1985-06-30', 'Instalaciones Eléctricas', '74077777', 'pa.torr@const.com',  'Calle Punata 600',     6200.00, '2019-02-28', 1, 5, 2),
('Raul',     'Aguilar Soria',    '8289045', '1990-10-18', 'Electricidad Residencial', '74088888', 'ra.agui@const.com',  'Zona Sur Av. 8',       6800.00, '2021-08-15', 1, 5, 2),
('Simon',    'Lima Flores',      '8390156', '1987-03-05', 'Alta Tensión',             '74099999', 'si.lima@const.com',  'Av. Heroínas 800',     7000.00, '2019-05-30', 1, 5, 2),
('Tomas',    'Salinas Condori',  '8401267', '1983-07-12', 'Electricidad Industrial',  '74111110', 'to.sal@const.com',   'Calle Baptista 900',   6600.00, '2018-03-17', 1, 5, 2),
('Ulises',   'Rojas Vega',       '8512378', '1991-12-08', 'Instalaciones Eléctricas', '74122221', 'ul.roj@const.com',   'Zona Norte Bloque 7',  6300.00, '2022-10-22', 1, 5, 2),
('Victor',   'Paz Cruz',         '8623489', '1986-04-25', 'Electricidad Residencial', '74133332', 'vi.paz@const.com',   'Av. Ballivián 1000',   6700.00, '2020-01-09', 1, 5, 2),
('Wilson',   'Condori Mamani',   '8734590', '1989-09-11', 'Alta Tensión',             '74144443', 'wi.cond@const.com',  'Calle Sucre 1100',     7100.00, '2021-07-26', 1, 5, 2),
('Xavier',   'Torrico Aguilar',  '8845601', '1984-01-28', 'Electricidad Industrial',  '74155554', 'xa.torr@const.com',  'Av. América 1200',     6400.00, '2019-03-13', 1, 5, 2),
('Yandel',   'Mendez Flores',    '8956712', '1992-06-14', 'Instalaciones Eléctricas', '74166665', 'ya.mend@const.com',  'Calle Lanza 1300',     6100.00, '2022-09-30', 1, 5, 2),
('Zenon',    'Quispe Torrico',   '8067834', '1987-10-01', 'Electricidad Industrial',  '74177776', 'ze.quis@const.com',  'Zona Sur Bloque 8',    6900.00, '2020-04-17', 1, 5, 2),
('Abdon',    'Vargas Cruz',      '8178945', '1985-02-18', 'Alta Tensión',             '74188887', 'ab.varg@const.com',  'Av. Tadeo Haenke 900', 7200.00, '2019-11-04', 1, 5, 2),
('Benigno',  'Choque Mamani',    '8289056', '1990-07-05', 'Electricidad Residencial', '74199998', 'be.choq@const.com',  'Zona Norte Bloque 8',  6500.00, '2021-06-21', 1, 5, 2),
('Cirilo',   'Lima Vega',        '8390167', '1983-11-22', 'Instalaciones Eléctricas', '74211109', 'ci.lima@const.com',  'Av. Heroínas 1000',    6800.00, '2018-02-08', 1, 5, 2),
('Dionisio', 'Salinas Soria',    '8401278', '1988-03-09', 'Electricidad Industrial',  '74222220', 'di.sal2@const.com',  'Calle Baptista 1100',  6200.00, '2020-08-25', 1, 5, 2);

-- Albañiles (idCargo=6, idDepartamento=2) - 40 albañiles
INSERT INTO Empleado (nombre, apellido, ci, fechaNacimiento, especialidad, numCelular, email, direccion, salario, fechaContratacion, idEstadoEmpleado, idCargo, idDepartamento) VALUES
('Carlos',    'Mamani Quispe',   '9234567', '1990-03-10', 'Mampostería y acabados',   '75111111', 'ca.mam@const.com',   'Villa Pagador A',     4500.00, '2020-01-15', 1, 6, 2),
('Roberto',   'Flores Choque',   '9345678', '1988-07-22', 'Albañilería general',      '75222222', 'ro.flo@const.com',   'Zona Sur Bloque 3',   4200.00, '2019-06-01', 1, 6, 2),
('Miguel',    'Quispe Tarqui',   '9456789', '1992-11-05', 'Revoque y tarrajeo',       '75333333', 'mi.quis@const.com',  'Calle Punata 200',    4300.00, '2021-03-10', 1, 6, 2),
('Fernando',  'Cruz Aguilar',    '9567890', '1985-04-18', 'Mampostería fina',         '75444444', 'fe.cru@const.com',   'Av. Tadeo Haenke 100',4600.00, '2018-08-20', 1, 6, 2),
('Victor',    'Condori Marca',   '9678901', '1995-09-30', 'Acabados y revestidos',    '75555555', 'vi.con@const.com',   'Calle Lanza 300',     4100.00, '2022-02-01', 1, 6, 2),
('Esteban',   'Torrez Lima',     '9789012', '1987-01-15', 'Albañilería',              '75666666', 'es.tor@const.com',   'Zona Norte Bloque 9', 4400.00, '2019-09-10', 1, 6, 2),
('Fabian',    'Aguilar Soria',   '9890123', '1993-05-28', 'Mampostería',              '75777777', 'fa.agu@const.com',   'Av. Heroínas 200',    4250.00, '2021-07-25', 1, 6, 2),
('German',    'Vega Mamani',     '9901234', '1986-10-11', 'Revoque y enlucido',       '75888888', 'ge.veg@const.com',   'Calle Baptista 400',  4350.00, '2018-11-12', 1, 6, 2),
('Hernan',    'Torrico Paz',     '9012345', '1991-02-24', 'Albañilería general',      '75999999', 'he.tor@const.com',   'Zona Sur Av. 9',      4150.00, '2020-05-07', 1, 6, 2),
('Ivan',      'Flores Condori',  '9123456', '1989-07-07', 'Mampostería y acabados',   '76011111', 'iv.flo@const.com',   'Av. Ballivián 200',   4500.00, '2019-12-22', 1, 6, 2),
('Julian',    'Cruz Mamani',     '9234568', '1994-11-20', 'Albañilería',              '76122222', 'ju.cru@const.com',   'Calle Sucre 300',     4200.00, '2022-04-08', 1, 6, 2),
('Kevin',     'Quispe Flores',   '9345679', '1987-04-03', 'Revoque y tarrajeo',       '76233333', 'ke.quis@const.com',  'Av. América 400',     4350.00, '2019-10-25', 1, 6, 2),
('Leonel',    'Torrez Vega',     '9456780', '1992-08-16', 'Mampostería fina',         '76344444', 'le.tor@const.com',   'Calle Lanza 500',     4400.00, '2021-02-11', 1, 6, 2),
('Manuel',    'Aguilar Cruz',    '9567891', '1985-12-29', 'Acabados y revestidos',    '76455555', 'ma.agu@const.com',   'Zona Norte Bloque 10',4600.00, '2018-06-28', 1, 6, 2),
('Nicolas',   'Soria Mamani',    '9678902', '1990-05-12', 'Albañilería general',      '76566666', 'ni.sor@const.com',   'Av. Heroínas 300',    4250.00, '2020-09-14', 1, 6, 2),
('Oscar',     'Paz Torrico',     '9789013', '1988-09-25', 'Mampostería',              '76677777', 'os.paz@const.com',   'Calle Baptista 500',  4300.00, '2019-03-31', 1, 6, 2),
('Pablo',     'Condori Flores',  '9890124', '1993-01-08', 'Revoque y enlucido',       '76788888', 'pa.con@const.com',   'Zona Sur Bloque 10',  4150.00, '2021-11-17', 1, 6, 2),
('Quirino',   'Mamani Cruz',     '9901235', '1986-06-21', 'Albañilería',              '76899999', 'qi.mam@const.com',   'Av. Ballivián 400',   4450.00, '2018-04-03', 1, 6, 2),
('Ramiro',    'Vega Quispe',     '9012346', '1991-10-04', 'Mampostería y acabados',   '76911110', 'ra.veg@const.com',   'Calle Sucre 500',     4500.00, '2020-12-19', 1, 6, 2),
('Sergio',    'Torrez Aguilar',  '9123457', '1989-02-17', 'Albañilería general',      '77022221', 'se.tor@const.com',   'Av. América 600',     4200.00, '2019-08-05', 1, 6, 2),
('Tomas',     'Flores Lima',     '9234569', '1994-07-01', 'Revoque y tarrajeo',       '77133332', 'to.flo@const.com',   'Calle Lanza 700',     4300.00, '2022-06-22', 1, 6, 2),
('Ulises',    'Cruz Torrico',    '9345670', '1987-11-14', 'Mampostería fina',         '77244443', 'ul.cru@const.com',   'Zona Norte Bloque 11',4350.00, '2019-12-09', 1, 6, 2),
('Valentin',  'Quispe Soria',    '9456781', '1992-03-27', 'Acabados y revestidos',    '77355554', 'va.quis@const.com',  'Av. Heroínas 400',    4100.00, '2021-09-25', 1, 6, 2),
('Wilber',    'Aguilar Mamani',  '9567892', '1985-08-10', 'Albañilería',              '77466665', 'wi.agu@const.com',   'Calle Baptista 600',  4600.00, '2018-01-12', 1, 6, 2),
('Xavier',    'Soria Paz',       '9678903', '1990-12-23', 'Mampostería',              '77577776', 'xa.sor@const.com',   'Zona Sur Av. 11',     4250.00, '2020-07-29', 1, 6, 2),
('Yandel',    'Torrico Vega',    '9789014', '1988-04-06', 'Revoque y enlucido',       '77688887', 'ya.tor@const.com',   'Av. Ballivián 600',   4400.00, '2019-02-14', 1, 6, 2),
('Zenon',     'Condori Cruz',    '9890125', '1993-08-19', 'Albañilería general',      '77799998', 'ze.con@const.com',   'Calle Sucre 700',     4150.00, '2021-10-01', 1, 6, 2),
('Abdon',     'Mamani Flores',   '9901236', '1986-01-02', 'Mampostería y acabados',   '77811109', 'ab.mam@const.com',   'Av. América 800',     4500.00, '2018-08-18', 1, 6, 2),
('Benigno',   'Vega Torrez',     '9012347', '1991-05-15', 'Albañilería',              '77922220', 'be.veg@const.com',   'Calle Lanza 900',     4300.00, '2020-03-04', 1, 6, 2),
('Cirilo',    'Quispe Aguilar',  '9123458', '1989-09-28', 'Revoque y tarrajeo',       '78033331', 'ci.quis@const.com',  'Zona Norte Av. 5',    4200.00, '2019-11-20', 1, 6, 2),
('Dionisio',  'Torrez Mamani',   '9234570', '1994-02-11', 'Mampostería fina',         '78144442', 'dio.tor@const.com',  'Av. Heroínas 500',    4350.00, '2022-08-07', 1, 6, 2),
('Elias',     'Flores Paz',      '9345671', '1987-06-24', 'Acabados y revestidos',    '78255553', 'el.flo@const.com',   'Calle Baptista 700',  4450.00, '2019-04-23', 1, 6, 2),
('Filiberto', 'Cruz Soria',      '9456782', '1992-10-07', 'Albañilería general',      '78366664', 'fi.cru@const.com',   'Zona Sur Bloque 11',  4100.00, '2021-12-10', 1, 6, 2),
('Gregorio',  'Aguilar Vega',    '9567893', '1985-02-20', 'Mampostería',              '78477775', 'gr.agu@const.com',   'Av. Ballivián 800',   4600.00, '2018-05-27', 1, 6, 2),
('Hilarion',  'Soria Condori',   '9678904', '1990-07-03', 'Revoque y enlucido',       '78588886', 'hi.sor@const.com',   'Calle Sucre 900',     4250.00, '2020-10-13', 1, 6, 2),
('Isidoro',   'Torrico Torrez',  '9789015', '1988-11-16', 'Albañilería',              '78699997', 'is.tor@const.com',   'Av. América 1000',    4350.00, '2019-07-30', 1, 6, 2),
('Jacinto',   'Mamani Quispe',   '9890126', '1993-03-29', 'Mampostería y acabados',   '78811108', 'ja.mam@const.com',   'Calle Lanza 1100',    4500.00, '2021-05-15', 1, 6, 2),
('Klever',    'Vega Flores',     '9901237', '1986-08-12', 'Albañilería general',      '78922219', 'kl.veg@const.com',   'Zona Norte Bloque 12',4200.00, '2018-02-01', 1, 6, 2),
('Laureano',  'Cruz Mamani',     '9012348', '1991-12-25', 'Revoque y tarrajeo',       '79033330', 'la.cru@const.com',   'Av. Heroínas 600',    4300.00, '2020-06-18', 1, 6, 2),
('Macedonio', 'Quispe Torrez',   '9123459', '1989-04-08', 'Mampostería fina',         '79144441', 'mac.quis@const.com', 'Calle Baptista 800',  4150.00, '2019-10-05', 1, 6, 2);

-- Contadores (idCargo=7, idDepartamento=4)
INSERT INTO Empleado (nombre, apellido, ci, fechaNacimiento, especialidad, numCelular, email, direccion, salario, fechaContratacion, idEstadoEmpleado, idCargo, idDepartamento) VALUES
('Carmen Rosa',  'Gutierrez Paz',   '1956712', '1992-07-22', 'Contabilidad',           '74055555', 'c.gut@const.com',   'Calle Hamiraya 400',  8000.00, '2019-04-20', 1, 7, 4),
('Elena',        'Rojas Mamani',    '1067823', '1988-11-08', 'Contabilidad Financiera','74066667', 'e.roj@const.com',   'Av. América 700',     7800.00, '2018-09-15', 1, 7, 4),
('Fernanda',     'Paz Condori',     '1178934', '1994-03-25', 'Auditoría',              '74077778', 'fe.paz@const.com',  'Calle Lanza 800',     7600.00, '2021-01-30', 1, 7, 4),
('Gloria',       'Mendez Flores',   '1289045', '1990-08-12', 'Contabilidad',           '74088889', 'gl.men@const.com',  'Zona Norte Bloque 13',7900.00, '2020-06-17', 1, 7, 4),
('Hilda',        'Quispe Cruz',     '1390156', '1986-12-29', 'Finanzas',               '74099990', 'hi.qui@const.com',  'Av. Heroínas 1100',   8200.00, '2017-11-04', 1, 7, 4);

-- Asistentes Administrativos (idCargo=8, idDepartamento=1)
INSERT INTO Empleado (nombre, apellido, ci, fechaNacimiento, especialidad, numCelular, email, direccion, salario, fechaContratacion, idEstadoEmpleado, idCargo, idDepartamento) VALUES
('Rosa',      'Perez Alvarado',   '2401234', '1995-09-05', 'Administración',      '76077777', 'r.per@const.com',   'Calle Punata 600',    5500.00, '2021-02-15', 1, 8, 1),
('Sandra',    'Torrez Lima',      '2512345', '1993-01-18', 'Secretariado',        '76088888', 's.tor@const.com',   'Av. Ballivián 700',   5300.00, '2020-08-02', 1, 8, 1),
('Teresa',    'Aguilar Soria',    '2623456', '1997-05-31', 'Administración',      '76099999', 'te.agu@const.com',  'Calle Sucre 800',     5200.00, '2022-03-19', 1, 8, 1),
('Ursula',    'Lima Mamani',      '2734567', '1994-10-14', 'Gestión Documental',  '76111110', 'ur.lim@const.com',  'Av. América 900',     5400.00, '2021-09-05', 1, 8, 1),
('Vanessa',   'Salinas Flores',   '2845678', '1996-02-27', 'Administración',      '76122221', 'va.sal@const.com',  'Calle Lanza 1000',    5100.00, '2022-11-22', 1, 8, 1);

-- Plomeros (idCargo=9, idDepartamento=2) - 20 plomeros
INSERT INTO Empleado (nombre, apellido, ci, fechaNacimiento, especialidad, numCelular, email, direccion, salario, fechaContratacion, idEstadoEmpleado, idCargo, idDepartamento) VALUES
('Juan',      'Perez Mamani',    '3677881', '1991-02-14', 'Instalaciones sanitarias',  '77666666', 'j.per@const.com',   'Calle Oquendo 400',    4800.00, '2020-05-10', 1, 9, 2),
('Luis',      'Garcia Flores',   '3788992', '1989-08-25', 'Tuberías y desagüe',        '77777777', 'l.gar@const.com',   'Av. America 500',      4500.00, '2019-03-15', 1, 9, 2),
('Mario',     'Suarez Quispe',   '3899003', '1993-11-30', 'Plomería general',          '77888888', 'ma.sua@const.com',  'Zona Sur Calle 3',     4600.00, '2021-07-01', 1, 9, 2),
('Norberto',  'Choque Torrez',   '3900114', '1986-04-07', 'Instalaciones sanitarias',  '77999999', 'no.cho@const.com',  'Av. Heroínas 700',     4700.00, '2018-10-18', 1, 9, 2),
('Oswaldo',   'Lima Aguilar',    '4011225', '1994-08-20', 'Tuberías y desagüe',        '78111110', 'os.lim@const.com',  'Calle Baptista 800',   4400.00, '2022-01-05', 1, 9, 2),
('Porfirio',  'Vega Mamani',     '4122336', '1988-01-03', 'Plomería general',          '78222221', 'po.veg@const.com',  'Zona Norte Bloque 14', 4850.00, '2019-08-22', 1, 9, 2),
('Quintin',   'Flores Cruz',     '4233447', '1991-05-16', 'Instalaciones sanitarias',  '78333332', 'qi.flo@const.com',  'Av. Ballivián 1200',   4550.00, '2020-12-09', 1, 9, 2),
('Rufino',    'Torrico Soria',   '4344558', '1985-09-29', 'Tuberías PVC',             '78444443', 'ru.tor@const.com',  'Calle Sucre 1300',     4750.00, '2018-04-26', 1, 9, 2),
('Salvador',  'Quispe Paz',      '4455669', '1993-02-12', 'Plomería general',          '78555554', 'sa.quis@const.com', 'Av. América 1400',     4650.00, '2021-10-13', 1, 9, 2),
('Trifon',    'Condori Vega',    '4566770', '1987-06-25', 'Instalaciones sanitarias',  '78666665', 'tr.con@const.com',  'Calle Lanza 1500',     4800.00, '2019-05-30', 1, 9, 2),
('Ubaldo',    'Mamani Flores',   '4677881', '1995-10-08', 'Tuberías y desagüe',        '78777776', 'ub.mam@const.com',  'Zona Sur Bloque 12',   4350.00, '2022-03-16', 1, 9, 2),
('Vidal',     'Cruz Torrez',     '4788992', '1989-02-21', 'Plomería general',          '78888887', 'vi.cru@const.com',  'Av. Heroínas 800',     4700.00, '2020-09-02', 1, 9, 2),
('Wilfredo',  'Aguilar Mamani',  '4899003', '1992-07-04', 'Instalaciones sanitarias',  '78999998', 'wi.agu2@const.com', 'Calle Baptista 900',   4450.00, '2021-04-19', 1, 9, 2),
('Xiomara',   'Soria Quispe',    '4900114', '1986-11-17', 'Tuberías y desagüe',        '79111109', 'xi.sor@const.com',  'Zona Norte Bloque 15', 4600.00, '2018-12-06', 1, 9, 2),
('Yolanda',   'Torrico Lima',    '5011225', '1994-03-30', 'Plomería general',          '79222220', 'yo.tor@const.com',  'Av. Ballivián 1400',   4500.00, '2022-07-23', 1, 9, 2),
('Zunilda',   'Paz Flores',      '5122336', '1988-08-13', 'Instalaciones sanitarias',  '79333331', 'zu.paz@const.com',  'Calle Sucre 1500',     4750.00, '2020-02-09', 1, 9, 2),
('Adolfo',    'Vega Condori',    '5233447', '1991-12-26', 'Tuberías PVC',             '79444442', 'ad.veg@const.com',  'Av. América 1600',     4650.00, '2021-08-26', 1, 9, 2),
('Bernabe',   'Flores Torrez',   '5344558', '1985-04-09', 'Plomería general',          '79555553', 'be.flo@const.com',  'Calle Lanza 1700',     4800.00, '2018-07-13', 1, 9, 2),
('Cornelio',  'Quispe Aguilar',  '5455669', '1993-08-22', 'Instalaciones sanitarias',  '79666664', 'co.quis@const.com', 'Zona Sur Bloque 13',   4550.00, '2021-12-30', 1, 9, 2),
('Demetrio',  'Condori Mamani',  '5566770', '1987-01-05', 'Tuberías y desagüe',        '79777775', 'de.con@const.com',  'Av. Heroínas 900',     4700.00, '2019-06-17', 1, 9, 2);

-- Soldadores (idCargo=10, idDepartamento=2) - 10 soldadores
INSERT INTO Empleado (nombre, apellido, ci, fechaNacimiento, especialidad, numCelular, email, direccion, salario, fechaContratacion, idEstadoEmpleado, idCargo, idDepartamento) VALUES
('Eloy',      'Mamani Soria',    '6677881', '1988-03-15', 'Soldadura MIG/TIG',    '80111111', 'el.mam@const.com',  'Calle Punata 1000',    5500.00, '2019-04-01', 1, 10, 2),
('Filemon',   'Cruz Vega',       '6788992', '1985-07-28', 'Soldadura industrial', '80222222', 'fi.cru@const.com',  'Av. Ballivián 1600',   5300.00, '2018-10-18', 1, 10, 2),
('Genaro',    'Quispe Lima',     '6899003', '1992-12-11', 'Soldadura al arco',    '80333333', 'ge.qui@const.com',  'Calle Sucre 1700',     5600.00, '2021-05-05', 1, 10, 2),
('Hipolito',  'Torrez Mamani',   '6900114', '1986-04-24', 'Soldadura MIG/TIG',    '80444444', 'hi.tor@const.com',  'Av. América 1800',     5400.00, '2018-11-22', 1, 10, 2),
('Ignacio',   'Aguilar Flores',  '7011225', '1994-09-06', 'Soldadura industrial', '80555555', 'ig.agu@const.com',  'Calle Lanza 1800',     5200.00, '2022-02-08', 1, 10, 2),
('Jacinto2',  'Soria Condori',   '7122336', '1989-01-19', 'Soldadura al arco',    '80666666', 'jac.sor@const.com', 'Zona Norte Bloque 16', 5700.00, '2020-08-25', 1, 10, 2),
('Kristian',  'Paz Torrico',     '7233447', '1991-05-02', 'Soldadura MIG/TIG',    '80777777', 'kr.paz@const.com',  'Av. Heroínas 1000',    5500.00, '2021-03-12', 1, 10, 2),
('Lorenzo',   'Vega Quispe',     '7344558', '1984-09-15', 'Soldadura industrial', '80888888', 'lo.veg@const.com',  'Calle Baptista 1200',  5800.00, '2017-10-29', 1, 10, 2),
('Macedon2',  'Flores Torrez',   '7455669', '1993-01-28', 'Soldadura al arco',    '80999999', 'mac.flo@const.com', 'Zona Sur Bloque 14',   5300.00, '2022-07-15', 1, 10, 2),
('Narciso',   'Condori Cruz',    '7566770', '1987-06-11', 'Soldadura MIG/TIG',    '81111110', 'na.con@const.com',  'Av. Ballivián 1800',   5600.00, '2019-01-02', 1, 10, 2);

-- Carpinteros (idCargo=11, idDepartamento=2) - 10 carpinteros
INSERT INTO Empleado (nombre, apellido, ci, fechaNacimiento, especialidad, numCelular, email, direccion, salario, fechaContratacion, idEstadoEmpleado, idCargo, idDepartamento) VALUES
('Obdulio',   'Mamani Vega',     '8677881', '1986-04-24', 'Carpintería de obra',     '82111111', 'ob.mam@const.com',  'Calle Sucre 1900',     5000.00, '2018-05-10', 1, 11, 2),
('Primitivo', 'Cruz Soria',      '8788992', '1990-08-06', 'Carpintería fina',        '82222222', 'pr.cru@const.com',  'Av. América 2000',     4800.00, '2020-12-27', 1, 11, 2),
('Quiliano',  'Quispe Flores',   '8899003', '1993-12-19', 'Carpintería de obra',     '82333333', 'qi.qui@const.com',  'Calle Lanza 2000',     4900.00, '2022-08-13', 1, 11, 2),
('Rosendo',   'Torrez Paz',      '8900114', '1984-04-01', 'Encofrado y apuntalado',  '82444444', 'ro.tor@const.com',  'Zona Norte Av. 6',     5200.00, '2017-02-28', 1, 11, 2),
('Sebastian2','Aguilar Mamani',  '9011225', '1991-08-14', 'Carpintería de obra',     '82555555', 'seb.agu@const.com', 'Av. Heroínas 1100',    5100.00, '2021-06-15', 1, 11, 2),
('Timoteo',   'Soria Vega',      '9122336', '1988-12-27', 'Carpintería fina',        '82666666', 'ti.sor@const.com',  'Calle Baptista 1300',  4850.00, '2020-01-01', 1, 11, 2),
('Urbano',    'Paz Cruz',        '9233447', '1995-05-10', 'Carpintería de obra',     '82777777', 'ur.paz@const.com',  'Zona Sur Bloque 15',   4700.00, '2022-10-18', 1, 11, 2),
('Valentin2', 'Vega Quispe',     '9344558', '1983-09-23', 'Encofrado y apuntalado',  '82888888', 'val.veg@const.com', 'Av. Ballivián 2000',   5300.00, '2016-07-05', 1, 11, 2),
('Wenceslao', 'Flores Mamani',   '9455669', '1990-02-05', 'Carpintería fina',        '82999999', 'we.flo@const.com',  'Calle Sucre 2100',     5000.00, '2020-04-22', 1, 11, 2),
('Ygnacio',   'Condori Torrez',  '9566770', '1987-06-18', 'Carpintería de obra',     '83111110', 'yg.con@const.com',  'Av. América 2200',     4900.00, '2019-11-08', 1, 11, 2);

-- Pintores (idCargo=12, idDepartamento=2) - 10 pintores
INSERT INTO Empleado (nombre, apellido, ci, fechaNacimiento, especialidad, numCelular, email, direccion, salario, fechaContratacion, idEstadoEmpleado, idCargo, idDepartamento) VALUES
('Zenobio',   'Mamani Cruz',     '1677881', '1989-07-31', 'Pintura de interiores',    '84111111', 'ze.mam@const.com',  'Calle Lanza 2100',     4200.00, '2019-08-17', 1, 12, 2),
('Abundio',   'Vega Soria',      '1788992', '1993-12-14', 'Pintura exterior',         '84222222', 'ab.veg@const.com',  'Zona Norte Bloque 17', 4100.00, '2022-04-03', 1, 12, 2),
('Baldomero', 'Flores Paz',      '1899003', '1986-04-27', 'Pintura industrial',       '84333333', 'ba.flo@const.com',  'Av. Heroínas 1200',    4500.00, '2018-11-19', 1, 12, 2),
('Casimiro',  'Torrez Aguilar',  '1900114', '1991-09-10', 'Pintura de interiores',    '84444444', 'ca.tor@const.com',  'Calle Baptista 1400',  4300.00, '2021-06-06', 1, 12, 2),
('Delfino',   'Quispe Mamani',   '2011225', '1988-01-23', 'Pintura exterior',         '84555555', 'de.qui@const.com',  'Zona Sur Bloque 16',   4400.00, '2019-12-23', 1, 12, 2),
('Eulogio',   'Condori Vega',    '2122336', '1994-06-06', 'Pintura industrial',       '84666666', 'eu.con@const.com',  'Av. Ballivián 2200',   4150.00, '2022-07-10', 1, 12, 2),
('Filomeno',  'Soria Flores',    '2233447', '1985-10-19', 'Pintura de interiores',    '84777777', 'fi.sor@const.com',  'Calle Sucre 2300',     4600.00, '2017-04-27', 1, 12, 2),
('Gumercindo','Paz Torrez',      '2344558', '1990-03-02', 'Pintura exterior',         '84888888', 'gu.paz@const.com',  'Av. América 2400',     4250.00, '2020-11-13', 1, 12, 2),
('Hermenegildo','Cruz Quispe',   '2455669', '1987-07-15', 'Pintura industrial',       '84999999', 'he.cru@const.com',  'Calle Lanza 2400',     4350.00, '2019-05-30', 1, 12, 2),
('Inocencio', 'Mamani Aguilar',  '2566770', '1993-11-28', 'Pintura de interiores',    '85111110', 'in.mam@const.com',  'Zona Norte Bloque 18', 4200.00, '2022-02-14', 1, 12, 2);

-- ============================================================
-- GRUPO 6: PROYECTOS (10 proyectos)
-- ============================================================

INSERT INTO Proyecto (nombreProyecto, descripcion, idTipoProyecto, ubicacion, fechaInicio, fechaFinEstimada, fechaFinReal, idEstadoProyecto, idCliente) VALUES
('Residencia Mendoza',              'Casa de dos plantas con jardín',         1, 'Urb. Las Brisas',         '2024-01-10', '2024-08-10', NULL,         2, 1),
('Edificio Los Andes',              'Edificio de 6 pisos 24 departamentos',   2, 'Av. América 789',         '2023-06-01', '2025-06-01', NULL,         2, 4),
('Local Fernández',                 'Local comercial 120 m²',                 5, 'Calle Sucre 456',         '2024-03-15', '2024-07-15', '2024-07-20', 3, 2),
('Pavimentación Zona Norte',        'Pavimentación 2km carretera vecinal',    3, 'Zona Norte Cochabamba',   '2023-09-01', '2024-03-01', '2024-03-15', 3, 3),
('Ampliación Salinas',              'Ampliación y refacción vivienda',        1, 'Calle Baptista 321',      '2024-05-01', '2024-10-01', NULL,         2, 5),
('Construccion Casa Familiar Norte','Casa familiar zona norte',               1, 'Zona Norte Cochabamba',   '2025-11-01', '2026-06-01', NULL,         2, 20),
('Edificio Residencial Sur',        'Edificio 4 pisos zona sur',              2, 'Zona Sur Cochabamba',     '2026-02-01', '2027-02-01', NULL,         1, 3),
('Centro Comercial Oeste',          'Centro comercial 2000 m²',               5, 'Av. Blanco Galindo Km 6', '2025-03-01', '2026-03-01', NULL,         2, 6),
('Puente Río Rocha',                'Puente peatonal sobre río Rocha',        4, 'Río Rocha Sector Norte',  '2024-08-01', '2025-02-01', '2025-02-20', 3, 8),
('Vivienda Social Zona Sur',        'Conjunto habitacional 20 unidades',      1, 'Zona Sur Cochabamba',     '2025-06-01', '2026-12-01', NULL,         2, 12);

-- ============================================================
-- GRUPO 7: PROVEEDOR MATERIAL
-- ============================================================

INSERT INTO ProveedorMaterial (idProveedor, idMaterial, precioProveedor, tiempoEntrega) VALUES
(1,  1, 55.00, 2), (1, 10, 85.00, 2), (1, 11,  2.20, 1),
(2,  2,  8.00, 3), (2,  3,  5.00, 3), (2, 12,  6.50, 3),
(3,  4, 32.00, 5), (3, 13, 16.00, 5),
(4,  5, 82.00, 7), (4, 14, 23.00, 4),
(5,  6, 75.00, 1), (5,  7, 90.00, 1),
(6,  8, 42.00, 3), (6, 15, 52.00, 3),
(7,  9, 62.00, 4),
(8,  1, 57.00, 1), (8,  2,  8.30, 2),
(9,  6, 78.00, 2), (9, 11,  2.40, 1),
(10, 4, 34.00, 4), (10, 7, 93.00, 2);

-- ============================================================
-- GRUPO 8: CONTRATOS Y COTIZACIONES
-- ============================================================

INSERT INTO Contrato (numeroContrato, idTipoContrato, fechaContrato, fechaFirma, fechaInicio, fechaVencimiento, montoTotal, idEstadoContrato, idProyecto) VALUES
('CONT-2024-001', 1, '2023-12-20', '2024-01-05', '2024-01-10', '2024-08-10',  185000.00, 1, 1),
('CONT-2023-002', 2, '2023-05-15', '2023-05-25', '2023-06-01', '2025-06-01',  920000.00, 1, 2),
('CONT-2024-003', 1, '2024-03-01', '2024-03-10', '2024-03-15', '2024-07-15',   95000.00, 2, 3),
('CONT-2023-004', 1, '2023-08-20', '2023-08-28', '2023-09-01', '2024-03-01',  320000.00, 2, 4),
('CONT-2024-005', 3, '2024-04-20', '2024-04-28', '2024-05-01', '2024-10-01',   75000.00, 1, 5),
('CONT-2025-006', 1, '2025-10-15', '2025-10-25', '2025-11-01', '2026-06-01',  150000.00, 1, 6),
('CONT-2025-007', 2, '2025-01-10', '2025-01-20', '2025-03-01', '2026-03-01',  850000.00, 1, 8),
('CONT-2024-008', 1, '2024-07-15', '2024-07-25', '2024-08-01', '2025-02-01',  280000.00, 2, 9),
('CONT-2025-009', 2, '2025-05-01', '2025-05-10', '2025-06-01', '2026-12-01',  450000.00, 1, 10);

INSERT INTO CotizacionCliente (numeroCotizacionCliente, fechaCotizacion, fechaValidez, observaciones, idProyecto, idEstadoCotizacion) VALUES
('COT-CLI-2023-001', '2023-12-01', '2023-12-31', 'Incluye materiales y mano de obra',         1, 2),
('COT-CLI-2023-002', '2023-05-01', '2023-05-20', 'Precio por etapas',                         2, 2),
('COT-CLI-2024-003', '2024-02-20', '2024-03-05', 'Precio fijo todo incluido',                 3, 2),
('COT-CLI-2023-004', '2023-08-10', '2023-08-25', 'Incluye señalización y compactación',       4, 2),
('COT-CLI-2024-005', '2024-04-10', '2024-04-25', 'Solo mano de obra',                         5, 2),
('COT-CLI-2025-006', '2025-10-01', '2025-10-31', 'Cotización pendiente de respuesta',         5, 1),
('COT-CLI-2025-007', '2025-11-15', '2025-12-15', 'Cliente evaluando propuesta',               1, 1),
('COT-CLI-2025-008', '2025-02-01', '2025-02-28', 'Cotización centro comercial',               8, 2),
('COT-CLI-2024-009', '2024-07-01', '2024-07-20', 'Cotización puente peatonal',                9, 2);

INSERT INTO CotizacionInterna (numeroCotizacionInterna, fechaCotizacion, observaciones, idProyecto, idEstadoCotizacion) VALUES
('COT-INT-2023-001', '2023-11-25', 'Costo real estimado proyecto Mendoza',      1, 2),
('COT-INT-2023-002', '2023-04-28', 'Costo real estimado edificio Los Andes',    2, 2),
('COT-INT-2024-003', '2024-02-18', 'Costo real estimado local Fernández',       3, 2),
('COT-INT-2023-004', '2023-08-08', 'Costo real estimado pavimentación',         4, 2),
('COT-INT-2024-005', '2024-04-08', 'Costo real estimado ampliación Salinas',    5, 2),
('COT-INT-2026-006', '2026-01-15', 'Costo interno edificio sur',                7, 1),
('COT-INT-2025-007', '2025-02-01', 'Costo interno centro comercial',            8, 2),
('COT-INT-2024-008', '2024-07-01', 'Costo interno puente Rocha',                9, 2);

-- ============================================================
-- GRUPO 9: ORDENES DE COMPRA Y DETALLE
-- ============================================================

INSERT INTO OrdenCompra (fechaOrden, idEstadoOrden, idProveedor, montoTotal) VALUES
('2024-01-15', 2, 1,  8700.00),
('2024-01-20', 2, 2, 15300.00),
('2024-03-10', 1, 5,  4750.00),
('2024-06-01', 2, 1,  5800.00),
('2024-05-10', 1, 3,  2100.00),
('2025-11-05', 2, 1, 12000.00),
('2025-11-10', 2, 2, 18500.00),
('2025-03-01', 2, 6,  8000.00),
('2024-08-05', 2, 5,  9500.00),
('2025-06-01', 1, 4,  6500.00);

INSERT INTO DetalleCompra (idOrdenCompra, idMaterial, cantidad, precioUnitario) VALUES
(1,  1, 150.00, 55.00), (1,  6,  10.00, 75.00),
(2,  2, 800.00,  8.00), (2,  3, 500.00,  5.00),
(3,  7,  50.00, 95.00),
(4,  1, 100.00, 58.00),
(5,  4,  60.00, 35.00),
(6,  1, 200.00, 55.00), (6, 11, 1000.00, 2.20),
(7,  2,1200.00,  8.00), (7, 12, 800.00,  6.50),
(8,  8, 150.00, 42.00), (8, 15, 100.00, 52.00),
(9,  6, 100.00, 75.00), (9,  7,  50.00, 90.00),
(10, 5,  40.00, 82.00), (10,14, 100.00, 23.00);

-- ============================================================
-- GRUPO 10: ASIGNACION EMPLEADOS A PROYECTOS
-- ============================================================

INSERT INTO EmpleadoProyecto (idEmpleado, idProyecto, idRolProyecto, fechaInicio, fechaFin) VALUES
(1,  1, 1, '2024-01-10', NULL),   (6,  1, 2, '2024-01-10', NULL),
(16, 1, 3, '2024-01-10', NULL),   (31, 1, 4, '2024-01-10', NULL),
(32, 1, 4, '2024-01-10', NULL),   (1,  2, 1, '2023-06-01', NULL),
(7,  2, 2, '2023-06-01', NULL),   (17, 2, 3, '2023-06-01', NULL),
(26, 2, 4, '2023-06-01', NULL),   (27, 2, 4, '2023-06-01', NULL),
(28, 2, 4, '2023-06-01', NULL),   (2,  3, 1, '2024-03-15', '2024-07-20'),
(8,  3, 2, '2024-03-15', '2024-07-20'), (18, 3, 3, '2024-03-15', '2024-07-20'),
(33, 3, 4, '2024-03-15', '2024-07-20'), (3,  4, 1, '2023-09-01', '2024-03-15'),
(9,  4, 2, '2023-09-01', '2024-03-15'), (19, 4, 3, '2023-09-01', '2024-03-15'),
(1,  6, 1, '2025-11-01', NULL),   (6,  6, 2, '2025-11-01', NULL),
(20, 6, 3, '2025-11-01', NULL),   (34, 6, 4, '2025-11-01', NULL),
(35, 6, 4, '2025-11-01', NULL),   (36, 6, 4, '2025-11-01', NULL);

-- ============================================================
-- GRUPO 11: MATERIALES POR PROYECTO
-- ============================================================

INSERT INTO MaterialProyecto (idProyecto, idMaterial, cantidadUtilizada, fechaRegistro, costoTotal) VALUES
(1, 1,  150.00, '2024-01-20',  8700.00),
(1, 2, 1200.00, '2024-01-20', 10200.00),
(1, 6,   80.00, '2024-02-01',  6400.00),
(2, 1,  800.00, '2023-07-01', 46400.00),
(2, 2, 5000.00, '2023-07-01', 42500.00),
(2, 9, 1200.00, '2023-08-01', 78000.00),
(3, 1,   80.00, '2024-03-20',  4640.00),
(3, 8,  200.00, '2024-06-01',  9000.00),
(4, 6,  500.00, '2023-09-10', 40000.00),
(4, 7,  400.00, '2023-09-10', 38000.00),
(6, 1,  200.00, '2025-11-10', 11600.00),
(6, 2, 1500.00, '2025-11-10', 12750.00),
(6, 11,2000.00, '2025-11-15',  5000.00),
(8, 9,  800.00, '2025-03-10', 52000.00),
(8, 8,  300.00, '2025-04-01', 13500.00);

-- ============================================================
-- GRUPO 12: DETALLE COTIZACIONES
-- ============================================================

INSERT INTO DetalleCotizacionCliente (idCotizacionCliente, concepto, descripcion, cantidad, precioUnitario) VALUES
(1, 'Cimentación',   'Excavación y losa de cimentación',      1.00, 25000.00),
(1, 'Estructura',    'Columnas, vigas y losa de entrepiso',    1.00, 55000.00),
(1, 'Mampostería',   'Muros de ladrillo visto',                1.00, 40000.00),
(1, 'Instalaciones', 'Eléctricas y sanitarias',                1.00, 30000.00),
(1, 'Acabados',      'Pisos, pintura y puertas',               1.00, 35000.00),
(2, 'Etapa 1',       'Excavación y sótano',                    1.00,150000.00),
(2, 'Etapa 2',       'Estructura hormigón armado 6 pisos',     1.00,400000.00),
(2, 'Etapa 3',       'Acabados, instalaciones y exteriores',   1.00,370000.00),
(3, 'Obra gruesa',   'Cimentación, estructura y muros',        1.00, 55000.00),
(3, 'Acabados',      'Pisos, pintura y carpintería',           1.00, 40000.00),
(8, 'Cimentación',   'Excavación y fundaciones',               1.00,120000.00),
(8, 'Estructura',    'Estructura metálica y losas',            1.00,350000.00),
(8, 'Acabados',      'Fachada, interiores y exteriores',       1.00,380000.00);

INSERT INTO DetalleCotizacionInterna (idCotizacionInterna, idMaterial, cantidadEstimada, costoUnitarioEstimado) VALUES
(1,  1,  150.00, 55.00), (1,  2, 1200.00,  8.00),
(1,  6,   80.00, 75.00), (1,  7,   60.00, 90.00),
(2,  1,  800.00, 55.00), (2,  2, 5000.00,  8.00),
(2,  9, 1200.00, 62.00),
(3,  1,   80.00, 55.00), (3,  8,  200.00, 42.00),
(4,  6,  500.00, 75.00), (4,  7,  400.00, 90.00),
(7,  9,  800.00, 62.00), (7,  8,  300.00, 42.00),
(8,  2, 2000.00,  8.00), (8, 12, 1000.00,  6.50);

INSERT INTO DetalleCotizacionManoObra (idCotizacionInterna, idCargo, cantidadPersonas, horasEstimadas, pagoPorHora, totalEstimado) VALUES
(1, 2, 2, 320.00, 20.00,  12800.00), (1, 4, 1, 200.00, 35.00,  7000.00),
(1, 5, 1, 100.00, 25.00,   2500.00), (1, 6, 3, 480.00, 15.00, 21600.00),
(2, 2, 4, 960.00, 20.00,  76800.00), (2, 4, 2, 640.00, 35.00, 44800.00),
(2, 3, 2, 480.00, 40.00,  38400.00), (2, 6, 8,1920.00, 15.00,230400.00),
(3, 2, 1, 160.00, 20.00,   3200.00), (3, 6, 2, 320.00, 15.00,  9600.00),
(4, 2, 2, 480.00, 20.00,  19200.00), (4, 6, 4, 960.00, 15.00, 57600.00),
(5, 2, 1, 120.00, 20.00,   2400.00), (5, 6, 2, 240.00, 15.00,  7200.00),
(6, 2, 2, 200.00, 20.00,   8000.00), (6, 6, 3, 300.00, 15.00, 13500.00),
(6, 9, 1, 150.00, 17.00,   2550.00);

-- ============================================================
-- GRUPO 13: CUOTAS
-- ============================================================

INSERT INTO Cuota (idContrato, numeroCuota, fechaVencimiento, montoCuota, saldoPendiente, idEstadoPago) VALUES
(1, 1, '2024-02-10',  37000.00,     0.00, 3),
(1, 2, '2024-04-10',  37000.00,     0.00, 3),
(1, 3, '2024-06-10',  37000.00, 37000.00, 1),
(1, 4, '2024-08-10',  74000.00, 74000.00, 1),
(2, 1, '2023-09-01', 184000.00,     0.00, 3),
(2, 2, '2024-01-01', 184000.00,     0.00, 3),
(2, 3, '2024-07-01', 184000.00,184000.00, 1),
(2, 4, '2025-01-01', 184000.00,184000.00, 1),
(2, 5, '2025-06-01', 184000.00,184000.00, 1),
(3, 1, '2024-05-15',  47500.00,     0.00, 3),
(3, 2, '2024-07-20',  47500.00,     0.00, 3),
(4, 1, '2023-12-01',  96000.00,     0.00, 3),
(4, 2, '2024-03-01', 224000.00,     0.00, 3),
(5, 1, '2024-07-01',  37500.00,     0.00, 3),
(5, 2, '2024-10-01',  37500.00, 37500.00, 1),
(6, 1, '2026-01-01',  50000.00,     0.00, 3),
(6, 2, '2026-03-01',  50000.00, 50000.00, 1),
(6, 3, '2026-06-01',  50000.00, 50000.00, 1),
(7, 1, '2025-06-01', 212500.00,     0.00, 3),
(7, 2, '2025-12-01', 212500.00,212500.00, 1),
(7, 3, '2026-06-01', 212500.00,212500.00, 1),
(7, 4, '2026-12-01', 212500.00,212500.00, 1),
(8, 1, '2024-10-01', 140000.00,     0.00, 3),
(8, 2, '2025-02-01', 140000.00,     0.00, 3),
(9, 1, '2025-09-01', 150000.00,     0.00, 3),
(9, 2, '2026-03-01', 150000.00,150000.00, 1),
(9, 3, '2026-09-01', 150000.00,150000.00, 1);

-- ============================================================
-- GRUPO 14: PAGOS
-- ============================================================

INSERT INTO PagoCliente (idContrato, idCuota, fechaPago, monto, idMetodoPago, idEstadoPago) VALUES
(1, 1, '2024-02-08',  37000.00, 1, 3),
(1, 2, '2024-04-09',  37000.00, 1, 3),
(2, 5, '2023-08-30', 184000.00, 1, 3),
(2, 6, '2023-12-28', 184000.00, 2, 3),
(3,10, '2024-05-14',  47500.00, 3, 3),
(3,11, '2024-07-19',  47500.00, 1, 3),
(4,12, '2023-11-28',  96000.00, 1, 3),
(4,13, '2024-02-28', 224000.00, 2, 3),
(5,14, '2024-06-30',  37500.00, 1, 3),
(6,16, '2025-12-28',  50000.00, 1, 3),
(7,19, '2025-05-28', 212500.00, 2, 3),
(8,23, '2024-09-28', 140000.00, 1, 3),
(8,24, '2025-01-28', 140000.00, 1, 3),
(9,25, '2025-08-28', 150000.00, 3, 3);

INSERT INTO PagoProveedor (idProveedor, fechaPago, monto, idMetodoPago, factura) VALUES
(1, '2024-01-18',  8700.00, 1, 'FAC-FANC-00123'),
(2, '2024-01-25', 15300.00, 1, 'FAC-ACER-00456'),
(5, '2024-03-15',  4750.00, 3, 'FAC-ARID-00789'),
(1, '2024-06-05',  5800.00, 1, 'FAC-FANC-00234'),
(3, '2024-05-15',  2100.00, 2, 'FAC-PINE-00101'),
(1, '2025-11-08', 12000.00, 1, 'FAC-FANC-00345'),
(2, '2025-11-15', 18500.00, 1, 'FAC-ACER-00567'),
(6, '2025-03-05',  8000.00, 2, 'FAC-PINR-00234'),
(5, '2024-08-10',  9500.00, 1, 'FAC-ARID-00890');

-- ============================================================
-- GRUPO 15: REGISTRO DE HORAS TRABAJADAS
-- ============================================================

INSERT INTO RegistroHoras (idEmpleado, idProyecto, fecha, horasTrabajadas, pagoPorHora, totalPago) VALUES
-- Albañiles en proyecto 1
(31, 1, '2024-01-15', 8.00, 20.00, 160.00),
(31, 1, '2024-01-16', 8.00, 20.00, 160.00),
(31, 1, '2024-01-17', 8.00, 20.00, 160.00),
(32, 1, '2024-01-15', 8.00, 15.00, 120.00),
(32, 1, '2024-01-16', 8.00, 15.00, 120.00),
(32, 1, '2024-01-17', 8.00, 15.00, 120.00),
-- Albañiles en proyecto 6 Casa Familiar Norte Enero 2026
(34, 6, '2026-01-05', 8.00, 20.00, 160.00),
(34, 6, '2026-01-06', 8.00, 20.00, 160.00),
(34, 6, '2026-01-07', 8.00, 20.00, 160.00),
(34, 6, '2026-01-08', 8.00, 20.00, 160.00),
(35, 6, '2026-01-05', 8.00, 15.00, 120.00),
(35, 6, '2026-01-06', 8.00, 15.00, 120.00),
(35, 6, '2026-01-07', 8.00, 15.00, 120.00),
(35, 6, '2026-01-08', 8.00, 15.00, 120.00),
(36, 6, '2026-01-05', 8.00, 18.00, 144.00),
(36, 6, '2026-01-06', 8.00, 18.00, 144.00),
(36, 6, '2026-01-12', 8.00, 18.00, 144.00),
(37, 6, '2026-01-05', 8.00, 22.00, 176.00),
(37, 6, '2026-01-06', 8.00, 22.00, 176.00),
(37, 6, '2026-01-13', 8.00, 22.00, 176.00),
(38, 6, '2026-01-07', 8.00, 16.00, 128.00),
(38, 6, '2026-01-08', 8.00, 16.00, 128.00),
(38, 6, '2026-01-14', 8.00, 16.00, 128.00),
-- Plomeros en proyecto 6 Casa Familiar Norte Enero 2026
(96, 6, '2026-01-05', 8.00, 20.00, 160.00),
(96, 6, '2026-01-06', 8.00, 20.00, 160.00),
(96, 6, '2026-01-07', 8.00, 20.00, 160.00),
(96, 6, '2026-01-08', 8.00, 20.00, 160.00),
(97, 6, '2026-01-05', 8.00, 15.00, 120.00),
(97, 6, '2026-01-06', 8.00, 15.00, 120.00),
(97, 6, '2026-01-07', 8.00, 15.00, 120.00),
(97, 6, '2026-01-08', 8.00, 15.00, 120.00),
(98, 6, '2026-01-05', 8.00, 17.00, 136.00),
(98, 6, '2026-01-06', 8.00, 17.00, 136.00),
(98, 6, '2026-01-09', 8.00, 17.00, 136.00);

-- ============================================================
-- GRUPO 16: INVENTARIO
-- ============================================================

INSERT INTO Inventario (idMaterial, stockActual, stockMinimo, ubicacion, fechaActualizacion) VALUES
(1,  500.00, 100.00, 'Bodega Central Estante A1',   '2026-01-01'),
(2, 2000.00, 500.00, 'Bodega Central Estante B1',   '2026-01-01'),
(3, 1500.00, 300.00, 'Bodega Central Estante B2',   '2026-01-01'),
(4,  200.00,  50.00, 'Bodega Madera Estante C1',    '2026-01-01'),
(5,   30.00,  10.00, 'Bodega Eléctrica Estante D1', '2026-01-01'),
(6,  300.00,  80.00, 'Bodega Central Estante A2',   '2026-01-01'),
(7,  250.00,  80.00, 'Bodega Central Estante A3',   '2026-01-01'),
(8,  100.00,  20.00, 'Bodega Pintura Estante E1',   '2026-01-01'),
(9,  800.00, 200.00, 'Bodega Central Estante F1',   '2026-01-01'),
(10,  50.00,  10.00, 'Bodega Central Estante A4',   '2026-01-01'),
(11,5000.00,1000.00, 'Bodega Central Estante G1',   '2026-01-01'),
(12,3000.00, 500.00, 'Bodega Central Estante B3',   '2026-01-01'),
(13, 800.00, 100.00, 'Bodega Madera Estante C2',    '2026-01-01'),
(14, 400.00,  50.00, 'Bodega Plomería Estante H1',  '2026-01-01'),
(15, 150.00,  30.00, 'Bodega Pintura Estante E2',   '2026-01-01');

-- ============================================================
-- GRUPO 17: BONIFICACION Y PAGO PLANILLA
-- ============================================================

INSERT INTO bonificacionempleado (idEmpleado, tipoBonificacion, aniosAntiguedad, porcentajeBono, salarioBase, gestion, descripcion, idEstadoPago) VALUES
(1,  'Antigüedad',  15,  25.00, 15000.00, 2025, 'Bono antigüedad más de 10 años',    3),
(6,  'Aguinaldo',   NULL,100.00,10000.00, 2025, 'Aguinaldo anual completo',           3),
(16, 'Antigüedad',   8,  15.00,  9000.00, 2025, 'Bono antigüedad 6 a 10 años',       1),
(26, 'Aguinaldo',   NULL,100.00, 4500.00, 2025, 'Aguinaldo anual',                    3),
(31, 'Antigüedad',   6,  10.00,  4500.00, 2025, 'Bono antigüedad 3 a 5 años',        1),
(96, 'Aguinaldo',   NULL,100.00, 4800.00, 2025, 'Aguinaldo anual',                    3),
(97, 'Legal',        5,   8.00,  4500.00, 2025, 'Beneficio normativa interna',        2),
(36, 'Antigüedad',   4,   5.00,  4600.00, 2025, 'Bono antigüedad 1 a 2 años',        1);

INSERT INTO pagoplanilla (idEmpleado, idBonificacion, fechaPago, monto, idMetodoPago, idEstadoPago) VALUES
(1,  1, '2025-12-15', 3750.00, 1, 3),
(6,  2, '2025-12-20',10000.00, 2, 3),
(26, 4, '2025-12-20',  4500.00, 1, 3),
(96, 6, '2025-12-20',  4800.00, 1, 3),
(97, 7, '2025-11-30',   360.00, 1, 2);

SET FOREIGN_KEY_CHECKS = 1;
SET SQL_SAFE_UPDATES = 1;

-- ============================================================
-- VERIFICACION FINAL
-- ============================================================
SELECT 'Empleado'    AS Tabla, COUNT(*) AS Total FROM Empleado    UNION ALL
SELECT 'Cliente',              COUNT(*)           FROM Cliente     UNION ALL
SELECT 'Proyecto',             COUNT(*)           FROM Proyecto    UNION ALL
SELECT 'Contrato',             COUNT(*)           FROM Contrato    UNION ALL
SELECT 'RegistroHoras',        COUNT(*)           FROM RegistroHoras UNION ALL
SELECT 'Albañiles', COUNT(*) FROM Empleado e JOIN Cargo c ON e.idCargo=c.idCargo WHERE c.nombreCargo='Albañil' UNION ALL
SELECT 'Plomeros',  COUNT(*) FROM Empleado e JOIN Cargo c ON e.idCargo=c.idCargo WHERE c.nombreCargo='Plomero';
