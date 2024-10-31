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
title Carrito de Compras

actor Persona
actor User as Comprador
actor Administrator as Administrador

Persona <|-- Comprador
Persona <|-- Administrador

package "Sistema Carrito de Compras" as SC {
    usecase "Buscar Producto" as UC1
    usecase "Agregar al Carrito" as UC2
    usecase "Realizar Pago" as UC3
    usecase "Generar Factura" as UC4
    usecase "Gestionar Inventario" as UC5
    usecase "detalle factura" as UC6
}

Comprador --> UC1
Comprador --> UC2
Comprador --> UC3
UC3 --> UC6
Administrador --> UC5
UC4 --> UC6

UC5 --> UC4

database "Base de Datos" as DB
DB <--> SC


@enduml

## Diagrama de casos uso

![casos de uso](\out\caso_de_usoUML)
