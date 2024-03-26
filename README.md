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

![image](https://github.com/JoanAcevedo/Lab06-CVDS/assets/99531702/336a6f3b-967e-4344-a476-b7c9ccd46eb5)

Posteriormente creamos una web estática.

![image](https://github.com/JoanAcevedo/Lab06-CVDS/assets/99531702/e39dd7ee-83ec-4751-be20-c543fdba2f3d)

Nos aseguramos de que la creación se haya ejecutado correctamente, para
esto nos vamos a la pestaña de "informacion general".

![image](https://github.com/JoanAcevedo/Lab06-CVDS/assets/99531702/5e2a82cc-6e70-4175-9126-2317bd1fc083)

Después de verificar que todo está bien, procedemos a abrir la pagina 
para ver que se haya desplegado correctamente, damos click en "visitar sitio".

![image](https://github.com/JoanAcevedo/Lab06-CVDS/assets/99531702/3996ce5e-6782-4d16-9432-dde190957887)

Observamos que se desplego correctamente! (Enlace en la sección [Links](#links)).

![image](https://github.com/JoanAcevedo/Lab06-CVDS/assets/99531702/b0f918df-8d1c-4f49-b898-2d97a738d4d2)

## Parte 2 - Ejercicio 1

Para poder desplegar la App web que estamos manejando, primero debemos
crear un grupo de recursos, para lo cual ingresamos el siguiente comando.

```bash
az group create --name recursosDeJoancito --location westus
```

![image](https://github.com/JoanAcevedo/Lab06-CVDS/assets/99531702/adb6ea04-1921-48b7-9615-a44ca99101bf)

Ahora creamos un App Service plan con el siguiente comando.

```bash
az appservice plan create --resource-group recursosDeJoancito --name planDeJoancito --sku F1
```

![image](https://github.com/JoanAcevedo/Lab06-CVDS/assets/99531702/45e3ebf0-a80e-4340-8531-614ea00e4ade)

Finalmente se crea el servidor MySQL con el siguiente comando.

```bash
az account list-locations --query "[].{DisplayName:displayName, Name:name}" -o table # choose region
az configure --defaults location=eastus # set region
az mysql flexible-server create --resource-group recursosDeJoancito --name baseDeJoancito --admin-user joancito --admin-password P2ssw0rd123 --sku-name Standard_B1ms
```

![image](https://github.com/JoanAcevedo/Lab06-CVDS/assets/99531702/8d5b28f9-6252-4ae1-868d-c5791c4aa451)

![image](https://github.com/JoanAcevedo/Lab06-CVDS/assets/99531702/f3d2b9ea-ea9c-4c8a-a18f-72141bcace6b)

## Parte 2 - Ejercicio 2

Procedemos a crear la apliación web. primero buscamos "Aplicación web":

![image](https://github.com/JoanAcevedo/Lab06-CVDS/assets/99531702/d02ddc9a-ade6-4025-b34f-e1cbdb97fc07)

Configuramos los datos necesarios.

![image](https://github.com/JoanAcevedo/Lab06-CVDS/assets/99531702/2f26632b-e92f-4b64-a424-aab20fcbba64)

Ahora revisamos y confirmamos la creación de la Aplicación web.

![image](https://github.com/JoanAcevedo/Lab06-CVDS/assets/99531702/20caf006-0aab-43c1-b0aa-48a09bc9318f)

Posteriormente podemos observar la Aplicación web dirigiendonos a "Overviwe" -> "Browser".

![image](https://github.com/JoanAcevedo/Lab06-CVDS/assets/99531702/ad1638a1-28d6-415d-b99e-1bc545ad2ac8)

A continuación actualizamos las cadenas de conexión para que 
la aplicación web se conecte correctamente a la base de datos.

![image](https://github.com/JoanAcevedo/Lab06-CVDS/assets/99531702/8a8c765c-dfc2-4cb1-a07a-0dda27c34965)

## Parte 2 - Ejercicio 3

Ya en la parte final del laboratorio procedemos a apagar los servicios, 
nos conectamos con un cliente FTP y subimos el .jar de la aplicación Java.

![image](https://github.com/JoanAcevedo/Lab06-CVDS/assets/99531702/41f4af29-ae83-4aef-9ec0-8884234e0086)

![image](https://github.com/JoanAcevedo/Lab06-CVDS/assets/99531702/7da9c1b7-6322-4361-99f1-4f4739684325)

Finalmente podemos observar la Aplicación web.

![image](https://github.com/JoanAcevedo/Lab06-CVDS/assets/99531702/e5f012e9-53ba-4d87-bd87-e8de60fe5239)

## Links

- [App React](https://proud-forest-08979ed10.5.azurestaticapps.net)
- [App web](https://cvdsappweb2joan.azurewebsites.net)
