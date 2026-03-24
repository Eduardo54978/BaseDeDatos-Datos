-- ============================================================
--   DATOS DE EJEMPLO - Sistema Empresa Constructora
-- ============================================================

USE constructora;

-- ============================================================
-- GRUPO 1: Catálogos
-- ============================================================

INSERT INTO Cargo (nombreCargo, descripcionCargo) VALUES
('Gerente General',       'Responsable de la dirección general de la empresa'),
('Jefe de Obra',          'Supervisa la ejecución de obras en campo'),
('Arquitecto',            'Diseño y planificación de proyectos'),
('Ingeniero Civil',       'Cálculo estructural y supervisión técnica'),
('Electricista',          'Instalaciones eléctricas en obra'),
('Albañil',               'Trabajos de mampostería y acabados'),
('Contador',              'Gestión contable y financiera'),
('Asistente Administrativo', 'Apoyo en tareas administrativas');

INSERT INTO TipoCliente (nombreTipoCliente, descripcionTipoCliente) VALUES
('Persona Natural', 'Cliente individual, persona física'),
('Empresa',         'Cliente corporativo o jurídico');

INSERT INTO EstadoProyecto (nombreEstadoProyecto, descripcionEstadoProyecto) VALUES
('En planificación', 'El proyecto está en fase de diseño y planificación'),
('En ejecución',     'El proyecto está siendo construido activamente'),
('Finalizado',       'El proyecto ha sido completado y entregado'),
('Suspendido',       'El proyecto está temporalmente paralizado');

INSERT INTO TipoProyecto (nombreTipoProyecto, descripcionTipoProyecto) VALUES
('Casa',        'Construcción de vivienda unifamiliar'),
('Edificio',    'Construcción de edificio multifamiliar o comercial'),
('Carretera',   'Construcción o mejoramiento de vías'),
('Puente',      'Construcción de puentes y obras de arte'),
('Local Comercial', 'Construcción de espacios comerciales');

INSERT INTO EstadoContrato (nombreEstadoContrato, descripcionEstadoContrato) VALUES
('Vigente',    'Contrato activo y en cumplimiento'),
('Finalizado', 'Contrato cumplido y cerrado'),
('Rescindido', 'Contrato cancelado antes de su vencimiento');

INSERT INTO TipoContrato (nombreTipoContrato, descripcionTipoContrato) VALUES
('Obra completa',      'Se contrata la ejecución total de la obra'),
('Por etapas',         'La obra se ejecuta y paga por fases'),
('Por administración', 'La empresa administra recursos del cliente');

INSERT INTO EstadoCotizacion (nombreEstadoCotizacion, descripcionEstadoCotizacion) VALUES
('Pendiente', 'Cotización enviada, esperando respuesta del cliente'),
('Aprobado',  'Cotización aceptada por el cliente'),
('Rechazado', 'Cotización no aceptada por el cliente');

INSERT INTO Departamento (nombreDepartamento, descripcionDepartamento) VALUES
('Gerencia',        'Dirección y administración general'),
('Obras',           'Ejecución y supervisión de proyectos'),
('Diseño',          'Arquitectura e ingeniería de proyectos'),
('Contabilidad',    'Finanzas, pagos y contabilidad'),
('Logística',       'Compras, materiales y proveedores');

INSERT INTO EstadoOrden (nombreEstadoOrden, descripcionEstadoOrden) VALUES
('Pendiente',  'Orden realizada, esperando entrega'),
('Entregada',  'Materiales recibidos conforme'),
('Cancelada',  'Orden anulada antes de la entrega');

INSERT INTO TipoMaterial (nombreTipoMaterial, descripcionTipoMaterial) VALUES
('Cemento',    'Materiales cementantes y aglomerantes'),
('Acero',      'Varillas, mallas y perfiles de acero'),
('Madera',     'Tablones, vigas y madera en general'),
('Eléctrico',  'Cables, tuberías y accesorios eléctricos'),
('Áridos',     'Arena, grava y piedra triturada'),
('Pintura',    'Pinturas, barnices y selladores'),
('Cerámica',   'Pisos, azulejos y revestimientos');

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
('Director',    'Dirige y toma decisiones en el proyecto'),
('Supervisor',  'Supervisa el avance y calidad de la obra'),
('Técnico',     'Ejecuta tareas técnicas especializadas'),
('Operario',    'Realiza trabajos manuales en la obra');

