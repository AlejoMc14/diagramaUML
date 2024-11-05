## Explicación
Flujo de Interacciones: Este diagrama muestra cómo los componentes se comunican entre sí para completar una compra.
Componentes Clave:
GUI: Interfaz gráfica del usuario que interactúa directamente con el comprador.
Sistema Carrito de Compras: Procesa las solicitudes de la GUI y administra las interacciones con la base de datos y el módulo de pago.
Base de Datos (DB): Consulta y actualiza datos, como la disponibilidad de productos y el inventario.
Pago: Responsable del proceso de pago y validación de información.
Factura: Genera y envía la confirmación de la compra al comprador.


## construccion del codigo en plantUML

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


## Diagrama 
![diagrama](/diagrama_comportamental/diagrama_de_colaboracion/diagrama.png)