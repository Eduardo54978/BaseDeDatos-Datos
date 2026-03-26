-- ============================================================
--   DATOS DE EJEMPLO - Sistema Empresa Constructora
--   Con identificadores únicos por tabla
-- ============================================================

USE constructora;

-- ============================================================
-- GRUPO 1: Catálogos
-- ============================================================

INSERT INTO Cargo (idCargo, nombreCargo, descripcionCargo) VALUES
('CAR01', 'Gerente General',          'Responsable de la dirección general de la empresa'),
('CAR02', 'Jefe de Obra',             'Supervisa la ejecución de obras en campo'),
('CAR03', 'Arquitecto',               'Diseño y planificación de proyectos'),
('CAR04', 'Ingeniero Civil',          'Cálculo estructural y supervisión técnica'),
('CAR05', 'Electricista',             'Instalaciones eléctricas en obra'),
('CAR06', 'Albañil',                  'Trabajos de mampostería y acabados'),
('CAR07', 'Contador',                 'Gestión contable y financiera'),
('CAR08', 'Asistente Administrativo', 'Apoyo en tareas administrativas');

INSERT INTO TipoCliente (idTipoCliente, nombreTipoCliente, descripcionTipoCliente) VALUES
('TC01', 'Persona Natural', 'Cliente individual, persona física'),
('TC02', 'Empresa',         'Cliente corporativo o jurídico');

INSERT INTO EstadoProyecto (idEstadoProyecto, nombreEstadoProyecto, descripcionEstadoProyecto) VALUES
('EP01', 'En planificación', 'El proyecto está en fase de diseño y planificación'),
('EP02', 'En ejecución',     'El proyecto está siendo construido activamente'),
('EP03', 'Finalizado',       'El proyecto ha sido completado y entregado'),
('EP04', 'Suspendido',       'El proyecto está temporalmente paralizado');

INSERT INTO TipoProyecto (idTipoProyecto, nombreTipoProyecto, descripcionTipoProyecto) VALUES
('TP01', 'Casa',             'Construcción de vivienda unifamiliar'),
('TP02', 'Edificio',         'Construcción de edificio multifamiliar o comercial'),
('TP03', 'Carretera',        'Construcción o mejoramiento de vías'),
('TP04', 'Puente',           'Construcción de puentes y obras de arte'),
('TP05', 'Local Comercial',  'Construcción de espacios comerciales');

INSERT INTO EstadoContrato (idEstadoContrato, nombreEstadoContrato, descripcionEstadoContrato) VALUES
('EC01', 'Vigente',    'Contrato activo y en cumplimiento'),
('EC02', 'Finalizado', 'Contrato cumplido y cerrado'),
('EC03', 'Rescindido', 'Contrato cancelado antes de su vencimiento');

INSERT INTO TipoContrato (idTipoContrato, nombreTipoContrato, descripcionTipoContrato) VALUES
('TCONT01', 'Obra completa',      'Se contrata la ejecución total de la obra'),
('TCONT02', 'Por etapas',         'La obra se ejecuta y paga por fases'),
('TCONT03', 'Por administración', 'La empresa administra recursos del cliente');

INSERT INTO EstadoCotizacion (idEstadoCotizacion, nombreEstadoCotizacion, descripcionEstadoCotizacion) VALUES
('ECOT01', 'Pendiente', 'Cotización enviada, esperando respuesta del cliente'),
('ECOT02', 'Aprobado',  'Cotización aceptada por el cliente'),
('ECOT03', 'Rechazado', 'Cotización no aceptada por el cliente');

INSERT INTO Departamento (idDepartamento, nombreDepartamento, descripcionDepartamento) VALUES
('DEP01', 'Gerencia',     'Dirección y administración general'),
('DEP02', 'Obras',        'Ejecución y supervisión de proyectos'),
('DEP03', 'Diseño',       'Arquitectura e ingeniería de proyectos'),
('DEP04', 'Contabilidad', 'Finanzas, pagos y contabilidad'),
('DEP05', 'Logística',    'Compras, materiales y proveedores');

INSERT INTO EstadoOrden (idEstadoOrden, nombreEstadoOrden, descripcionEstadoOrden) VALUES
('EO01', 'Pendiente', 'Orden realizada, esperando entrega'),
('EO02', 'Entregada', 'Materiales recibidos conforme'),
('EO03', 'Cancelada', 'Orden anulada antes de la entrega');

