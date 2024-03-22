## Setup Sonarqube

- There many way to setup sonar cube like you can setup in local installation, you can setup in docker container or directly use sonar cloud.
- I am using Docker container for setup Sonarqube
- First you have to install docker then you can run the 
    ```sh
        docker compose up -d
    ```
- After this you can see service is running at port 9000 you can also change in docker.yml file.

## Download [SonarScanner CLI](https://docs.sonarsource.com/sonarqube/latest/analyzing-source-code/scanners/sonarscanner/)
- For Setup project you have to just read out the step mention in the sonarqube portal.
- And for running in local you have to run this cmd.

  ```sh
  sonar-scanner \
    -Dsonar.projectKey=<Project key> \
    -Dsonar.sources=. \
    -Dsonar.host.url=<sonar host url> \
    -Dsonar.login=<sonar token>
  ```

- You can also create ```sonar-project.properties``` file in your project and then you can run 
  ```sh
  sonar-scanner
  ```
- if you are maintaining the dir structure like ```build/sonarqube/sonar-project.properties``` then you have pass the complete path like this
  ```sh 
  sonar-scanner -Dproject.settings=sonar-project.properties -Dsonar.login=$SONAR_TOKEN"
  ```
- For security purpose you can set the token as env. variable like this ```export SONAR_TOKEN=sqp_eae3243636952159a245e2f5d1611e75881f1a1f``` or you can mention it into ```~/.zshrc``` or ```~/.bashrc``` file.

