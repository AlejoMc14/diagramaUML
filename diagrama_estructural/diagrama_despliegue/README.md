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
@startuml
node Cliente { [Navegador Web] –> ServidorApp }
node ServidorApp { [Sistema Carrito de Compras] Sistema –> Servidor : consultas SQL }
node Servidor { [Base de Datos] }
@enduml
![diagrama](/diagrama_estructural/diagrama_despliegue/diagrama.png)