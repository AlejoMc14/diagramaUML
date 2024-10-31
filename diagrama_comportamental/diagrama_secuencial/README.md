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

![diagrama secuencial](/out/diagrama_comportamental/diagrama_secuencial/codigo/codigo.png)
