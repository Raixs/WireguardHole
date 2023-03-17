# Configuración de Pihole, Wireguard y DuckDNS con Docker Compose

Este repositorio de GitHub contiene un archivo de variables de entorno y un archivo de Docker Compose para usar Pihole, Wireguard y DuckDNS juntos. Esta configuración permite crear una VPN segura y privada, bloquear anuncios y rastreadores en todos los dispositivos conectados y tener una dirección IP pública en constante actualización mediante DuckDNS.

## Requisitos previos

-   Docker y Docker Compose deben estar instalados en el host.
- Una cuenta de DuckDNS.

## Configuración de variables de entorno

Antes de usar Docker Compose, debe crear un archivo `.env` en la raíz del directorio del proyecto y agregar las siguientes variables de entorno:

```
WG_HOST= # Dirección IP/DNS del servidor de Wireguard

WG_PASSWORD= # Contraseña del servidor de Wireguard 

PH_WEBPASSWORD= # Contraseña para acceder a la interfaz web de Pihole 

DD_SUBDOMAINS= # Subdominios de DuckDNS separados por coma

DD_TOKEN= # Token de DuckDNS
```

## Configuración de Docker Compose

El archivo de Docker Compose incluye los siguientes servicios:

-   **wg-easy**: servicio de Wireguard.
-   **pihole**: servicio de Pihole.
-   **nginx-proxy-manager**: servicio de Nginx Proxy Manager.
-   **duckdns**: servicio de DuckDNS.

Puede editar el archivo de Docker Compose según sus necesidades. Por ejemplo, si desea **habilitar el servicio de monitoreo** de Uptime Kuma, puede descomentar las líneas correspondientes.

## Uso de Docker Compose

Después de configurar las variables de entorno, puede ejecutar los servicios utilizando el siguiente comando:

`docker-compose up -d`

Este comando creará y ejecutará todos los contenedores necesarios en segundo plano. Puede detener los contenedores utilizando el siguiente comando:

`docker-compose down`

## Licencia

Este proyecto se distribuye bajo la licencia MIT. Consulte el archivo [LICENSE](https://chat.openai.com/LICENSE) para obtener más información.