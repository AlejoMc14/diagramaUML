Explicación
Actores y Componentes:

Comprador representa al usuario que interactúa con el sistema.
Interfaz de Usuario (UI) representa la interfaz mediante la cual el Comprador interactúa con el sistema.
Sistema Carrito de Compras representa la lógica del sistema.
Base de Datos (DB) guarda y actualiza la información de productos y facturas.
Flujo de la Secuencia:

El Comprador selecciona un producto, y el Sistema obtiene los detalles de la Base de Datos.
Luego, el Comprador agrega el producto al carrito, lo que actualiza el inventario en la base de datos.
Finalmente, el Comprador procede al pago, y el sistema registra la factura en la base de datos y confirma la compra al usuario.
´´´sql

@startuml
title Secuencia de Compra de Producto - Carrito de Compras

actor Comprador
participant "Interfaz de Usuario" as UI
participant "Sistema Carrito de Compras" as Sistema
database "Base de Datos" as DB

Comprador -> UI: Seleccionar Producto
UI -> Sistema: Solicitar Detalles del Producto
Sistema -> DB: Consultar Detalles del Producto
DB --> Sistema: Retornar Detalles del Producto
Sistema --> UI: Mostrar Detalles al Comprador

Comprador -> UI: Agregar Producto al Carrito
UI -> Sistema: Añadir Producto al Carrito
Sistema -> DB: Actualizar Inventario

Comprador -> UI: Proceder al Pago
UI -> Sistema: Iniciar Proceso de Pago
Sistema -> DB: Crear Registro de Factura
DB --> Sistema: Confirmar Factura

Sistema --> UI: Confirmación de Compra
UI --> Comprador: Mostrar Confirmación y Factura

@enduml

![diagrama secuencial](/diagrama_comportamental/diagrama_secuencial/diagrama.png)