INSERT INTO TipoMaterial (idTipoMaterial, nombreTipoMaterial, descripcionTipoMaterial) VALUES
('TM01', 'Cemento',   'Materiales cementantes y aglomerantes'),
('TM02', 'Acero',     'Varillas, mallas y perfiles de acero'),
('TM03', 'Madera',    'Tablones, vigas y madera en general'),
('TM04', 'Eléctrico', 'Cables, tuberías y accesorios eléctricos'),
('TM05', 'Áridos',    'Arena, grava y piedra triturada'),
('TM06', 'Pintura',   'Pinturas, barnices y selladores'),
('TM07', 'Cerámica',  'Pisos, azulejos y revestimientos');

INSERT INTO UnidadMedida (idUnidadMedida, nombreUnidadMedida, descripcionUnidadMedida) VALUES
('UM01', 'kg',     'Kilogramo'),
('UM02', 'bolsa',  'Bolsa (50 kg)'),
('UM03', 'm',      'Metro lineal'),
('UM04', 'm²',     'Metro cuadrado'),
('UM05', 'm³',     'Metro cúbico'),
('UM06', 'unidad', 'Pieza o unidad'),
('UM07', 'rollo',  'Rollo de cable o manguera'),
('UM08', 'litro',  'Litro');

INSERT INTO EstadoEmpleado (idEstadoEmpleado, nombreEstadoEmpleado, descripcionEstadoEmpleado) VALUES
('EE01', 'Activo',   'Empleado trabajando actualmente'),
('EE02', 'Inactivo', 'Empleado que ya no trabaja en la empresa');

INSERT INTO RolProyecto (idRolProyecto, nombreRolProyecto, descripcionRolProyecto) VALUES
('RP01', 'Director',   'Dirige y toma decisiones en el proyecto'),
('RP02', 'Supervisor', 'Supervisa el avance y calidad de la obra'),
('RP03', 'Técnico',    'Ejecuta tareas técnicas especializadas'),
('RP04', 'Operario',   'Realiza trabajos manuales en la obra');

INSERT INTO EstadoPago (idEstadoPago, nombreEstadoPago, descripcionEstadoPago) VALUES
('EPAGO01', 'Pendiente',  'Pago aún no realizado'),
('EPAGO02', 'Registrado', 'Pago registrado en el sistema'),
('EPAGO03', 'Verificado', 'Pago confirmado y validado'),
('EPAGO04', 'Anulado',    'Pago cancelado o revertido');

INSERT INTO MetodoPago (idMetodoPago, nombreMetodoPago, descripcionMetodoPago) VALUES
('MET01', 'Transferencia', 'Transferencia bancaria'),
('MET02', 'Cheque',        'Pago mediante cheque'),
('MET03', 'Efectivo',      'Pago en efectivo');

-- ============================================================
-- GRUPO 2: Clientes, Proveedores, Materiales, Empleados
-- ============================================================

INSERT INTO Cliente (idCliente, nombre, idTipoCliente, documentoID, numCelular, email, direccion, fechaRegistro) VALUES
('CLI001', 'Carlos Mendoza Ríos',        'TC01', '7823451',    '70012345', 'carlos.mendoza@gmail.com',  'Av. Heroínas 123, Cochabamba',  '2023-01-15'),
('CLI002', 'María Fernández Vega',       'TC01', '6541237',    '71023456', 'maria.fernandez@gmail.com', 'Calle Sucre 456, Cochabamba',   '2023-03-22'),
('CLI003', 'Constructora Horizonte SRL', 'TC02', '1023456789', '72034567', 'contacto@horizonte.com.bo', 'Av. Blanco Galindo Km 5',       '2022-11-10'),
('CLI004', 'Inmobiliaria Los Andes SA',  'TC02', '2034567890', '73045678', 'info@losandes.com.bo',      'Av. América 789, Cochabamba',   '2022-08-05'),
('CLI005', 'Roberto Salinas Peña',       'TC01', '5312789',    '74056789', 'roberto.salinas@hotmail.com','Calle Baptista 321, Cochabamba','2024-01-08');

