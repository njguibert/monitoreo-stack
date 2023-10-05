# 

# Stack de monitoreo básico útilizando Zabbix/Grafana


<img src="../assets/images/environment-alpha/intro.gif" width="80%">

**Índice**

1. [Descripción](#descrip)
2. [Accesos y credenciales](#acc)
3. [Problemas conocidos](#knowerr)
 

## Descripción<a name="descrip"></a>

Este repositorio tiene los manifiestos necesarios para crear un stack de monitoreo útilizando docker compose, utilizando los siguientes microservicios:

1. zabbix/zabbix-server-mysql
2. zabbix/zabbix-web-apache-mysql
3. zabbix/zabbix-web-nginx-mysql
4. zabbix/zabbix-agent
5. zabbix/zabbix-web-service
6. mysql:8.0-oracle
7. busybox
8. postgres
9. grafana/grafana
10. redis

![a!](../assets/images/environment-alpha/1.png "logo") 

## Accesos y credenciales<a name="acc"></a>

Las credenciales para cada servicio son:

Credencial Zabbix
```
User: Admin
Password: zabbix
```

Credencial Grafana
```
User: admin
Password: zabbix
```

## Problemas conocidos<a name="knowerr"></a>

### 1. Error de permisos al iniciar Grafana:

![a!](../assets/images/environment-alpha/1_err.png "logo") 

En el directorio del repositorio ejecutar:
```
sudo chown -R $USER:$USER grafana/
```

### 2. Zabbix server RED Availability:

![a!](../assets/images/environment-alpha/2_err.png "logo") 

Como estamos ejecutando el stack en contenedores, no existe la ip 127.0.0.1 , se deberá de cambiar el tipo de interfaz a DNS name: zabbix-agent

![a!](../assets/images/environment-alpha/2.png "logo") 