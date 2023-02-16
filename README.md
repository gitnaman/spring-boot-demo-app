# Spring-Boot Manual Installation

## Step-1

Perform the below step only when you launch a new ec2 instance. This command updates all the packages with latest version.

```bash
sudo yum update -y
```
```bash
sudo yum install git -y
```

## Step-2

Download the spring-boot application from repository at any specific location

```bash
sudo git clone https://github.com/TheCloudWorld/spring-boot-demo-app.git
```

## Step-3

Perform the below steps to install all the dependent packages

### Add Maven package into yum repository
```bash
sudo wget http://repos.fedorapeople.org/repos/dchen/apache-maven/epel-apache-maven.repo -O /etc/yum.repos.d/epel-apache-maven.repo
```
```bash
sudo sed -i s/\$releasever/6/g /etc/yum.repos.d/epel-apache-maven.repo
```
### Install Apache Maven package
```bash
sudo yum install -y apache-maven
```
### Install Java package
```bash
sudo yum install java-1.8.0-openjdk-devel.x86_64 -y

```

## Step-4

Build the Artifact

```bash
mvn clean install
```

## Step-5

You will get your ".jar" file in the target folder. Move the .Jar file to any specific application location, from where you want to run the application. Then perform the below step to run the application.

### Run the below command to launch spring-boot app
```bash
java -jar JAR_FILE_NAME.jar
```
"OR"
### Below command runs launches the spring-boot app as the background process
```bash
nohup java -jar JAR_FILE_NAME.jar > /dev/null 2>&1 &
```
