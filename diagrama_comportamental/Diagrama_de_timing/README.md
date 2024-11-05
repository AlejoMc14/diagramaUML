Explicación del Diagrama de Tiempos
Componentes:

Comprador (C): El cliente que interactúa con el sistema.
Interfaz de Usuario (UI): La interfaz a través de la cual el comprador interactúa.
Sistema Carrito (SC): Gestiona el carrito y la lógica de procesamiento de pedidos.
Base de Datos (DB): Almacena la información de los productos y la factura.
Pago (P): Verifica y procesa el pago.
Eventos:

@0: El comprador comienza a seleccionar un producto.
@5: El comprador agrega el producto al carrito, y el sistema comienza a procesarlo.
@10: El sistema actualiza el inventario en la base de datos.
@15: El comprador procede al pago, y el sistema inicia la verificación del pago.
@20: El pago es exitoso y el sistema genera una factura.
@25: La interfaz de usuario confirma la compra, y la base de datos guarda la factura.
@30: Todos los componentes vuelven a estar inactivos al finalizar el proceso de compra.
sql´´´
@startuml
title Diagrama de Tiempos - Proceso de Compra en Carrito de Compras

robust "Comprador" as C
concise "Interfaz de Usuario" as UI
concise "Sistema Carrito" as SC
concise "Base de Datos" as DB
concise "Pago" as P

@0
C is "Seleccionando Producto" #LightBlue
UI is "Esperando Selección" #LightGray
SC is "Esperando Solicitud" #LightGray
DB is "Inactivo" #LightGray
P is "Inactivo" #LightGray

@5
C is "Agregando al Carrito" #LightBlue
UI is "Enviando Solicitud" #LightGreen
SC is "Procesando Carrito" #LightGreen

@10
SC is "Actualizando Inventario" #LightGreen
DB is "Actualizando Datos" #Yellow

@15
C is "Procediendo al Pago" #LightBlue
UI is "Solicitando Pago" #LightGreen
SC is "Validando" #LightGreen
P is "Verificando Pago" #Yellow

@20
P is "Pago Exitoso" #LightGreen
SC is "Generando Factura" #Yellow

@25
UI is "Confirmando Compra" #LightGreen
C is "Compra Completa" #LightBlue
DB is "Guardando Factura" #Yellow

@30
C is "Finalizado" #LightGray
UI is "Inactivo" #LightGray
SC is "Inactivo" #LightGray
DB is "Inactivo" #LightGray
P is "Inactivo" #LightGray

@enduml

![diagrama](/diagrama_comportamental/Diagrama_de_timing/diagrama.png)
