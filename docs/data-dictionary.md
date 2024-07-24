---
sidebar_position: 7
---

# Diccionario de datos

## Usuarios

| Restricción       | Columna      | Tipo de dato      | Descripción      | Ejemplo      |
| -------------- | --------- | --------- | --------- | --------- |
| PK           | user_id |  `int`  | Numero de identificación para usuario | 1/2/3/4/5 ...|
| FK           | id_rol  |  `int`  | Numero de identificación para roles   | 1/2/3/4/5 ...| 
|              | username  |  `str`  | Apodo del usuario   | osmarmora05   |
|              | correo  |  `str`  | Correo electrónico   | osmarmora05@gmail.com   |
|              | contraseña  |  `str`  | Contraseña del usuario (puede ser distinta del correo)   | contraseña123  |
|              | cedula  |  `str`  | Cedula  | 451-170284-0000M  |
|              | telefono  |  `int`  | Numero de telefono del usuario  | 87333221  |
|              | nombre  |  `str`  | Nombre del usuario  | Paquito Jimmy Simpson Morty  | 

## Roles

| Restricción       | Columna      | Tipo de dato      | Descripción      | Ejemplo      |
| -------------- | --------- | --------- | --------- | --------- |
| PK           | id_rol |  `int`  | Numero de identificación para roles | 1/2/3/4/5 ...|
|              | nombre  |  `str`  | Nombre de roles   | supervisor / bodegero / cajero / admin / cliente | 

## Pedidos

| Restricción       | Columna      | Tipo de dato      | Descripción      | Ejemplo      |
| -------------- | --------- | --------- | --------- | --------- |
| PK           | pedidos_id |  `int`  | Numero de identificación para pedidos | 1/2/3/4/5 ...|
| FK           | user_id  |  `int`  | Numero de identificación para usuario   | 1/2/3/4/5 ... | 
|              | subtotal  |  `int`  | Es la suma total de precio x la cantida de zapatos antes de aplicar cualquier impuesto   | 1000 |
|              | total  |  `int`  | Es la suma total de precio x la cantida de zapatos en el que ya se incluyen impuestos.    | 1000 |
|              | estado  |  `str`  | Indica si el pedido ya fue entregado o aun sigue pendiente.    | Entregado / pendiente | 

## Movimientos

| Restricción       | Columna      | Tipo de dato      | Descripción      | Ejemplo      |
| -------------- | --------- | --------- | --------- | --------- |
| PK           | movimiento_id |  `int`  | Numero de identificación para movimientos | 1/2/3/4/5 ...|
| FK           | pedido_id  |  `int`  | Numero de identificación para pedidos   | 1/2/3/4/5 ... |
| FK           | modelo_id  |  `int`  | Numero de identificación para modelos   | 1/2/3/4/5 ... |
| FK           | usuario_id  |  `int`  | Numero de identificación para usuarios   | 1/2/3/4/5 ... |
|              | talla  |  `int`  | Numero de talla del calzado   | 1/2/3/4/5/12 ... |
|              | color  |  `str`  | Color predominante del calzado   | rojo / verde ... |
|              | cantidad  |  `int`  | Cantidad del zapato   | 5/21/3/1 ... |
|              | tipo-movimiento  |  `str`  | Describe cuando un zapato ha entrado a la tienda o cuando ha salido (un pedido/venta)   | entrada / salida |

## Inventario

| Restricción       | Columna      | Tipo de dato      | Descripción      | Ejemplo      |
| -------------- | --------- | --------- | --------- | --------- |
| PK           | inventario_id |  `int`  | Numero de identificación para inventario | 1/2/3/4/5 ...|
| FK           | modelo_id  |  `int`  | Numero de identificación para modelos   | 1/2/3/4/5 ... |
|              | talla  |  `int`  | Numero de talla del calzado   | 1/2/3/4/5/12 ... |
|              | color  |  `str`  | Color predominante del calzado   | rojo / verde ... |
|              | cantidad  |  `int`  | Cantidad del zapato   | 5/21/3/1 ... |
|              | imagen  |  `img`  | Imagén del zapato   | https://placehold.co/600x400 |

