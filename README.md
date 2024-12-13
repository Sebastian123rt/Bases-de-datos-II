# Bases-de-datos-II
SISTEMA DE E-COMMERCE CON MONGO DB
# Sistema de E-Commerce con MongoDB

Este proyecto implementa un sistema de base de datos para un e-commerce, utilizando MongoDB. Incluye colecciones para gestionar productos, categorías, usuarios, carritos de compras y órdenes.

## Estructura de la Base de Datos

### 1. Colecciones
- *products*: Información de los productos.
- *categories*: Clasificación de productos.
- *users*: Detalles de los clientes y administradores.
- *cart*: Carritos de compras de los usuarios.
- *orders*: Órdenes generadas por los usuarios.

### 2. Campos por Colección

#### *products*
- nombre (string): Nombre del producto.
- descripcion (string): Detalle del producto.
- precio (float): Precio unitario.
- imagen (string): URL de la imagen del producto.
- categoria (string): Categoría del producto (relacionado con categories).
- stock (integer): Cantidad disponible.

#### *categories*
- nombre (string): Nombre de la categoría.
- descripcion (string): Descripción de la categoría.

#### *users*
- nombre (string): Nombre completo del usuario.
- correo (string): Dirección de correo electrónico.
- direccion (string): Dirección física.
- telefono (string): Número de contacto.
- rol (string): Cliente o administrador.
- fecha_registro (date): Fecha de registro en el sistema.

#### *cart*
- id_usuario (string): Identificador del usuario.
- productos (array):
  - id_producto (string): ID del producto.
  - cantidad (integer): Cantidad añadida al carrito.

#### *orders*
- id_usuario (string): Identificador del usuario.
- productos (array):
  - id_producto (string): ID del producto.
  - cantidad (integer): Cantidad comprada.
- estado (string): Estado de la orden (pendiente, pagado, enviado).
- total (float): Total de la orden.

---

## Configuración

### *Requisitos*
1. MongoDB instalado localmente o en la nube.
2. MongoDB Compass para visualizar la base de datos.
3. Node.js (si se va a integrar con una aplicación backend).

### *Importar las Colecciones*
1. Exporta las colecciones de MongoDB Compass en formato JSON.
2. Usa el comando mongoimport para cargar las colecciones:
   ```bash
   mongoimport --db nombre_base_datos --collection nombre_coleccion --file archivo.json --jsonArray