INSERT INTO EstadoPago (nombreEstadoPago, descripcionEstadoPago) VALUES
('Pendiente',   'Pago aún no realizado'),
('Registrado',  'Pago registrado en el sistema'),
('Verificado',  'Pago confirmado y validado'),
('Anulado',     'Pago cancelado o revertido');

INSERT INTO MetodoPago (nombreMetodoPago, descripcionMetodoPago) VALUES
('Transferencia', 'Transferencia bancaria'),
('Cheque',        'Pago mediante cheque'),
('Efectivo',      'Pago en efectivo');

-- ============================================================
-- GRUPO 2: Clientes, Proveedores, Materiales, Empleados
-- ============================================================

INSERT INTO Cliente (nombre, idTipoCliente, documentoID, numCelular, email, direccion, fechaRegistro) VALUES
('Carlos Mendoza Ríos',        1, '7823451',   '70012345', 'carlos.mendoza@gmail.com',   'Av. Heroínas 123, Cochabamba',    '2023-01-15'),
('María Fernández Vega',       1, '6541237',   '71023456', 'maria.fernandez@gmail.com',  'Calle Sucre 456, Cochabamba',     '2023-03-22'),
('Constructora Horizonte SRL', 2, '1023456789','72034567', 'contacto@horizonte.com.bo',  'Av. Blanco Galindo Km 5',         '2022-11-10'),
('Inmobiliaria Los Andes SA',  2, '2034567890','73045678', 'info@losandes.com.bo',       'Av. América 789, Cochabamba',     '2022-08-05'),
('Roberto Salinas Peña',       1, '5312789',   '74056789', 'roberto.salinas@hotmail.com','Calle Baptista 321, Cochabamba',  '2024-01-08');

INSERT INTO Proveedor (nombreProveedor, numCelular, email, direccion, ciudad, pais) VALUES
('Cementos Fancesa',       '42201100', 'ventas@fancesa.com.bo',    'Av. Industrial 100',       'Sucre',        'Bolivia'),
('Aceros del Sur SRL',     '72100200', 'info@acerosdelsur.com',    'Parque Industrial Zona Sur','Cochabamba',  'Bolivia'),
('Maderería El Pino',      '71300400', 'elpino@gmail.com',         'Calle Comercio 55',        'Cochabamba',   'Bolivia'),
('Electro Materiales SA',  '70400500', 'ventas@electroma.com.bo',  'Av. 6 de Agosto 200',      'La Paz',       'Bolivia'),
('Áridos y Pétreos Norte', '71500600', 'aridos.norte@gmail.com',   'Carretera al Norte Km 3',  'Cochabamba',   'Bolivia');

INSERT INTO Material (nombreMaterial, idTipoMaterial, idUnidadMedida, precioUnitario, descripcion) VALUES
('Cemento IP-30 Fancesa',    1, 2,  58.00,  'Cemento pórtland IP-30, bolsa 50kg'),
('Varilla de acero 12mm',    2, 1,   8.50,  'Varilla corrugada de 12mm de diámetro'),
('Varilla de acero 8mm',     2, 1,   5.20,  'Varilla corrugada de 8mm de diámetro'),
('Tablón de madera 2"x8"',   3, 3,  35.00,  'Tablón de madera pino, 2 pulgadas x 8 pulgadas'),
('Cable eléctrico 12AWG',    4, 7,  85.00,  'Cable THW 12 AWG rollo 100m'),
('Arena fina',               5, 5,  80.00,  'Arena fina para construcción, por m³'),
('Grava 3/4"',               5, 5,  95.00,  'Grava triturada 3/4 pulgada, por m³'),
('Pintura látex blanca',     6, 8,  45.00,  'Pintura látex interior/exterior, litro'),
('Piso cerámico 45x45',      7, 4,  65.00,  'Cerámica de piso 45x45 cm, por m²'),
('Cemento blanco',           1, 2,  90.00,  'Cemento blanco para juntas y acabados');

