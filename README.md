# PruebaPix
Prueba tecnica de pix

Contexto
Una empresa ficticia desea automatizar el análisis diario de productos disponibles en una tienda
online.
El proceso RPA debe realizar las siguientes tareas:
1. Obtener productos desde una API pública.
2. Guardar los datos originales y estructurados.
3. Almacenarlos en una base de datos.
4. Generar un reporte de Excel con estadísticas relevantes.
5. Subir ese reporte a OneDrive automáticamente.
6. Enviar el reporte a través de un formulario web.
7. Registrar evidencias del proceso.

Es necesario tener google chrome instalado y con la extensión de PIX RPA, tener MySQL y MySQL ODBC 9.4 Unicode y ANSI Driver en DNS Usuario y DNS de Sistema. No es necesario tener la base de datos previamente creada.

Proceso
1. Se iniciará el robot.
2. El robot cerrará los programas que puedan generar error y se conectará con la API para obtener los datos
3. Guardará esos datos en un .json
4. Se conectará a OneDrive mediante una carpeta vinculada (No por API por falta de licencias)
5. Se validará en OneDrive
6. Buscará la ruta '/RPA/Logs/Productos_YYYY-MM-DD.json en caso de no existir la ruta la creará.
7. Subirá el archivo .json con los datos.
8. Entrará a una base de datos en SQL Server.
9. Buscará la tabla 'productos' y en caso de no existir la creará bajo la estructura de id primary key-entero, title texto, price decimal, category texto, description texto, fecha_insercion fecha con registro de tiempo.
10. Extraerá los datos de id, title, price, category, description.
11. Obtendrá los datos ingresados y generará un excel llamado 'Reporte_YYYY-MM-DD.xlsx que se guardará en una carpeta llamada 'Reportes'
12. El excel tendrá dos hojas, en la hoja 1 todos los productos registrados en la base de datos, en la hoja 2 un resumen con el total de productos, el precio promedio general, precio promedio por categoria, cantidad de productos por categoria.
13. Subirá un reporte a una plataforma de formularios y llenará los campos solicitados.
14. Tomará una captura del formulario enviado y lo guardará como "Evidencia_(Fecha de el día tomada) y la subirá al onedrive en la ruta"\Evidencias\".

Dependencias:
System
System.IO
System.Collections
System.Linq
System.Data
System.Xml.Linq
Newtonsoft.Json.Linq
Newtonsoft.Json

Formulario = https://form.jotform.com/252248613636055