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
´´´sql @startuml package “Sistema Carrito de Compras” {
class Usuario { +id: Integer +nombre: String +email: String +password: String
+rol: String +agregarProducto(): void +comprar(): void }
class Producto { +id: Integer +nombre: String +descripcion: String +precio:
Float +stock: Integer }
class Inventario { +id: Integer +cantidad: Integer +fechaActualizacion: Date
+actualizarStock(): void }
class Factura { +id: Integer +fecha: Date +total: Float +generarFactura():
void }
class DetalleFactura { +id: Integer +cantidad: Integer +subtotal: Float }
Usuario – Factura : “Crea” Usuario – Producto : “Elige” Producto – Inventario :
“va a” Factura – DetalleFactura : “contiene” DetalleFactura – Producto : “trata
de” }
@enduml
![diagrama](/diagrama_estructural/diagrama_paquete/diagrama.png)