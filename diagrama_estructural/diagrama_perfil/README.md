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
´´´sql @startuml
package “Perfil de Sistema de Carrito de Compras” {
class Usuario <<Perfil>> {
+ idUsuario: int
+ nombre: String
+ rol: String
+ email: String
+ password: String
}
class Producto <<Perfil>> {
+ idProducto: int
+ nombre: String
+ descripcion: String
+ precio: float
}
class Inventario <<Perfil>> {
+ idInventario: int
+ cantidad: int
+ idProducto: int
}
class Factura <<Perfil>> {
+ idFactura: int
+ fecha: Date
+ total: float
+ idUsuario: int
}
1
class DetalleFactura <<Perfil>> {
+ idDetalleFactura: int
+ cantidad: int
+ subtotal: float
+ idFactura: int
+ idProducto: int
}
}
Usuario – Factura : crea Factura – DetalleFactura : contiene Producto – Inventario : está en Producto – DetalleFactura : incluye
@enduml
![diagrama](/diagrama_estructural/diagrama_perfil/diagrama.png)