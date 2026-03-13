| Componente | ¿Qué es? | ¿Qué hace? | ¿Con quién habla? | Runtime |
|---|---|---|---|---|
| **Server** | El cerebro central de Zabbix | Procesa datos, evalúa triggers, genera alertas y guarda todo en la base de datos | Agent (recibe métricas), DB (guarda datos), Frontend (expone info) | Proceso C corriendo como daemon, muy ligero, diseñado para alta concurrencia |
| **Agent** | Programa instalado en el host a monitorear | Recolecta métricas locales del host: CPU, RAM, disco, procesos, etc. y las envía al Server | Solo con el Server | Proceso C minimalista, consume muy poca RAM (~5 MB), corre en el host objetivo |
| **Frontend** | Interfaz web (PHP + Nginx) | Dashboard visual donde ves gráficas, configuras hosts, alertas y revisas el estado | DB (lee datos directamente), Server (acciones de config) | PHP 8+ sobre Nginx, requiere más recursos por ser una app web completa |


## Repositorio:

    https://github.com/zabbix/zabbix-docker


### Bibliografía:
---
