sql´´´
@startuml
title Colaboración - Carrito de Compras

actor Comprador
participant ":GUI" as GUI
participant ":Sistema Carrito de Compras" as Sistema
participant ":Base de Datos" as DB
participant ":Pago" as Pago
participant ":Factura" as Factura

Comprador -> GUI : Seleccionar Producto
GUI -> Sistema : 1: Solicitar detalles del producto
Sistema -> DB : 2: Consultar disponibilidad
DB --> Sistema : Retorna disponibilidad

Comprador -> GUI : Agregar al Carrito
GUI -> Sistema : 3: Actualizar carrito
Sistema -> DB : 4: Actualizar inventario

Comprador -> GUI : Proceder al Pago
GUI -> Pago : 5: Iniciar proceso de pago
Pago -> DB : 6: Validar información de pago
Pago --> Sistema : Confirmación de pago
Sistema -> Factura : 7: Generar factura
Factura --> GUI : 8: Enviar confirmación
GUI --> Comprador : Mostrar confirmación de compra

@enduml


![diagrama](/diagrama_comportamental/diagrama_de_colaboracion/diagrama.png)