INSERT INTO Proveedor (idProveedor, nombreProveedor, numCelular, email, direccion, ciudad, pais) VALUES
('PROV01', 'Cementos Fancesa',       '42201100', 'ventas@fancesa.com.bo',   'Av. Industrial 100',        'Sucre',       'Bolivia'),
('PROV02', 'Aceros del Sur SRL',     '72100200', 'info@acerosdelsur.com',   'Parque Industrial Zona Sur','Cochabamba',  'Bolivia'),
('PROV03', 'Maderería El Pino',      '71300400', 'elpino@gmail.com',        'Calle Comercio 55',         'Cochabamba',  'Bolivia'),
('PROV04', 'Electro Materiales SA',  '70400500', 'ventas@electroma.com.bo', 'Av. 6 de Agosto 200',       'La Paz',      'Bolivia'),
('PROV05', 'Áridos y Pétreos Norte', '71500600', 'aridos.norte@gmail.com',  'Carretera al Norte Km 3',   'Cochabamba',  'Bolivia');

INSERT INTO Material (idMaterial, nombreMaterial, idTipoMaterial, idUnidadMedida, precioUnitario, descripcion) VALUES
('MAT001', 'Cemento IP-30 Fancesa',  'TM01', 'UM02',  58.00, 'Cemento pórtland IP-30, bolsa 50kg'),
('MAT002', 'Varilla de acero 12mm',  'TM02', 'UM01',   8.50, 'Varilla corrugada de 12mm de diámetro'),
('MAT003', 'Varilla de acero 8mm',   'TM02', 'UM01',   5.20, 'Varilla corrugada de 8mm de diámetro'),
('MAT004', 'Tablón de madera 2"x8"', 'TM03', 'UM03',  35.00, 'Tablón de madera pino, 2 pulgadas x 8 pulgadas'),
('MAT005', 'Cable eléctrico 12AWG',  'TM04', 'UM07',  85.00, 'Cable THW 12 AWG rollo 100m'),
('MAT006', 'Arena fina',             'TM05', 'UM05',  80.00, 'Arena fina para construcción, por m³'),
('MAT007', 'Grava 3/4"',             'TM05', 'UM05',  95.00, 'Grava triturada 3/4 pulgada, por m³'),
('MAT008', 'Pintura látex blanca',   'TM06', 'UM08',  45.00, 'Pintura látex interior/exterior, litro'),
('MAT009', 'Piso cerámico 45x45',    'TM07', 'UM04',  65.00, 'Cerámica de piso 45x45 cm, por m²'),
('MAT010', 'Cemento blanco',         'TM01', 'UM02',  90.00, 'Cemento blanco para juntas y acabados');

INSERT INTO Empleado (idEmpleado, nombre, apellido, ci, fechaNacimiento, especialidad, numCelular, email, direccion, salario, fechaContratacion, idEstadoEmpleado, idCargo, idDepartamento) VALUES
('EMP001', 'Juan Pablo',  'Rojas Soria',     '4512378', '1980-05-12', 'Administración de Empresas', '70011111', 'jp.rojas@constructora.com',    'Av. Oquendo 100',     15000.00, '2015-03-01', 'EE01', 'CAR01', 'DEP01'),
('EMP002', 'Luis Alberto','Mamani Flores',   '5623489', '1985-08-20', 'Ingeniería Civil',           '71022222', 'l.mamani@constructora.com',    'Calle Lanza 200',     10000.00, '2017-06-15', 'EE01', 'CAR04', 'DEP02'),
('EMP003', 'Ana Cecilia', 'Torrico Vega',    '6734590', '1990-03-15', 'Arquitectura',               '72033333', 'a.torrico@constructora.com',   'Av. Ballivián 300',    9000.00, '2018-01-10', 'EE01', 'CAR03', 'DEP03'),
('EMP004', 'Pedro',       'Condori Quispe',  '7845601', '1978-11-30', 'Maestro de Obra',            '73044444', 'p.condori@constructora.com',   'Villa Pagador',        7000.00, '2016-09-01', 'EE01', 'CAR02', 'DEP02'),
('EMP005', 'Carmen Rosa', 'Gutierrez Paz',   '8956712', '1992-07-22', 'Contabilidad',               '74055555', 'c.gutierrez@constructora.com', 'Calle Hamiraya 400',   8000.00, '2019-04-20', 'EE01', 'CAR07', 'DEP04'),
('EMP006', 'Marco',       'Villanueva Cruz', '9067823', '1988-02-14', 'Electricidad Industrial',    '75066666', 'm.villanueva@constructora.com','Av. Tadeo Haenke 500', 6500.00, '2020-07-01', 'EE01', 'CAR05', 'DEP02'),
('EMP007', 'Rosa',        'Perez Alvarado',  '3401234', '1995-09-05', 'Administración',             '76077777', 'r.perez@constructora.com',     'Calle Punata 600',     5500.00, '2021-02-15', 'EE01', 'CAR08', 'DEP01');

