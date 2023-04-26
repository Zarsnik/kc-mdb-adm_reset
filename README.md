# kc-mdb-adm_reset
Reset admin Keycloak account in mariadb server


``` 
mysql -u root -p
USE keycloak;
select * from USER_ENTITY;
delete from CREDENTIAL where USER_ID = '<user-id>';
delete from USER_ROLE_MAPPING where USER_ID = '<user-id>';
delete from USER_ENTITY where ID = '<user-id>';
```


Unclean method :

```
mysql -u root -p
USE keycloak;
TRUNCATE TABLE CREDENTIAL;
TRUNCATE TABLE USER_ROLE_MAPPING;
SET FOREIGN_KEY_CHECKS = 0; 
TRUNCATE TABLE USER_ENTITY; 
SET FOREIGN_KEY_CHECKS = 1;
```

