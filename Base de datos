CREATE TABLE ingredientes (
	id_ingrediente int (10) auto_increment,
    nombre varchar (30),
    precio decimal (5,2),
    id_local int (10),
    id_estado int (10),
    PRIMARY KEY (id_ingrediente),
    FOREIGN KEY (id_local) REFERENCES local (id_local),
    FOREIGN KEY (id_estado) REFERENCES estados (id_estado)
);

CREATE TABLE platillos ( 
	id_platillo int (10) auto_increment,
    id_local int (10),
    nombre_platillo varchar (60),
    precio decimal (5,2),
    tiempo_preparacion smallint(4),
    cantidad tinyint (2),
    descripcion varchar (80),
    id_estado int (10),
    PRIMARY KEY (id_platillo),
    FOREIGN KEY (id_local) REFERENCES local (id_local),
    FOREIGN KEY (id_estado) REFERENCES estados (id_estado)
);

CREATE TABLE detalle_platillo (
	id_detalle_platillo int (10) auto_increment,
    id_platillo int (10),
    id_ingrediente int(10),
    PRIMARY KEY (id_detalle_platillo),
    FOREIGN KEY (id_platillo) REFERENCES platillos (id_platillo),
    FOREIGN KEY (id_ingrediente) REFERENCES ingredientes (id_ingrediente)
);

CREATE TABLE pedidos (
	id_pedido int (10) auto_increment,
    id_local int (10),
    id_usuario int (10),
    precio_total decimal (5,2),
    fecha_hora datetime,
    id_estado int (10),
    PRIMARY KEY (id_pedido),
    FOREIGN KEY (id_local) REFERENCES local (id_local),
    FOREIGN KEY (id_usuario) REFERENCES usuarios (id_usuario),
    FOREIGN KEY (id_estado) REFERENCES estados (id_estado)
);

CREATE TABLE detalle_pedido (
	id_detalle_pedido int (10) auto_increment,
    id_platillo int (10),
    id_pedido int (10),
    cantidad tinyint (2),
    precio_subtotal decimal (5,2),
    comentarios varchar (80),
    id_estado int (10),
    PRIMARY KEY (id_detalle_pedido),
    FOREIGN KEY (id_platillo) REFERENCES platillos (id_platillo),
    FOREIGN KEY (id_pedido) REFERENCES pedidos (id_pedido),
    FOREIGN KEY (id_estado) REFERENCES estados (id_estado)
);

CREATE TABLE detalle_ingredientes (
	id_detalle_ingrediente int (10) auto_increment,
    id_detalle_pedido int (10),
    id_ingrediente int (10),
    PRIMARY KEY (id_detalle_ingrediente),
    FOREIGN KEY (id_detalle_pedido) REFERENCES detalle_pedido (id_detalle_pedido),
    FOREIGN KEY (id_ingrediente) REFERENCES ingredientes (id_ingrediente)
);

Insert into estados (estado) 
values
('En existencia'),
('Agotado'),
('Activado'),
('Desactivado'),
('En espera'),
('En proceso'),
('Terminado');