-- ============================================================
-- GRUPO 3: Proyectos, Órdenes de Compra, ProveedorMaterial
-- ============================================================

INSERT INTO Proyecto (idProyecto, nombreProyecto, descripcion, idTipoProyecto, ubicacion, fechaInicio, fechaFinEstimada, fechaFinReal, idEstadoProyecto, idCliente) VALUES
('PROY001', 'Residencia Mendoza',       'Construcción de casa de dos plantas con jardín',       'TP01', 'Urbanización Las Brisas, Cochabamba', '2024-01-10', '2024-08-10', NULL,         'EP02', 'CLI001'),
('PROY002', 'Edificio Los Andes',       'Edificio de 6 pisos con 24 departamentos',             'TP02', 'Av. América 789, Cochabamba',         '2023-06-01', '2025-06-01', NULL,         'EP02', 'CLI004'),
('PROY003', 'Local Fernández',          'Construcción de local comercial 120 m²',               'TP05', 'Calle Sucre 456, Cochabamba',         '2024-03-15', '2024-07-15', '2024-07-20', 'EP03', 'CLI002'),
('PROY004', 'Pavimentación Zona Norte', 'Pavimentación de 2km de carretera vecinal',            'TP03', 'Zona Norte, Cochabamba',              '2023-09-01', '2024-03-01', '2024-03-15', 'EP03', 'CLI003'),
('PROY005', 'Ampliación Salinas',       'Ampliación y refacción de vivienda existente',         'TP01', 'Calle Baptista 321, Cochabamba',      '2024-05-01', '2024-10-01', NULL,         'EP01', 'CLI005');

INSERT INTO OrdenCompra (idOrdenCompra, fechaOrden, idEstadoOrden, idProveedor, montoTotal) VALUES
('OC001', '2024-01-15', 'EO02', 'PROV01',  8700.00),
('OC002', '2024-01-20', 'EO02', 'PROV02', 15300.00),
('OC003', '2024-03-10', 'EO01', 'PROV05',  4750.00),
('OC004', '2024-06-01', 'EO02', 'PROV01',  5800.00),
('OC005', '2024-05-10', 'EO01', 'PROV03',  2100.00);

INSERT INTO ProveedorMaterial (idProveedorMaterial, idProveedor, idMaterial, precioProveedor, tiempoEntrega) VALUES
('PROVMAT001', 'PROV01', 'MAT001', 55.00, 2),
('PROVMAT002', 'PROV02', 'MAT002',  8.00, 3),
('PROVMAT003', 'PROV02', 'MAT003',  5.00, 3),
('PROVMAT004', 'PROV03', 'MAT004', 32.00, 5),
('PROVMAT005', 'PROV04', 'MAT005', 82.00, 7),
('PROVMAT006', 'PROV05', 'MAT006', 75.00, 1),
('PROVMAT007', 'PROV05', 'MAT007', 90.00, 1),
('PROVMAT008', 'PROV01', 'MAT010', 85.00, 2);

-- ============================================================
-- GRUPO 4: Contratos, Cotizaciones, Asignaciones
-- ============================================================

INSERT INTO Contrato (idContrato, numeroContrato, idTipoContrato, fechaContrato, fechaFirma, fechaInicio, fechaVencimiento, montoTotal, idEstadoContrato, idProyecto) VALUES
('CONT001', 'CONT-2024-001', 'TCONT01', '2023-12-20', '2024-01-05', '2024-01-10', '2024-08-10',  185000.00, 'EC01', 'PROY001'),
('CONT002', 'CONT-2023-002', 'TCONT02', '2023-05-15', '2023-05-25', '2023-06-01', '2025-06-01',  920000.00, 'EC01', 'PROY002'),
('CONT003', 'CONT-2024-003', 'TCONT01', '2024-03-01', '2024-03-10', '2024-03-15', '2024-07-15',   95000.00, 'EC02', 'PROY003'),
('CONT004', 'CONT-2023-004', 'TCONT01', '2023-08-20', '2023-08-28', '2023-09-01', '2024-03-01',  320000.00, 'EC02', 'PROY004'),
('CONT005', 'CONT-2024-005', 'TCONT03', '2024-04-20', '2024-04-28', '2024-05-01', '2024-10-01',   75000.00, 'EC01', 'PROY005');

