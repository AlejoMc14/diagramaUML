Problema del Carrito de Compras
• El proyecto consiste en desarrollar una base de datos para un sistema de
carrito de compras, donde los estudiantes deberán manejar roles de administrador y comprador. Además, deberán realizar consultas SQL como
JOINs entre varias entidades. Las entidades mínimas que deben incluirse
son Usuario, Producto, Inventario, Detalle Factura y Factura. Cada ejercicio debe involucrar al menos cuatro entidades, y se deben entregar scripts
DDL y DML completos. El objetivo es que los estudiantes utilicen y
generen la documentación del proyecto de acuerdo con lo enseñado en
clase, utilizando un archivo .md y generando diagramas de clase parciales
y generales.
construccion del codigo en plantUML
´´´sql
@startuml object usuario1 { idUsuario: 1 nombre: “Sebastian Bermudez” email:
“sbermudez-2023a@corhuila.edu.co” rol: “Comprador” }
object producto1 { idProducto: nombre: “Chicle” precio: 500 categoria:
“Golosina” }
object producto2 { idProducto: 1 nombre: “Lapiz” precio: 3000 categoria: “Util
escolar” }
object factura1 { idFactura: 1 fecha: “2024-10-30” total: 3500 }
object detalleFactura1 { idDetalle: 1 cantidad: 1 subtotal: 500 }
object detalleFactura2 { idDetalle: 2 cantidad: 1 subtotal: 3000 }
object inventario1 { idInventario: 1 cantidad: 10 }
object inventario2 { idInventario: 2 cantidad: 5 }
usuario1 – factura1 : realiza > factura1 – detalleFactura1 : contiene > factura1 – detalleFactura2 : contiene > detalleFactura1 – producto1 : incluye >
detalleFactura2 – producto2 : incluye > producto1 – inventario1 : controla >
producto2 – inventario2 : controla >
@enduml
![diagrama](/diagrama_estructural/diagrama_componentes/diagrama.png)