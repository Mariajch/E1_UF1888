
## Identificacion de modelos y tablas

### res.partner

- Nombre funcional: Contacto / Cliente
- Modelo de Odoo: res.partner
- Tabla PostgreSQL asociada: res_partner
- Campos principales: id, name, email, phone, company_id
- Clave primaria: id
- Principales claves ajenas: company_id, country_id, user_id
- Relaciones con otros objetos:
  - country_id -> res.country
  - user_id -> res.users
  - sale.order_id -> res.partner_id
  - Campos personalizados añadidos:
  - x_nivel_cliente: campo de seleccion para clasificar clientes.
  - x_segmento_comercial_id: campo many2one que relaciona el cliente con x_segmento_comercial.
- Relacion personalizada:
  - x_segmento_comercial_id -> x_segmento_comercial.id

### product.product

- Nombre funcional: Variante de producto 
- Modelo de Odoo: product.product
- Tabla PostgreSQL asociada: product_product
- Campos principales: id, product_tmpl_id, barcode, active
- Clave primaria: id
- Principales claves ajenas: product_tmpl_id
- Relaciones con otros objetos:
  - product_tmpl_id -> product.template
  - id -> sale.order.line (mediante product_id)

### sale.order

- Nombre funcional: Pedido de venta
- Modelo de Odoo: sale.order
- Tabla PostgreSQL asociada: sale_order
- Campos principales: id, name, date_order, partner_id
- Clave primaria: id
- Principales claves ajenas:
  - partner_id
  - partner_invoice_id
  - user_id
- Relaciones con otros objetos:
  - partner_id -> res.partner
  - user_id -> res.users
  - id -> sale.order.line (mediante order_id)

### sale.order.line

- Nombre funcional: Linea de pedido de venta
- Modelo de Odoo: sale.order.line
- Tabla PostgreSQL asociada: sale_order_line
- Campos principales:
  - id
  - order_id
  - product_id
  - product_uom_qty
  - price_unit
- Clave primaria: id
- Principales claves ajenas:
  - order_id
  - product_id
- Relaciones con otros objetos:
  - order_id -> sale.order
  - product_id -> product.product

### x_segmento_comercial

- Nombre funcional: Segmento comercial
- Modelo de Odoo: x_segmento_comercial
- Tabla PostgreSQL asociada: x_segmento_comercial
- Campos principales:
  - id
  - x_name
  - x_codigo
  - x_descripcion
- Clave primaria: id
- Relaciones con otros objetos:
- res.partner.x_segmento_comercial_id -> x_segmento_comercial.id
 
  