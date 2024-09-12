# CHANGELOG


## 12-9-2024

- template trouble buttons deactiveren niet goed qua css

```html
    <div id="javatbd199996X1X4SQ002" class="bootstrap-buttons-div col-12 col-md-2 mb-1">
        <div class="form-check col-12 ">
        <input type="checkbox" name="199996X1X4SQ002" data-name="199996X1X4SQ002" class="btn-check button-item" id="answer199996X1X4SQ002" value="Y">
        <label for="answer199996X1X4SQ002" class="col-12 btn btn-primary ">nee</label>
        <input type="hidden" name="java199996X1X4SQ002" id="java199996X1X4SQ002" value="Y">
        </div>
    </div>
    
    <div id="javatbd199996X1X4SQ002" class="bootstrap-buttons-div col-12 col-md-2 mb-1">
        <div class="form-check col-12 ">
        <input type="checkbox" name="199996X1X4SQ002" data-name="199996X1X4SQ002" class="btn-check button-item" id="answer199996X1X4SQ002" value="Y">
        <label for="answer199996X1X4SQ002" class="col-12 btn btn-primary ">nee</label>
        <input type="hidden" name="java199996X1X4SQ002" id="java199996X1X4SQ002" value="">
        </div>
    </div>


```



## 29-8-2024

- template aanpassingen Bootstrap buttons, kleuren te weinig verschil normaal en geactiveerd

- oplossing: template extenden en het volgende in de custom.css stoppen

```css
    div.bootstrap-buttons-div .btn-primary {
        background-color: white;
        border: 1px solid #0f3e12;
        color: black; 
    }

```

## 22-8-2024

Nieuwe pogingb om aan de praat te krijgen. LimeSurvey permissie problemen. Gelukt met de laatste versie.
Er is wel een verandering gaande in deze Stack.

- acspri/limesurvey is nu
- adamzammit/limesurvey

Geprobeerd aan de praat te krijgen.


https://hub.docker.com/r/acspri/limesurvey 

is nu

https://registry.hub.docker.com/r/adamzammit/limesurvey

Dit is de github

https://github.com/adamzammit/limesurvey-docker

Verschillende docker-compose files...

Met die van Githuib lukte het uiteindelijk. 
Moest een paar keer alle permissies recursief aan de mackant bij de gedeelde Volumes goed zetten.
Steeds opstarten met `docker-compose up` en kijken welke directory nu weer opnieuw gezet moest worden.

    chmod -R 777 config
    chmod -R 777 config
    chmod -R 777 config
    chmod -R 777 config
    chmod -R 777 plugins/
    chmod -R 777 sessions/
    chmod -R 777 upload/
    chmod -R 777 upload/
    chmod -R 777 upload/
    
Zo zag de sessie eruit en toen start hij op..


## 14-2-2023

Ook met 3 geprobeerd werkt niet.


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