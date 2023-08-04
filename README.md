# _🖥️ CI_CD Docker (Jenkins - Prometheus - Grafana )_

## 📚 Description
<div style="text-align: justify;">
  I have made a pipeline where I put a simple script in Jenkins ( Hello-World ) to produce metrics, after that with Prometheus and some plugins, I get all the data needed to send to Grafana.
  
Grafana will make grafics, dashboard and so on, to have a better understanding of the data.

Everythings is under Docker 🐋, I have containerize all the services by using docker-compose who help me to manage multiple containers easily.
</div>
<p align="center">
  <img src="ReadMe-Pictures/PipelineCICD.jpg" alt="Description de l'image">
</p>


## 🛠️ Requirements
  - 🐋 Docker on your host machine

## 🖱️ Installation

You have to execute inside the same folder of the _docker-compose.yml_, the docker-compose with the command: `sudo docker compose up -d`<br>
It will build the docker compose and create every containers of each services that are present inside the '_docker-compose.yml_'<br>
the '-d' is for _detached mode_ in docker, it will run all the containers in the background

  **After the command you will have access to differents webpages:**
  
  | Service     | URL                   |
  | ----------- | --------------------- |
  | Jenkins     | http://localhost:8080 |
  | Prometheus  | http://localhost:9090 |
  | Grafana     | http://localhost:3000 |

### Jenkins Configurations

Now you have access to Jenkins, you have to configure it.<br>
First connect to the page, it will ask for a password, you can have it by looking in the logs of the jenkins containers with these commands: <br>

  - `sudo docker ps` to see all the containers running, you need to get the _'Container ID'_ of Jenkins.
  - `sudo docker logs ['Container ID of Jenkins']` you will see the Jenkins password for the web page, copy and paste it in webpage

After the Jenkins's installation, you have to install a 'Prometheus plugins' call '_Promtheus Metric Exporter_'.

You will probably have to restart the container, I do `sudo docker compose stop` and `sudo docker compose up -d`

After that go back to Jenkins, you need to confirm in the System part, that Prometheus appear, if in the path there is _'\prometheus'_ so everything is good.