INSERT INTO CotizacionCliente (idCotizacionCliente, numeroCotizacionCliente, fechaCotizacion, fechaValidez, observaciones, idProyecto, idEstadoCotizacion) VALUES
('COTCLI001', 'COT-CLI-2023-001', '2023-12-01', '2023-12-31', 'Incluye materiales y mano de obra completa',          'PROY001', 'ECOT02'),
('COTCLI002', 'COT-CLI-2023-002', '2023-05-01', '2023-05-20', 'Precio por etapas, sujeto a ajuste por inflación',    'PROY002', 'ECOT02'),
('COTCLI003', 'COT-CLI-2024-003', '2024-02-20', '2024-03-05', 'Precio fijo todo incluido',                           'PROY003', 'ECOT02'),
('COTCLI004', 'COT-CLI-2023-004', '2023-08-10', '2023-08-25', 'Incluye señalización y compactación',                 'PROY004', 'ECOT02'),
('COTCLI005', 'COT-CLI-2024-005', '2024-04-10', '2024-04-25', 'Solo mano de obra, cliente provee algunos materiales','PROY005', 'ECOT02');

INSERT INTO CotizacionInterna (idCotizacionInterna, numeroCotizacionInterna, fechaCotizacion, observaciones, idProyecto, idEstadoCotizacion) VALUES
('COTINT001', 'COT-INT-2023-001', '2023-11-25', 'Costo real estimado proyecto Mendoza',      'PROY001', 'ECOT02'),
('COTINT002', 'COT-INT-2023-002', '2023-04-28', 'Costo real estimado edificio Los Andes',    'PROY002', 'ECOT02'),
('COTINT003', 'COT-INT-2024-003', '2024-02-18', 'Costo real estimado local Fernández',       'PROY003', 'ECOT02'),
('COTINT004', 'COT-INT-2023-004', '2023-08-08', 'Costo real estimado pavimentación',         'PROY004', 'ECOT02'),
('COTINT005', 'COT-INT-2024-005', '2024-04-08', 'Costo real estimado ampliación Salinas',    'PROY005', 'ECOT02');

INSERT INTO EmpleadoProyecto (idEmpleadoProyecto, idEmpleado, idProyecto, idRolProyecto, fechaInicio, fechaFin) VALUES
('EMPPROY001', 'EMP001', 'PROY001', 'RP01', '2024-01-10', NULL),
('EMPPROY002', 'EMP002', 'PROY001', 'RP02', '2024-01-10', NULL),
('EMPPROY003', 'EMP004', 'PROY001', 'RP04', '2024-01-10', NULL),
('EMPPROY004', 'EMP006', 'PROY001', 'RP03', '2024-02-01', NULL),
('EMPPROY005', 'EMP001', 'PROY002', 'RP01', '2023-06-01', NULL),
('EMPPROY006', 'EMP002', 'PROY002', 'RP02', '2023-06-01', NULL),
('EMPPROY007', 'EMP003', 'PROY002', 'RP03', '2023-06-01', NULL),
('EMPPROY008', 'EMP004', 'PROY002', 'RP04', '2023-06-01', NULL),
('EMPPROY009', 'EMP002', 'PROY003', 'RP02', '2024-03-15', '2024-07-20'),
('EMPPROY010', 'EMP004', 'PROY003', 'RP04', '2024-03-15', '2024-07-20'),
('EMPPROY011', 'EMP002', 'PROY004', 'RP02', '2023-09-01', '2024-03-15'),
('EMPPROY012', 'EMP004', 'PROY004', 'RP04', '2023-09-01', '2024-03-15');

