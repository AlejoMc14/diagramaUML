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