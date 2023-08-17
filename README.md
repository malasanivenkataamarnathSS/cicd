# Spring Boot based Java web application
 
This is a simple Sprint Boot based Java application that can be built using Maven. Sprint Boot dependencies are handled using the pom.xml 
at the root directory of the repository.

This is a MVC architecture based application where controller returns a page with title and message attributes to the view.

## Execute the application locally and access it using your browser

Checkout the repo and move to the directory

```
git clone https://github.com/iam-veeramalla/Jenkins-Zero-To-Hero/java-maven-sonar-argocd-helm-k8s/sprint-boot-app
cd java-maven-sonar-argocd-helm-k8s/sprint-boot-app
```

Execute the Maven targets to generate the artifacts

```
mvn clean package
```

The above maven target stroes the artifacts to the `target` directory. You can either execute the artifact on your local machine
(or) run it as a Docker container.

** Note: To avoid issues with local setup, Java versions and other dependencies, I would recommend the docker way. **


### Execute locally (Java 11 needed) and access the application on http://localhost:8080

```
java -jar target/spring-boot-web.jar
```

### The Docker way

Build the Docker Image

```
docker build -t ultimate-cicd-pipeline:v1 .
```

```
docker run -d -p 8010:8080 -t ultimate-cicd-pipeline:v1
```

Hurray !! Access the application on `http://<ip-address>:8010`


## Next Steps

### Configure a Sonar Server locally

```
apt install unzip
adduser sonarqube
wget https://binaries.sonarsource.com/Distribution/sonarqube/sonarqube-9.4.0.54424.zip
unzip *
chmod -R 755 /home/sonarqube/sonarqube-9.4.0.54424
chown -R sonarqube:sonarqube /home/sonarqube/sonarqube-9.4.0.54424
cd sonarqube-9.4.0.54424/bin/linux-x86-64/
./sonar.sh start
```

Hurray !! Now you can access the `SonarQube Server` on `http://<ip-address>:9000` 


----------------------------------------------------------------------------------
    1 apt update
    2  apt install git maven -y
    3  sudo apt update
    4  sudo apt install openjdk-11-jre
    5  wget https://get.jenkins.io/war-stable/2.401.3/jenkins.war
    6  java -jar jenkins.war --httpPort=80
# after open jenkins in crome
    Docker:--
    1 apt install docker.io
    2 sudo su -
    3 usermod -aG docker jenkins
    4 usermod -aG docker ubuntu
    5 systemctl restart docker

after we need to install pulgin in jenkins server 
   -- docker pipeline (pulgin)
----------------------------------------------------------------------
    SonarQube:--
    apt install unzip
1 adduser sonarqube
2 wget https://binaries.sonarsource.com/Distribution/sonarqube/sonarqube-9.4.0.54424.zip
3 unzip *
4 chmod -R 755 /home/sonarqube/sonarqube-9.4.0.54424
5 chown -R sonarqube:sonarqube /home/sonarqube/sonarqube-9.4.0.54424
6 cd sonarqube-9.4.0.54424/bin/linux-x86-64/
7 ./sonar.sh start

 Now you can access the SonarQube Server on http://<ip-address>:9000

username -- admin
password -- admin

geneate access key 

for that first go to -- my account
                     -- click on security 
                     -- generate token
now we need to install sonar scanner pulign in jenkins.
after manage credentials -->system-->Global credentials-->kind(Secret text) --> Secret (past sonarqube access key) 
-->id (sonarqube)

same like we  need to add dockerhub username and password
--
userwithpassword
id --docker-cred 