INSERT INTO Empleado (nombre, apellido, ci, fechaNacimiento, especialidad, numCelular, email, direccion, salario, fechaContratacion, idEstadoEmpleado, idCargo, idDepartamento) VALUES
('Juan Pablo',  'Rojas Soria',     '4512378', '1980-05-12', 'Administración de Empresas', '70011111', 'jp.rojas@constructora.com',    'Av. Oquendo 100',     15000.00, '2015-03-01', 1, 1, 1),
('Luis Alberto','Mamani Flores',   '5623489', '1985-08-20', 'Ingeniería Civil',           '71022222', 'l.mamani@constructora.com',    'Calle Lanza 200',     10000.00, '2017-06-15', 1, 4, 2),
('Ana Cecilia', 'Torrico Vega',    '6734590', '1990-03-15', 'Arquitectura',               '72033333', 'a.torrico@constructora.com',   'Av. Ballivián 300',    9000.00, '2018-01-10', 1, 3, 3),
('Pedro',       'Condori Quispe',  '7845601', '1978-11-30', 'Maestro de Obra',            '73044444', 'p.condori@constructora.com',   'Villa Pagador',        7000.00, '2016-09-01', 1, 2, 2),
('Carmen Rosa', 'Gutierrez Paz',   '8956712', '1992-07-22', 'Contabilidad',               '74055555', 'c.gutierrez@constructora.com', 'Calle Hamiraya 400',   8000.00, '2019-04-20', 1, 7, 4),
('Marco',       'Villanueva Cruz', '9067823', '1988-02-14', 'Electricidad Industrial',    '75066666', 'm.villanueva@constructora.com','Av. Tadeo Haenke 500', 6500.00, '2020-07-01', 1, 5, 2),
('Rosa',        'Perez Alvarado',  '3401234', '1995-09-05', 'Administración',             '76077777', 'r.perez@constructora.com',     'Calle Punata 600',     5500.00, '2021-02-15', 1, 8, 1);

-- ============================================================
-- GRUPO 3: Proyectos, Órdenes de Compra, ProveedorMaterial
-- ============================================================

INSERT INTO Proyecto (nombreProyecto, descripcion, idTipoProyecto, ubicacion, fechaInicio, fechaFinEstimada, fechaFinReal, idEstadoProyecto, idCliente) VALUES
('Residencia Mendoza',       'Construcción de casa de dos plantas con jardín',         1, 'Urbanización Las Brisas, Cochabamba', '2024-01-10', '2024-08-10', NULL,         2, 1),
('Edificio Los Andes',       'Edificio de 6 pisos con 24 departamentos',               2, 'Av. América 789, Cochabamba',         '2023-06-01', '2025-06-01', NULL,         2, 4),
('Local Fernández',          'Construcción de local comercial 120 m²',                5, 'Calle Sucre 456, Cochabamba',         '2024-03-15', '2024-07-15', '2024-07-20', 3, 2),
('Pavimentación Zona Norte', 'Pavimentación de 2km de carretera vecinal',              3, 'Zona Norte, Cochabamba',              '2023-09-01', '2024-03-01', '2024-03-15', 3, 3),
('Ampliación Salinas',       'Ampliación y refacción de vivienda existente',           1, 'Calle Baptista 321, Cochabamba',      '2024-05-01', '2024-10-01', NULL,         1, 5);

INSERT INTO OrdenCompra (fechaOrden, idEstadoOrden, idProveedor, montoTotal) VALUES
('2024-01-15', 2, 1,  8700.00),
('2024-01-20', 2, 2, 15300.00),
('2024-03-10', 1, 5,  4750.00),
('2024-06-01', 2, 1,  5800.00),
('2024-05-10', 1, 3,  2100.00);