INSERT INTO MaterialProyecto (idMaterialProyecto, idProyecto, idMaterial, cantidadUtilizada, fechaRegistro, costoTotal) VALUES
('MP001', 'PROY001', 'MAT001',  150.000, '2024-01-20',  8700.00),
('MP002', 'PROY001', 'MAT002', 1200.000, '2024-01-20', 10200.00),
('MP003', 'PROY001', 'MAT006',   80.000, '2024-02-01',  6400.00),
('MP004', 'PROY002', 'MAT001',  800.000, '2023-07-01', 46400.00),
('MP005', 'PROY002', 'MAT002', 5000.000, '2023-07-01', 42500.00),
('MP006', 'PROY002', 'MAT009', 1200.000, '2023-08-01', 78000.00),
('MP007', 'PROY003', 'MAT001',   80.000, '2024-03-20',  4640.00),
('MP008', 'PROY003', 'MAT008',  200.000, '2024-06-01',  9000.00),
('MP009', 'PROY004', 'MAT006',  500.000, '2023-09-10', 40000.00),
('MP010', 'PROY004', 'MAT007',  400.000, '2023-09-10', 38000.00);

-- ============================================================
-- GRUPO 5: Detalles de compras y cotizaciones
-- ============================================================

INSERT INTO DetalleCompra (idDetalleCompra, idOrdenCompra, idMaterial, cantidad, precioUnitario) VALUES
('DC001', 'OC001', 'MAT001', 150.000, 55.00),
('DC002', 'OC001', 'MAT006',  10.000, 75.00),
('DC003', 'OC002', 'MAT002', 800.000,  8.00),
('DC004', 'OC002', 'MAT003', 500.000,  5.00),
('DC005', 'OC003', 'MAT007',  50.000, 95.00),
('DC006', 'OC004', 'MAT001', 100.000, 58.00),
('DC007', 'OC005', 'MAT004',  60.000, 35.00);

INSERT INTO DetalleCotizacionCliente (idDetalleCotizacionCliente, idCotizacionCliente, concepto, descripcion, cantidad, precioUnitario) VALUES
('DCC001', 'COTCLI001', 'Cimentación',          'Excavación y losa de cimentación',         1.000,  25000.00),
('DCC002', 'COTCLI001', 'Estructura',            'Columnas, vigas y losa de entrepiso',       1.000,  55000.00),
('DCC003', 'COTCLI001', 'Mampostería',           'Muros de ladrillo visto y tarrajeado',      1.000,  40000.00),
('DCC004', 'COTCLI001', 'Instalaciones',         'Instalaciones eléctricas y sanitarias',     1.000,  30000.00),
('DCC005', 'COTCLI001', 'Acabados',              'Pisos, pintura y puertas',                  1.000,  35000.00),
('DCC006', 'COTCLI002', 'Etapa 1 - Sótano',     'Excavación y sótano',                       1.000, 150000.00),
('DCC007', 'COTCLI002', 'Etapa 2 - Estructura', 'Estructura de hormigón armado 6 pisos',     1.000, 400000.00),
('DCC008', 'COTCLI002', 'Etapa 3 - Acabados',   'Acabados, instalaciones y exteriores',      1.000, 370000.00),
('DCC009', 'COTCLI003', 'Obra gruesa',           'Cimentación, estructura y muros',           1.000,  55000.00),
('DCC010', 'COTCLI003', 'Acabados',              'Pisos, pintura y carpintería',              1.000,  40000.00);

INSERT INTO DetalleCotizacionInterna (idDetalleCotizacionInterna, idCotizacionInterna, idMaterial, cantidadEstimada, costoUnitarioEstimado) VALUES
('DCI001', 'COTINT001', 'MAT001',  150.000, 55.00),
('DCI002', 'COTINT001', 'MAT002', 1200.000,  8.00),
('DCI003', 'COTINT001', 'MAT006',   80.000, 75.00),
('DCI004', 'COTINT001', 'MAT007',   60.000, 90.00),
('DCI005', 'COTINT002', 'MAT001',  800.000, 55.00),
('DCI006', 'COTINT002', 'MAT002', 5000.000,  8.00),
('DCI007', 'COTINT002', 'MAT009', 1200.000, 62.00),
('DCI008', 'COTINT003', 'MAT001',   80.000, 55.00),
('DCI009', 'COTINT003', 'MAT008',  200.000, 42.00),
('DCI010', 'COTINT004', 'MAT006',  500.000, 75.00),
('DCI011', 'COTINT004', 'MAT007',  400.000, 90.00);

