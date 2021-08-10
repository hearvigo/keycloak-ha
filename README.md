# keycloak-ha

## Supported tags and respective Dockerfile links
* [15.0.0, 15.0.0-mysql, latest](https://github.com/hearvigo/keycloak-ha/blob/master/15.0.0/mysql/Dockerfile)
* [15.0.0-postgres](https://github.com/hearvigo/keycloak-ha/blob/master/15.0.0/postgres/Dockerfile)
* [14.0.0, 14.0.0-mysql](https://github.com/hearvigo/keycloak-ha/blob/master/14.0.0/mysql/Dockerfile)
* [14.0.0-postgres](https://github.com/hearvigo/keycloak-ha/blob/master/14.0.0/postgres/Dockerfile)
* [13.0.1, 13.0.1-mysql](https://github.com/hearvigo/keycloak-ha/blob/master/13.0.1/mysql/Dockerfile)
* [13.0.1-postgres](https://github.com/hearvigo/keycloak-ha/blob/master/13.0.1/postgres/Dockerfile)
* [13.0.0, 13.0.0-mysql](https://github.com/hearvigo/keycloak-ha/blob/master/13.0.0/mysql/Dockerfile)
* [13.0.0-postgres](https://github.com/hearvigo/keycloak-ha/blob/master/13.0.0/postgres/Dockerfile)
* [12.0.4, 12.0.4-mysql](https://github.com/hearvigo/keycloak-ha/blob/master/12.0.4/mysql/Dockerfile)
* [12.0.4-postgres](https://github.com/hearvigo/keycloak-ha/blob/master/12.0.4/postgres/Dockerfile)
* [12.0.3, 12.0.3-mysql](https://github.com/hearvigo/keycloak-ha/blob/master/12.0.3/mysql/Dockerfile)
* [12.0.3-postgres](https://github.com/hearvigo/keycloak-ha/blob/master/12.0.3/postgres/Dockerfile)
* [12.0.2, 12.0.2-mysql](https://github.com/hearvigo/keycloak-ha/blob/master/12.0.2/mysql/Dockerfile)
* [12.0.2-postgres](https://github.com/hearvigo/keycloak-ha/blob/master/12.0.2/postgres/Dockerfile)
* [12.0.1, 12.0.1-mysql](https://github.com/hearvigo/keycloak-ha/blob/master/12.0.1/mysql/Dockerfile)
* [12.0.1-postgres](https://github.com/hearvigo/keycloak-ha/blob/master/12.0.1/postgres/Dockerfile)
* [12.0.0, 12.0.0-mysql](https://github.com/hearvigo/keycloak-ha/blob/master/12.0.0/mysql/Dockerfile)
* [12.0.0-postgres](https://github.com/hearvigo/keycloak-ha/blob/master/12.0.0/postgres/Dockerfile)
* [11.0.3, 11.0.3-mysql](https://github.com/hearvigo/keycloak-ha/blob/master/11.0.3/mysql/Dockerfile)
* [11.0.3-postgres](https://github.com/hearvigo/keycloak-ha/blob/master/11.0.3/postgres/Dockerfile)
* [11.0.2, 11.0.2-mysql](https://github.com/hearvigo/keycloak-ha/blob/master/11.0.2/mysql/Dockerfile)
* [11.0.2-postgres](https://github.com/hearvigo/keycloak-ha/blob/master/11.0.2/postgres/Dockerfile)
* [11.0.1, 11.0.1-mysql](https://github.com/hearvigo/keycloak-ha/blob/master/11.0.1/mysql/Dockerfile)
* [11.0.1-postgres](https://github.com/hearvigo/keycloak-ha/blob/master/11.0.1/postgres/Dockerfile)
* [11.0.0, 11.0.0-mysql](https://github.com/hearvigo/keycloak-ha/blob/master/11.0.0/mysql/Dockerfile)
* [11.0.0-postgres](https://github.com/hearvigo/keycloak-ha/blob/master/11.0.0/postgres/Dockerfile)
* [10.0.2, 10.0.2-mysql](https://github.com/hearvigo/keycloak-ha/blob/master/10.0.2/mysql/Dockerfile)
* [10.0.2-postgres](https://github.com/hearvigo/keycloak-ha/blob/master/10.0.2/postgres/Dockerfile)
* [10.0.1, 10.0.1-mysql](https://github.com/hearvigo/keycloak-ha/blob/master/10.0.1/mysql/Dockerfile)
* [10.0.1-postgres](https://github.com/hearvigo/keycloak-ha/blob/master/10.0.1/postgres/Dockerfile)
* [10.0.0, 10.0.0-mysql](https://github.com/hearvigo/keycloak-ha/blob/master/10.0.0/mysql/Dockerfile)
* [10.0.0-postgres](https://github.com/hearvigo/keycloak-ha/blob/master/10.0.0/postgres/Dockerfile)
* [9.0.3, 9.0.3-mysql](https://github.com/hearvigo/keycloak-ha/blob/master/9.0.3/mysql/Dockerfile)
* [9.0.3-postgres](https://github.com/hearvigo/keycloak-ha/blob/master/9.0.3/postgres/Dockerfile)
* [9.0.2, 9.0.2-mysql](https://github.com/hearvigo/keycloak-ha/blob/master/9.0.2/mysql/Dockerfile)
* [9.0.2-postgres](https://github.com/hearvigo/keycloak-ha/blob/master/9.0.2/postgres/Dockerfile)
* [9.0.0, 9.0.0-mysql](https://github.com/hearvigo/keycloak-ha/blob/master/9.0.0/mysql/Dockerfile)
* [9.0.0-postgres](https://github.com/hearvigo/keycloak-ha/blob/master/9.0.0/postgres/Dockerfile)

## Use MySQL
### Run keycloak1
```
docker run -d --name keycloak1 --restart=always \
    -p 8080:8080 \
    -p 8443:8443 \
    -p 8009:8009 \
    -p 9990:9990 \
    -p 7600:7600 \
    -p 57600:57600 \
    -e KEYCLOAK_USER=admin \
    -e KEYCLOAK_PASSWORD=admin \
    -e DB_VENDOR=mysql \
    -e DB_ADDR=localhost \
    -e DB_PORT=3306 \
    -e DB_DATABASE=keycloak \
    -e DB_USER=keycloak \
    -e DB_PASSWORD=password \
    -e JGROUPS_DISCOVERY_PROTOCOL=JDBC_PING \
    -e JGROUPS_DISCOVERY_EXTERNAL_IP=172.31.72.101 \
    -e PROXY_ADDRESS_FORWARDING=true \
    -e KEYCLOAK_FRONTEND_URL=https://your-domain/auth \
    vigoz/keycloak-ha:10.0.2
```

### Run keycloak2
```
docker run -d --name keycloak2 --restart=always \
    -p 8080:8080 \
    -p 8443:8443 \
    -p 8009:8009 \
    -p 9990:9990 \
    -p 7600:7600 \
    -p 57600:57600 \
    -e KEYCLOAK_USER=admin \
    -e KEYCLOAK_PASSWORD=admin \
    -e DB_VENDOR=mysql \
    -e DB_ADDR=localhost \
    -e DB_PORT=3306 \
    -e DB_DATABASE=keycloak \
    -e DB_USER=keycloak \
    -e DB_PASSWORD=password \
    -e JGROUPS_DISCOVERY_PROTOCOL=JDBC_PING \
    -e JGROUPS_DISCOVERY_EXTERNAL_IP=172.31.72.102 \
    -e PROXY_ADDRESS_FORWARDING=true \
    -e KEYCLOAK_FRONTEND_URL=https://your-domain/auth \
    vigoz/keycloak-ha:10.0.2
```

### MySQL Configuration
If you got error `Table 'keycloak.client_session' doesn't exist` when keycloak start up with MySQL, you should change MySQL's `lower_case_table_names` config to `1`
```
lower_case_table_names=1
```

## Use PostgreSQL
### Run keycloak1
```
docker run -d --name keycloak1 --restart=always \
    -p 8080:8080 \
    -p 8443:8443 \
    -p 8009:8009 \
    -p 9990:9990 \
    -p 7600:7600 \
    -p 57600:57600 \
    -e KEYCLOAK_USER=admin \
    -e KEYCLOAK_PASSWORD=admin \
    -e DB_VENDOR=postgres \
    -e DB_ADDR=localhost \
    -e DB_PORT=5432 \
    -e DB_DATABASE=keycloak \
    -e DB_SCHEMA=public \
    -e DB_USER=keycloak \
    -e DB_PASSWORD=password \
    -e JGROUPS_DISCOVERY_PROTOCOL=JDBC_PING \
    -e JGROUPS_DISCOVERY_EXTERNAL_IP=172.31.72.101 \
    -e PROXY_ADDRESS_FORWARDING=true \
    -e KEYCLOAK_FRONTEND_URL=https://your-domain/auth \
    vigoz/keycloak-ha:10.0.2-postgres
```

### Run keycloak2
```
docker run -d --name keycloak2 --restart=always \
    -p 8080:8080 \
    -p 8443:8443 \
    -p 8009:8009 \
    -p 9990:9990 \
    -p 7600:7600 \
    -p 57600:57600 \
    -e KEYCLOAK_USER=admin \
    -e KEYCLOAK_PASSWORD=admin \
    -e DB_VENDOR=postgres \
    -e DB_ADDR=localhost \
    -e DB_PORT=5432 \
    -e DB_DATABASE=keycloak \
    -e DB_SCHEMA=public \
    -e DB_USER=keycloak \
    -e DB_PASSWORD=password \
    -e JGROUPS_DISCOVERY_PROTOCOL=JDBC_PING \
    -e JGROUPS_DISCOVERY_EXTERNAL_IP=172.31.72.102 \
    -e PROXY_ADDRESS_FORWARDING=true \
    -e KEYCLOAK_FRONTEND_URL=https://your-domain/auth \
    vigoz/keycloak:10.0.2-postgres
```