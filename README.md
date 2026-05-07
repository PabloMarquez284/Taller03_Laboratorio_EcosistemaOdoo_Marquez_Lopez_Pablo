# Laboratorio: Ecosistema Odoo
## PREPARACIÓN DEL ENTORNO
Primero he comprobado que los **contenedores** de **Odoo** y **Postgres-db** están en estado Running.
<img width="1069" height="88" alt="image" src="https://github.com/user-attachments/assets/948290c2-63f9-4c93-aaf8-0b168f1097a3" />

Luego he abierto una terminal integrada para dejar los **logs** corriendo mediante el comando ***docker logs \-f odoo***.  
<img width="1378" height="392" alt="image" src="https://github.com/user-attachments/assets/5c210f87-2901-45b5-9f49-956068074056" />


## FASE 1: Introducción de módulos
Esta primera fase consiste en crear una base de datos ficticia con datos implementados por el docente (exportándolos directamente a Odoo), crear un nuevo producto ("Audífonos Headset") y finalmente crear un presupuesto.
1\.   
He activado los módulos de **Ventas** e **Inventario** 
<img width="1918" height="318" alt="image" src="https://github.com/user-attachments/assets/cf023a5f-3485-4764-a6ce-61de32c73d2a" />

2\.   
Para no empezar la práctica con una base de datos vacía, he implementado los datos sintéticos implementados por el docente, en un archivo llamado ***clientes\_mock.csv****.*  
<img width="769" height="287" alt="image" src="https://github.com/user-attachments/assets/34de27b4-4b40-4915-a554-c88652216d94" />

Luego he instalado la extensión **Rainbow CSV** de **mechatroner**,lo que permite realizar lo necesario para luego poder exportar dicho archivo a odoo.  
<img width="915" height="464" alt="image" src="https://github.com/user-attachments/assets/247ae524-1a85-440d-b010-baf954a272b5" />

Cuando el archivo esté listo para su **exportación**, abro todo en la parte de ventas, pedidos, clientes e importo el archivo.
<img width="1919" height="941" alt="image" src="https://github.com/user-attachments/assets/1a2bce37-33eb-4962-894a-a50c64941dc4" />

Una vez me confirmó Odoo que está todo correcto, he dado las validación para que se **importe al completo**. 
<img width="1917" height="623" alt="image" src="https://github.com/user-attachments/assets/d7e5915f-5871-434f-b1ee-191c3b939ae8" />

3\.   
Antes de realizar una facturación, hay que crear un producto. Yo voy a crear el producto **“Audífonos Headset”.**  
<img width="949" height="804" alt="image" src="https://github.com/user-attachments/assets/3e15e530-7a77-4ebb-8eb2-06f71e33de30" />

Una vez creado el producto, creamos el **presupuesto**.  
<img width="930" height="759" alt="image" src="https://github.com/user-attachments/assets/7485c2f9-51b0-4eeb-8ce6-8bcff9d94838" />
<img width="1919" height="775" alt="image" src="https://github.com/user-attachments/assets/b07b2504-960f-49eb-8ef4-0828a82e1e8e" />

Por último, creamos y confirmamos dicha **factura**.
<img width="1919" height="946" alt="image" src="https://github.com/user-attachments/assets/6b503fc1-ca54-4b02-8882-b9f183107ace" />


## FASE 2: ELABORACIÓN DE INFORMES
Esta segunda fase consiste en modificar la plantilla **XML** original utilizando el motor de plantillas de Odoo, generando así informes.

1\.   
Al tener el **Modo Desarrollador activo**, he ido al apartado de vistas siguiendo esta dirección: Ajustes \> Técnico \> Interfaz de Usuario \> **Vistas** (Views).

2\.   
En la caja de búsqueda, he buscado **sale.report\_saleorder\_document** filtrando por **Clave** (Key) . Esta es la vista base que genera el esqueleto **HTML** que luego el motor wkhtmltopdf convierte a **PDF**.
<img width="1366" height="945" alt="image" src="https://github.com/user-attachments/assets/8b1ee368-381b-4cfd-b50c-eb807be3fd7b" />

3\.   
Una vez analizado el **código HTML**, me he ido al final, concretamente al último **\<div\>** y debajo he implementado el código dado por el docente.

4\.   
Después de **añadir** la parte del código, lo he guardado correctamente, sin **ningun mensaje de error**, quedando asi la parte final del HTML:  
<img width="1417" height="945" alt="image" src="https://github.com/user-attachments/assets/799895fe-b2ef-44b1-9a48-8ac708e9fa54" />
El HTML entero está subido en dicho repositorio.

5\.   
Finalmente, he imprimido como **“Presupuesto / Pedido”** el pedido que hice anteriormente. Dicho **PDF** está implementado en el repositorio.
