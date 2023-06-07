version: '3.6'
services:
  jenkins:
    image: jenkins/jenkins:lts
    network_mode: bridge
    privileged: true
    user: root
    ports:
      - 8080:8080
      - 50000:50000
    container_name: my-jenkins
    environment:
      VIRTUAL_HOST: jenkins.pratian.com #change it to your host
      LETSENCRYPT_HOST: jenkins.pratian.com #change it to your host
      LETSENCRYPT_EMAIL: prahask1996@ymail.com #change it to your email
      VIRTUAL_PORT: "8080"
    volumes:
      - ~/jenkins_data:/var/jenkins_home
      - /var/run/docker.sock:/var/run/docker.sock
      - /usr/bin/docker:/usr/bin/docker
      - /opt/sonar-scanner/sonar-scanner-4.6.2.2472-linux/bin/sonar-scanner:/opt/sonar-scanner/sonar-scanner
    depends_on:
      - nginx-proxy
      - nginx-proxy-letsencrypt
