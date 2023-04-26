# kc-mdb-adm_reset
Reset admin Keycloak account in mariadb server


``` 
select * from user_entity
delete from credential where user_id = '<user-id>';
delete from user_role_mapping where user_id = '<user-id>';
delete from user_entity where id = '<user-id>';
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

