# limesurvey-6


Lokaal aan de praat krijgen van de versie 6 van de LimeSurvey stack voor HuC-DI en mogelijk SPAQ.

https://manual.limesurvey.org/LimeSurvey_roadmap#General

Support voor verise 5 sis gestopt in mei 2023 volgens de roadmap.

6.4. is in december gelanceerd. Nu is er 6.6.

Van de volgende docker repo wordt gebruik gemaakt:

https://github.com/adamzammit/limesurvey-docker

Op de Docker Hub te vinden onder:

https://registry.hub.docker.com/r/adamzammit/limesurvey

Let op: verschil in docker-compose op beide.


    docker compose up -d
    http://localhost:8082/admin/

Troubleshoot

In ieder geval op een Mac. Een aantal keer de 4 gedefinieerde bind volumes volledige permissies geven.
    
    docker compose up 
    chmod -R 777 config
    chmod -R 777 plugins/
    chmod -R 777 sessions/
    chmod -R 777 upload/

Afhankelijk van de meldingen in de LimeSurvey logs, een paar keer herhalen.
Geen idee waarom dat moet, niets over kunnen vinden 