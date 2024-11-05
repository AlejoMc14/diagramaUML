Explicación del Diagrama
Inicio y Selección de Producto: El proceso comienza con la selección de un producto.
Verificación de Disponibilidad: Se verifica si el producto está disponible.
Si el producto está disponible, se muestran los detalles y el usuario puede agregarlo al carrito.
Si el producto no está disponible, se notifica al usuario y el proceso finaliza.
Proceso de Pago:
Si el comprador decide proceder al pago, el sistema valida el método de pago.
Si el pago es exitoso, se genera una factura y se envía la confirmación de compra.
Si el pago falla, se notifica al usuario.
Continuar Comprando: Si el comprador decide no proceder al pago, puede continuar seleccionando productos.
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