INSERT INTO ProveedorMaterial (idProveedor, idMaterial, precioProveedor, tiempoEntrega) VALUES
(1, 1,  55.00, 2),
(2, 2,   8.00, 3),
(2, 3,   5.00, 3),
(3, 4,  32.00, 5),
(4, 5,  82.00, 7),
(5, 6,  75.00, 1),
(5, 7,  90.00, 1),
(1,10,  85.00, 2);

-- ============================================================
-- GRUPO 4: Contratos, Cotizaciones, Asignaciones
-- ============================================================

INSERT INTO Contrato (numeroContrato, idTipoContrato, fechaContrato, fechaFirma, fechaInicio, fechaVencimiento, montoTotal, idEstadoContrato, idProyecto) VALUES
('CONT-2024-001', 1, '2023-12-20', '2024-01-05', '2024-01-10', '2024-08-10', 185000.00, 1, 1),
('CONT-2023-002', 2, '2023-05-15', '2023-05-25', '2023-06-01', '2025-06-01', 920000.00, 1, 2),
('CONT-2024-003', 1, '2024-03-01', '2024-03-10', '2024-03-15', '2024-07-15',  95000.00, 2, 3),
('CONT-2023-004', 1, '2023-08-20', '2023-08-28', '2023-09-01', '2024-03-01', 320000.00, 2, 4),
('CONT-2024-005', 3, '2024-04-20', '2024-04-28', '2024-05-01', '2024-10-01',  75000.00, 1, 5);

INSERT INTO CotizacionCliente (numeroCotizacionCliente, fechaCotizacion, fechaValidez, observaciones, idProyecto, idEstadoCotizacion) VALUES
('COT-CLI-2023-001', '2023-12-01', '2023-12-31', 'Incluye materiales y mano de obra completa',         1, 2),
('COT-CLI-2023-002', '2023-05-01', '2023-05-20', 'Precio por etapas, sujeto a ajuste por inflación',   2, 2),
('COT-CLI-2024-003', '2024-02-20', '2024-03-05', 'Precio fijo todo incluido',                          3, 2),
('COT-CLI-2023-004', '2023-08-10', '2023-08-25', 'Incluye señalización y compactación',                4, 2),
('COT-CLI-2024-005', '2024-04-10', '2024-04-25', 'Solo mano de obra, cliente provee algunos materiales',5, 2);

INSERT INTO CotizacionInterna (numeroCotizacionInterna, fechaCotizacion, observaciones, idProyecto, idEstadoCotizacion) VALUES
('COT-INT-2023-001', '2023-11-25', 'Costo real estimado proyecto Mendoza',       1, 2),
('COT-INT-2023-002', '2023-04-28', 'Costo real estimado edificio Los Andes',     2, 2),
('COT-INT-2024-003', '2024-02-18', 'Costo real estimado local Fernández',        3, 2),
('COT-INT-2023-004', '2023-08-08', 'Costo real estimado pavimentación',          4, 2),
('COT-INT-2024-005', '2024-04-08', 'Costo real estimado ampliación Salinas',     5, 2);

INSERT INTO EmpleadoProyecto (idEmpleado, idProyecto, idRolProyecto, fechaInicio, fechaFin) VALUES
(1, 1, 1, '2024-01-10', NULL),
(2, 1, 2, '2024-01-10', NULL),
(4, 1, 4, '2024-01-10', NULL),
(6, 1, 3, '2024-02-01', NULL),
(1, 2, 1, '2023-06-01', NULL),
(2, 2, 2, '2023-06-01', NULL),
(3, 2, 3, '2023-06-01', NULL),
(4, 2, 4, '2023-06-01', NULL),
(2, 3, 2, '2024-03-15', '2024-07-20'),
(4, 3, 4, '2024-03-15', '2024-07-20'),
(2, 4, 2, '2023-09-01', '2024-03-15'),
(4, 4, 4, '2023-09-01', '2024-03-15');

