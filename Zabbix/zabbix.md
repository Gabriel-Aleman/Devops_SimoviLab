| Componente | ¿Qué es? | ¿Qué hace? | ¿Con quién habla? | Runtime |
|---|---|---|---|---|
| **Server** | El cerebro central de Zabbix | Procesa datos, evalúa triggers, genera alertas y guarda todo en la base de datos | Agent (recibe métricas), DB (guarda datos), Frontend (expone info) | Proceso C corriendo como daemon, muy ligero, diseñado para alta concurrencia |
| **Agent** | Programa instalado en el host a monitorear | Recolecta métricas locales del host: CPU, RAM, disco, procesos, etc. y las envía al Server | Solo con el Server | Proceso C minimalista, consume muy poca RAM (~5 MB), corre en el host objetivo |
| **Frontend** | Interfaz web (PHP + Nginx) | Dashboard visual donde ves gráficas, configuras hosts, alertas y revisas el estado | DB (lee datos directamente), Server (acciones de config) | PHP 8+ sobre Nginx, requiere más recursos por ser una app web completa |


# Instalación de software:

# VS code (opcional):
    sudo apt update && sudo apt install -y wget gpg && \
    wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor | sudo tee /usr/share/keyrings/vscode.gpg > /dev/null && \
    echo "deb [arch=amd64 signed-by=/usr/share/keyrings/vscode.gpg] https://packages.microsoft.com/repos/code stable main" | sudo tee /etc/apt/sources.list.d/vscode.list > /dev/null && \
    sudo apt update && sudo apt install -y code

## Docker (ubuntu 24):
-   https://docs.docker.com/engine/install/ubuntu/

Agrega tu usuario al grupo docker:

        sudo usermod -aG docker $USER
## zabbix (ubuntu 24):
-   https://www.zabbix.com/download?zabbix=7.4&os_distribution=ubuntu&os_version=24.04&components=server_frontend_agent&db=pgsql&ws=nginx

![alt text](Imagenes/image.png)

    The default credentials for the Zabbix web interface are username Admin (case-sensitive, capital 'A') and password zabbix

## zabbix (Docker):

https://github.com/zabbix/zabbix-docker


    docker exec -it mi_contenedor bash

### Acceder a ruta zabbix: 
    cd /etc/zabbix/

## Postgres:
-   https://www.postgresql.org/download/linux/ubuntu/

# Docker compose:

## Zabbix