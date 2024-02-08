# CHANGELOG

## 8-2-2023

Naieve start met aangepaste werkende docker-compose file voor SPAQ. Containers starten niet op.

Na `docker ps -a | grep mysql` en `docker logs <#idcontainer>` zie ik de volgende error bij mariadb:


```
`2024-02-08 11:48:04+00:00 [Note] [Entrypoint]: Entrypoint script for MariaDB Server 1:10.11.6+maria~ubu2204 started.
2024-02-08 11:48:04+00:00 [Note] [Entrypoint]: Switching to dedicated user 'mysql'
2024-02-08 11:48:04+00:00 [Note] [Entrypoint]: Entrypoint script for MariaDB Server 1:10.11.6+maria~ubu2204 started.
2024-02-08 11:48:04+00:00 [Note] [Entrypoint]: Initializing database files
2024-02-08 11:48:04 0 [ERROR] mariadbd: Error writing file './ddl_recovery.log' (Errcode: 28 "No space left on device")
2024-02-08 11:48:04 0 [ERROR] Aborting
2024-02-08 11:48:04 0 [ERROR] mariadbd: Error on close of '(null)' (Errcode: 9 "Bad file descriptor")
```

en bij limesurvey6

`docker ps -a | grep limesurvey6` en `docker logs <#idcontainer>`

```
cp: setting permissions for 'application/config/rest': Permission denied
Copying default container default config files into config volume...
cp: cannot create regular file 'application/config/rest/v1.php': Permission denied
cp: cannot create directory 'application/config/rest/v1': Permission denied
cp: clearing permissions for 'application/config/rest': Permission denied

```

Werk aan de winkel dus permissie geklooi dus.