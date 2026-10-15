# Tienda-Keycaps-SQL
Base de datos MySQL de una tienda de keycaps: tablas, relaciones y consultas

Proyecto de practica, es una base de datos simulando una tienda de keycaps, con productos, clientes y ventas.

  La hice recordando el tiempo en el que vendia keycaps... :D

## Tablas
- **productos**: nombre, color, tipo, costo, precio de venta y stock.
- **clientes**: datos de cada cliente.
- **ventas**: cada compra, vinculada a un producto y a un cliente mediante claves foráneas.


  ## Consultas de ejemplo
-- Productos con poco stock
SELECT * FROM productos WHERE stock < 5;

-- Total vendido
SELECT SUM(valor_final) AS total_vendido FROM ventas;

-- Ventas con nombre de producto y cliente
SELECT ventas.id AS venta, productos.nombre AS producto, clientes.nombre AS cliente, ventas.valor_final
FROM ventas
JOIN productos ON ventas.producto_id = productos.id
JOIN clientes ON ventas.cliente_id = clientes.id;

## Herramientas
MySQL (XAMPP) y phpMyAdmin.
