## Explicación de los Estados
Disponible: El estado inicial del producto, indicando que está disponible para el comprador.
Seleccionado: El producto es seleccionado por el comprador para ver más detalles.
Agregado al Carrito: El comprador agrega el producto al carrito.
En Proceso de Pago: El comprador decide proceder al pago y el sistema comienza el proceso.
Pago Exitoso: El pago se completa con éxito.
Pago Fallido: El pago es rechazado; el sistema vuelve al estado de Seleccionado para permitir un reintento.
Confirmado: El producto ha sido comprado con éxito, se genera una factura, y el proceso finaliza.

## construccion del codigo en plantUML

sql´´´
@startuml
title Diagrama de Estado - Proceso de Compra en Carrito de Compras

[*] --> Disponible : Producto cargado

Disponible --> Seleccionado : Selección por el Comprador
Seleccionado --> AgregadoAlCarrito : Agregar al carrito
AgregadoAlCarrito --> EnProcesoDePago : Proceder al pago
EnProcesoDePago --> PagoExitoso : Pago completado
EnProcesoDePago --> PagoFallido : Pago rechazado

PagoExitoso --> Confirmado : Generar factura y confirmar compra
Confirmado --> [*] : Fin del proceso

PagoFallido --> Seleccionado : Reintentar proceso de pago

@enduml

## Diagrama 
![diagrama](/diagrama_comportamental/Diagrama_de_Estados/diagrama.png)
