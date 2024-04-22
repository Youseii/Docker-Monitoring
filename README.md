# _🖥️ CI_CD Docker (Jenkins - Prometheus - Grafana )_

## 📚 _Description_
<div style="text-align: justify;">
  I've made a pipeline where I put a simple script in Jenkins ( Hello-World ) to produce metrics, after that with Prometheus and some plugins, I get all the data needed to send to Grafana.
  
Grafana will make grafics, dashboard and so on, to have a better understanding of the data.

Everything is under Docker 🐋, I have containerize all the services by using docker-compose who help me to manage multiple containers easily.
</div>
<p align="center">
  <img src="ReadMe-Pictures/PipelineCICD.jpg" alt="Description de l'image">
</p>


## 🛠️ _Requirements_
  - 🐋 Docker on your host machine

## 🖱️ _Installation_

You have to execute inside the same folder of the _docker-compose.yml_, the docker-compose with the command: `sudo docker compose up -d`.<br>
It will build the docker compose and create every containers of each services that are present inside the '_docker-compose.yml_'.<br>
the '-d' is for _detached mode_ in docker, it will run all the containers in the background.

  **After the command you will have access to differents webpages:**
  
  | Service     |                 URL                 |
  | ----------- | ----------------------------------- |
  | Jenkins     | http://localhost:8080               |
  | Metrics     | http://localhost:8080/prometheus    |
  | Prometheus  | http://localhost:9090               |
  | Grafana     | http://localhost:3000               |

## _Jenkins Configurations_

Now you have access to Jenkins, you have to configure it.<br>
First connect to the page, it will ask for a password, you can have it by looking in the logs of the jenkins containers with these commands: <br>

  - `sudo docker ps` to see all the containers running, you need to get the _'Container ID'_ of Jenkins.
  - `sudo docker logs ['Container ID of Jenkins']` you will see the Jenkins password for the web page, copy and paste it in webpage

After the Jenkins's installation, you have to install a 'Prometheus plugins' call '_Promtheus Metric Exporter_'.

You will probably have to restart the container, I do `sudo docker compose stop` and `sudo docker compose up -d`

After that go back to Jenkins, you need to confirm in the System part, that Prometheus plugin is installed correctly, you can check by adding in the url of jenkins  _'\prometheus'_  if you have a webpage with some metrics or weird information, it means that everything is good ! 

Create a simple pipeline with a Hello-world script to build for testing purpose.

## _Prometheus_

In Prometheus, you have to check if the target is up, you can see that in '_status_' and '_targets_'. ( Check the URL part at the start of the ReadMe )
</div>
<p align="center">
  <img src="ReadMe-Pictures/target.png" alt="Description de l'image">
</p>

## _Grafana_

By default Grafana give admin and *admin* as *username* and *password*, you will have to change it for the first time connection.

_To create your own datasource_:
  * Create a datasource --> In Dashboards - new Dashboards - Add visualization - configure new data source
  * Choose Prometheus and add the prometheus URL server ( http://prometheus:9090 ) change configuration as you need and save it at the end

_To create you own dashboards_:
  * In Dashboards - new Dashboards - Add visualization - choose the data source created previously
  * Select metrics that you want to display in the _Query tab_, next is to run the Query to display it

</div>
<p align="center">
  <img src="ReadMe-Pictures/grafana.PNG" alt="Description de l'image">
</p>

## _ERRORS_

If you have trouble during the installation, here some things that occurs during the project:

  * Proxy errors on Jenkins that block you to do configuration, script and so on... You have to enable the CRSF proxy compatibility in the security settings.
</div>
<p align="center">
  <img src="ReadMe-Pictures/CRSF.PNG" alt="Description de l'image">
</p>
