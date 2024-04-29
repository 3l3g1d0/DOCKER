# DOCKER

# Servidor de Correo con Docker

Este proyecto contiene la configuración necesaria para desplegar un servidor de correo electrónico utilizando `postfix` y `dovecot` en una imagen base de Ubuntu a través de Docker.

- Mantenido por: mail-c.stutreballs.es

Las variables de entorno predefinidas para la configuración de los servicios de correo son las siguientes:

- `POSTFIX_MAILNAME`: mail-c.stutreballs.es
- `DOVECOT_MAILNAME`: stutreballs.es
- `POSTGREY_MAX_AGE`: 35
- `POSTGREY_TEXT`: "Retrasado por Postgrey"
- `TZ`: Europe/Madrid

## Instalación y Despliegue

1. Descargar el Archivo.tar
2. docker load -i ruta/a/tu/archivo.tar
3. docker images
4. docker run -d --name mi-servidor-correo -p 25:25 -p 143:143 -p 587:587 -p 993:993 -p 995:995 nombre-de-la-imagen:etiqueta

## Volumenes

Los siguientes volúmenes se utilizan para almacenar datos persistentes:

- `/var/mail`: Almacenamiento de emails.
- `/var/lib/postfix`: Datos de operación de Postfix.
- `/var/lib/dovecot`: Datos de operación de Dovecot.
- `/etc/postfix`: Configuraciones de Postfix.
- `/etc/dovecot`: Configuraciones de Dovecot.

## Script de Inicio

El archivo `start-services.sh` se utiliza para iniciar los servicios de `postfix` y `dovecot` dentro del contenedor y para mantener el contenedor ejecutándose.





