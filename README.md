# _🖥️ CI_CD Docker (Jenkins - Prometheus - Grafana )_

## Description
<div style="text-align: justify;">
  I have made a pipeline where I put a simple script in Jenkins ( Hello-World ) to produce metrics, after that with Prometheus and some plugins, I get all the data needed to send to Grafana.
  
Grafana will make grafics, dashboard and so on, to have a better understanding of the data.

Everythings is under Docker 🐋, I have containerize all the services by using docker-compose who help me to manage multiple containers easily.
</div>
<p align="center">
  <img src="ReadMe-Pictures/PipelineCICD.jpg" alt="Description de l'image">
</p>


## Requirements
  - Docker on your host machine

## Installation

  1) You have first to execute the docker-compose with this command: ```sudo docker compose up -d```