## Modelos


| Restricción       | Columna      | Tipo de dato      | Descripción      | Ejemplo      |
| -------------- | --------- | --------- | --------- | --------- |
| PK           | modelo_id  |  `int`  | Numero de identificación para modelos   | 1/2/3/4/5 ... |
| FK           | catalogo_id  |  `int`  | Numero de identificación para catalogo   | 1/2/3/4/5 ... |
|              | modelo       |  `str`  | Cadena que contiene una patron que brinda la empresa de dicho zapato   | CD7069-001 |
|              | tallas       |  `array[int]`  | Conjunto de datos que contiene una o varias tallas del zapato   | [1,2,3,12] |
|              | colores       |  `array[str]`  | Conjunto de datos que contiene una o varios colores del zapato    | ["rojo", "verder"] |
|              | imagenes       |  `array[img]`  | Conjunto de datos que contiene una o varias imágenes del zapato.   | ["https://placehold.co/600x400", "https://placehold.co/600x400"] |
|              | precio  |  `int`  | Numero que representa el precio del calzado   | 1000 |


## Catalogo

| Restricción       | Columna      | Tipo de dato      | Descripción      | Ejemplo      |
| -------------- | --------- | --------- | --------- | --------- |
| PK           | catalogo_id |  `int`  | Numero de identificación para catalogo | 1/2/3/4/5 ...|
| FK           | user_id  |  `int`  | Numero de identificación para usuario   | 1/2/3/4/5 ... |
| FK           | categoria_id  |  `int`  | Numero de identificación para categorias   | 1/2/3/4/5 ... |
| FK           | marca_id  |  `int`  | Numero de identificación para marcas   | 1/2/3/4/5 ... |
|              | nombre       |  `str`  | Nombre del zapato   | Air Jordan Legacy 312 Low |
|              | descripcion       |  `str`  | Descripción del zapato   | Un clásico, remasterizado. Este AJ1 equilibra el amarillo ocre y el negro con un fondo de cuero abatanado color vela para un acabado impecable y sofisticado. |

## Marca

| Restricción       | Columna      | Tipo de dato      | Descripción      | Ejemplo      |
| -------------- | --------- | --------- | --------- | --------- |
| PK           | marca_id |  `int`  | Numero de identificación para marca | 1/2/3/4/5 ...|
|              | nombre       |  `str`  | Nombre de la marca del zapato   | Nike |

## Categorías

| Restricción       | Columna      | Tipo de dato      | Descripción      | Ejemplo      |
| -------------- | --------- | --------- | --------- | --------- |
| PK           | categoria_id |  `int`  | Numero de identificación para categorías | 1/2/3/4/5 ...|
|              | nombre       |  `str`  | Nombre de la categoria del zapato   | Tenis |

## Empresa

| Restricción       | Columna      | Tipo de dato      | Descripción      | Ejemplo      |
| -------------- | --------- | --------- | --------- | --------- |
| PK           | id_empresa |  `int`  | Numero de identificación para empresa | 1/2/3/4/5 ...|
|              | nombre       |  `str`  | Nombre de la tienda   | Tenis |
|              | ruc       |  `str`  | Cadena que contiene una patron que representa aquellas personas naturales y/o sociedades, que sean titulares de bienes o derechos por los cuales deben pagar impuestos   | J0310000004340 |
|              | telefono       |  `int`  | Numero de telefono de la tienda   | 87333221 |
|              | direccion       |  `str`  | Localización de la tienda   | Del gindo a mano derecha, 3 cuadras hacia abajo |
|              | logo       |  `img`  | Imagén de la tienda   | https://placehold.co/600x400 |