-- ============================================================
-- GRUPO 6: Cuotas
-- ============================================================

INSERT INTO Cuota (idCuota, idContrato, numeroCuota, fechaVencimiento, montoCuota, saldoPendiente, idEstadoPago) VALUES
('CUO001', 'CONT001', 1, '2024-02-10',  37000.00,      0.00, 'EPAGO03'),
('CUO002', 'CONT001', 2, '2024-04-10',  37000.00,      0.00, 'EPAGO03'),
('CUO003', 'CONT001', 3, '2024-06-10',  37000.00,  37000.00, 'EPAGO01'),
('CUO004', 'CONT001', 4, '2024-08-10',  74000.00,  74000.00, 'EPAGO01'),
('CUO005', 'CONT002', 1, '2023-09-01', 184000.00,      0.00, 'EPAGO03'),
('CUO006', 'CONT002', 2, '2024-01-01', 184000.00,      0.00, 'EPAGO03'),
('CUO007', 'CONT002', 3, '2024-07-01', 184000.00, 184000.00, 'EPAGO01'),
('CUO008', 'CONT002', 4, '2025-01-01', 184000.00, 184000.00, 'EPAGO01'),
('CUO009', 'CONT002', 5, '2025-06-01', 184000.00, 184000.00, 'EPAGO01'),
('CUO010', 'CONT003', 1, '2024-05-15',  47500.00,      0.00, 'EPAGO03'),
('CUO011', 'CONT003', 2, '2024-07-20',  47500.00,      0.00, 'EPAGO03'),
('CUO012', 'CONT004', 1, '2023-12-01',  96000.00,      0.00, 'EPAGO03'),
('CUO013', 'CONT004', 2, '2024-03-01', 224000.00,      0.00, 'EPAGO03'),
('CUO014', 'CONT005', 1, '2024-07-01',  37500.00,      0.00, 'EPAGO03'),
('CUO015', 'CONT005', 2, '2024-10-01',  37500.00,  37500.00, 'EPAGO01');

-- ============================================================
-- GRUPO 7: Pagos
-- ============================================================

INSERT INTO PagoCliente (idPagoCliente, idContrato, idCuota, fechaPago, monto, idMetodoPago, idEstadoPago) VALUES
('PCLI001', 'CONT001', 'CUO001', '2024-02-08',  37000.00, 'MET01', 'EPAGO03'),
('PCLI002', 'CONT001', 'CUO002', '2024-04-09',  37000.00, 'MET01', 'EPAGO03'),
('PCLI003', 'CONT002', 'CUO005', '2023-08-30', 184000.00, 'MET01', 'EPAGO03'),
('PCLI004', 'CONT002', 'CUO006', '2023-12-28', 184000.00, 'MET02', 'EPAGO03'),
('PCLI005', 'CONT003', 'CUO010', '2024-05-14',  47500.00, 'MET03', 'EPAGO03'),
('PCLI006', 'CONT003', 'CUO011', '2024-07-19',  47500.00, 'MET01', 'EPAGO03'),
('PCLI007', 'CONT004', 'CUO012', '2023-11-28',  96000.00, 'MET01', 'EPAGO03'),
('PCLI008', 'CONT004', 'CUO013', '2024-02-28', 224000.00, 'MET02', 'EPAGO03'),
('PCLI009', 'CONT005', 'CUO014', '2024-06-30',  37500.00, 'MET01', 'EPAGO03');

INSERT INTO PagoProveedor (idPagoProveedor, idProveedor, fechaPago, monto, idMetodoPago, factura) VALUES
('PPROV001', 'PROV01', '2024-01-18',  8700.00, 'MET01', 'FAC-FANC-00123'),
('PPROV002', 'PROV02', '2024-01-25', 15300.00, 'MET01', 'FAC-ACER-00456'),
('PPROV003', 'PROV05', '2024-03-15',  4750.00, 'MET03', 'FAC-ARID-00789'),
('PPROV004', 'PROV01', '2024-06-05',  5800.00, 'MET01', 'FAC-FANC-00234'),
('PPROV005', 'PROV03', '2024-05-15',  2100.00, 'MET02', 'FAC-PINE-00101');
