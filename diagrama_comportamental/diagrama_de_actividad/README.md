sql´´´
@startuml
title Diagrama de Actividad - Proceso de Compra en Carrito de Compras

start

:Seleccionar Producto;
if (Producto disponible?) then (Sí)
    :Mostrar detalles del producto;
    :Agregar producto al carrito;
else (No)
    :Notificar "Producto no disponible";
    stop
endif

:Verificar productos en el carrito;
if (¿Desea proceder al pago?) then (Sí)
    :Iniciar proceso de pago;
    :Validar método de pago;
    if (Pago exitoso?) then (Sí)
        :Generar factura;
        :Enviar confirmación de compra al comprador;
    else (No)
        :Notificar "Pago fallido";
        stop
    endif
else (No)
    :Permitir continuar comprando;
endif

stop
@enduml

![diagrama](/diagrama_comportamental/diagrama_de_actividad/diagrama.png)
