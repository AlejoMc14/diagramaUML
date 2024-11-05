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
![diagrama](/diagrama_comportamental/Diagrama_de_Estados/diagrama.png)
