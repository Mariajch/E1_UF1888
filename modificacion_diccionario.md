# Modificacion del diccionario de datos 

## Objetivo creado

Ampliar la informacion de los clientes para
permitir su clasificacion comercial mediante
campos personalizados.

## Modelo modificado

- Nombre funcional: Contactos / Clientes
- Modelo Odoo: res.partner
- Tabla PostgreSQL: res_partner

## Campos personalizados

### Nivel de cliente

- Nombre tecnico: x_nivel_cliente
- Tipo de campo: Seleccion
- Finalidad: Clasificar comercialmente al cliente.

### Segmento comercial

- Nombre tecnico: x_segmento_comercial_id
- Tipo de campo: Many2one
- Modelo relacionado: x_segmento_comercial
- Finalidad: Asociar cada cliente con un
  segmento de negocio.

## Modelo personalizado

- Nombre funcional: Segmento comercial
- Nombre tecnico: x_segmento_comercial
- Tabla PostgreSQL: x_segmento_comercial

Campos principales:
- id
- x_name
- x_codigo
- x_descripcion

## Modificacion de la vista

Se creo una vista heredada del formulario
res.partner.form para mostrar los campos
Nivel de cliente y Segmento comercial.

## Resultado

Se modifico el cliente Academia Teide Formacion,
asignandole:

- Nivel de cliente: Preferente
- Segmento comercial: Educacion

## 5. Evidencias de la modificacion

### Captura 1. Modelo Segmento comercial

![Modelo Segmento comercial](<captura/modelo Segmento comercial en Odoo.png>)

### Captura 2. Campos personalizados

![Campo Nivel de cliente](<captura/campo Nivel de cliente configurado.png>)

### Captura 3. Vista heredada

![Vista heredada de Contactos](<captura/vista heredada del formulario de Contactos.png>)

### Captura 4. Cliente modificado

![Academia Teide Formacion](<captura/04_cliente_modificado.png>)

### Creación del menú y mejora del formulario

Se creó una acción de ventana llamada "Segmentos comerciales",
asociada al modelo x_segmento_comercial.

Se añadió el menú "Segmentos comerciales" dentro de Contactos.

También se modificó la vista x_segmento_comercial.form
para mostrar los campos Nombre, Código y Descripción.

Se comprobó su funcionamiento abriendo el segmento
Educación, con código EDU001 y su descripción correspondiente.

![Formulario de segmento comercial](captura/08_formulario_segmento_comercial.png)







