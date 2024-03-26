# Laboratorio 6 

En este laboraotio nos centramos en el despliegue de apliaciones en Azure y todo lo que conlleva esta acción.

## Table of Contents

- [Integrantes](#integrantes)
- [Parte 1 - Despliegue App React en Azure](#parte-1---despliegue-app-react-en-azure)
- [Parte 2 - Ejercicio 1](#parte-2---ejercicio-1)
- [Parte 2 - Ejercicio 2](#parte-2---ejercicio-2)
- [Parte 2 - Ejercicio 3](#parte-2---ejercicio-3)
- [Links](#links)


## Integrantes

Joan S. Acevedo A.\
Miguel A. Gonzalez M.

## Parte 1 - Despliegue App React en Azure

A continuación vamos a ver el paso a paso a seguir para poder desplegar 
la aplicacion creada en el laboratorio anterior.

Primero creamos un budget de 1 dólar para la cuenta.

-imagen 1-

Posteriormente creamos una web estática.

-imagen 2-

Nos aseguramos de que la creación se haya ejecutado correctamente, para
esto nos vamos a la pestaña de "informacion general".

-imagen 4-

Después de verificar que todo está bien, procedemos a abrir la pagina 
para ver que se haya desplegado correctamente, damos click en "visitar sitio".

-imagen 5-

Observamos que se desplego correctamente! (Enlace en la sección [Links](#links)).

-imagen de la web app calculadora-

## Parte 2 - Ejercicio 1

Para poder desplegar la App web que estamos manejando, primero debemos
crear un grupo de recursos, para lo cual ingresamos el siguiente comando.

```bash
az group create --name recursosDeJoancito --location westus
```

-imagen 6-

Ahora creamos un App Service plan con el siguiente comando.

```bash
az appservice plan create --resource-group recursosDeJoancito --name planDeJoancito --sku F1
```

-imagen 7-

Finalmente se crea el servidor MySQL con el siguiente comando.

```bash
az account list-locations --query "[].{DisplayName:displayName, Name:name}" -o table # choose region
az configure --defaults location=eastus # set region
az mysql flexible-server create --resource-group recursosDeJoancito --name baseDeJoancito --admin-user joancito --admin-password P2ssw0rd123 --sku-name Standard_B1ms
```

-imagen 8-

-imagen 9-


## Parte 2 - Ejercicio 2

Procedemos a crear la apliación web. primero buscamos "Aplicación web":

-imagen 12-

Configuramos los datos necesarios.

-imagen 11-

Ahora revisamos y confirmamos la creación de la Aplicación web.

-imagen 13-

Posteriormente podemos observar la Aplicación web dirigiendonos a "Overviwe" -> "Browser".

-imagen 14-

A continuación actualizamos las cadenas de conexión para que 
la aplicación web se conecte correctamente a la base de datos.

-imagen 16-

## Parte 2 - Ejercicio 3

Ya en la parte final del laboratorio procedemos a apagar los servicios, 
nos conectamos con un cliente FTP y subimos el .jar de la aplicación Java.

-imagenes del winSCP-

-imagen de la app web-

## Links

- [App React](https://proud-forest-08979ed10.5.azurestaticapps.net)
- [App web](https://cvdsappweb2joan.azurewebsites.net)
