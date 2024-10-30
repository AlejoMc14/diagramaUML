## Problema del Carrito de Compras

- El proyecto consiste en desarrollar una base de datos para un sistema de carrito de compras, donde los
estudiantes deberán manejar roles de administrador y comprador. Además, deberán realizar consultas SQL
como JOINs entre varias entidades. Las entidades mínimas que deben incluirse son Usuario, Producto,
Inventario, Detalle Factura y Factura. Cada ejercicio debe involucrar al menos cuatro entidades, y se deben
entregar scripts DDL y DML completos. El objetivo es que los estudiantes utilicen y generen la
documentación del proyecto de acuerdo con lo enseñado en clase, utilizando un archivo .md y generando
diagramas de clase parciales y generales.


## construccion del codigo en plantUML

´´´sql

@startuml
class Usuario {
    +Integer idUsuario
    +String nombre
    +String email
    +String rol
}

' Clase Producto
class Producto {
    +Integer idProducto
    +String nombre
    +Double precio
    +String categoria
}

' Clase Inventario
class Inventario {
    +Integer idInventario
    +Integer cantidad
    +Producto producto
}

' Clase Factura
class Factura {
    +Integer idFactura
    +Date fecha
    +Double total
    +Usuario usuario
}

' Clase DetalleFactura
class DetalleFactura {
    +Integer idDetalle
    +Integer cantidad
    +Double subtotal
    +Factura factura
    +Producto producto
}

' Relaciones entre clases
Usuario  --  Factura : crea
Factura  --  DetalleFactura : tiene
Producto  --  Inventario : esta en
Inventario  --  Producto : controla
Producto  --  DetalleFactura : va
@enduml

## Diagrama de Estructural

![estructural1](estructural1.PNG)