INSERT INTO MaterialProyecto (idProyecto, idMaterial, cantidadUtilizada, fechaRegistro, costoTotal) VALUES
(1, 1,  150.000, '2024-01-20',  8700.00),
(1, 2, 1200.000, '2024-01-20', 10200.00),
(1, 6,   80.000, '2024-02-01',  6400.00),
(2, 1,  800.000, '2023-07-01', 46400.00),
(2, 2, 5000.000, '2023-07-01', 42500.00),
(2, 9, 1200.000, '2023-08-01', 78000.00),
(3, 1,   80.000, '2024-03-20',  4640.00),
(3, 8,  200.000, '2024-06-01',  9000.00),
(4, 6,  500.000, '2023-09-10', 40000.00),
(4, 7,  400.000, '2023-09-10', 38000.00);

-- ============================================================
-- GRUPO 5: Detalles de compras y cotizaciones
-- ============================================================

INSERT INTO DetalleCompra (idOrdenCompra, idMaterial, cantidad, precioUnitario) VALUES
(1,  1, 150.000, 55.00),
(1,  6,  10.000, 75.00),
(2,  2, 800.000,  8.00),
(2,  3, 500.000,  5.00),
(3,  7,  50.000, 95.00),
(4,  1, 100.000, 58.00),
(5,  4,  60.000, 35.00);

INSERT INTO DetalleCotizacionCliente (idCotizacionCliente, concepto, descripcion, cantidad, precioUnitario) VALUES
(1, 'Cimentación',         'Excavación y losa de cimentación',          1.000, 25000.00),
(1, 'Estructura',          'Columnas, vigas y losa de entrepiso',        1.000, 55000.00),
(1, 'Mampostería',         'Muros de ladrillo visto y tarrajeado',       1.000, 40000.00),
(1, 'Instalaciones',       'Instalaciones eléctricas y sanitarias',      1.000, 30000.00),
(1, 'Acabados',            'Pisos, pintura y puertas',                   1.000, 35000.00),
(2, 'Etapa 1 - Sotano',    'Excavación y sótano',                        1.000,150000.00),
(2, 'Etapa 2 - Estructura','Estructura de hormigón armado 6 pisos',      1.000,400000.00),
(2, 'Etapa 3 - Acabados',  'Acabados, instalaciones y exteriores',       1.000,370000.00),
(3, 'Obra gruesa',         'Cimentación, estructura y muros',            1.000, 55000.00),
(3, 'Acabados',            'Pisos, pintura y carpintería',               1.000, 40000.00);

INSERT INTO DetalleCotizacionInterna (idCotizacionInterna, idMaterial, cantidadEstimada, costoUnitarioEstimado) VALUES
(1, 1, 150.000, 55.00),
(1, 2,1200.000,  8.00),
(1, 6,  80.000, 75.00),
(1, 7,  60.000, 90.00),
(2, 1, 800.000, 55.00),
(2, 2,5000.000,  8.00),
(2, 9,1200.000, 62.00),
(3, 1,  80.000, 55.00),
(3, 8, 200.000, 42.00),
(4, 6, 500.000, 75.00),
(4, 7, 400.000, 90.00);

-- ============================================================
-- GRUPO 6: Cuotas
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
(5, 2, '2024-10-01',  37500.00, 37500.00, 1);

-- ============================================================
-- GRUPO 7: Pagos
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
(5,14, '2024-06-30',  37500.00, 1, 3);

INSERT INTO PagoProveedor (idProveedor, fechaPago, monto, idMetodoPago, factura) VALUES
(1, '2024-01-18',  8700.00, 1, 'FAC-FANC-00123'),
(2, '2024-01-25', 15300.00, 1, 'FAC-ACER-00456'),
(5, '2024-03-15',  4750.00, 3, 'FAC-ARID-00789'),
(1, '2024-06-05',  5800.00, 1, 'FAC-FANC-00234'),
(3, '2024-05-15',  2100.00, 2, 'FAC-PINE-00101');
