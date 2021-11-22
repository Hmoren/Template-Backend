# Template-Backend

# Template para el desarrollo de una API REST como backend utilizando Azure Functions o ASP.NET Core:

## Notas
- Arquitectura en 3 capas (API, l�gica de negocios, acceso a datos).
- Ejemplo de ASP.NET Core y Azure Functions compartiendo la misma arquitectura.
- Uso de interfaces e infecci�n de dependencias.
- Configuraci�n de CORS
- Swagger para la documentaci�n de la API 
- Estandariza la respuesta de las solicitudes haciendo un "envelop" con una clase Response.
- Ejemplo de acceso a los valores del appsetting.json (por ejemplo, acceder a la cadena de conexi�n en la capa de datos).
- Seperaci�n en capas (logica de negocios y acceso a datos)


## Para utilizar el entity framework
- Establecer el proyecto de SqlProvisiong como proyecto de inicio
- En VS, Tools, Nuget Package Manager abrir el Package Manager Console
- Seleccionar como ""Default project"" el de DataAccess (en la barra de la ventana)
- Escribir Add-Migration {nombre de la migraci�n} para agregar las migraciones (se van a crear en el proyecto de DataAccess)
- Escribir Update-Database para ejecutar las migraciones contra la base de datos


## Soporte de Swagger en Azure Function
- El soporte de OpenAPI (swagger) es a trav�s de esta [librer�a](https://www.nuget.org/packages/Microsoft.Azure.WebJobs.Extensions.OpenApi). 
- Es necesario agregar un archivo de configuraci�n con los detalles de la API (ver en Configuration/OpenApiOptions.cs). 
- Luego ade agregar los atributos necesarios a cada m�todo, al ejecutar la functi�n se genera un endpoint para ver la UI del swagger.


## Soporte de Swagger en ASP.NET Core
- Viene integrado como parte de Net 5, solo depende que se gener� el archivo XML de documentaci�n


## Pr�ximamente
- Migraci�n el template a NET 6.
- Incoporar proyectos de TEST y pipelines de cada caso (GitHub, DevOps)
- Ejemplo de Durable Function )no est� soportado en NET 5, lo agregaremos al template cuando migregrmos a NET 6).
