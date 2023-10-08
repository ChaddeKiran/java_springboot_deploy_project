
# Java Spring Boot Application Deployment on Amazon EKS with CI/CD Pipeline

Successfully deployed a Java Spring Boot application on Amazon 
EKS, utilizing a streamlined CI/CD pipeline orchestrated by Jenkins. The project 
emphasized automation and efficient deployment processes to enhance 
software delivery and reliability. Established comprehensive monitoring using 
Grafana and Prometheus for enhanced performance insights and proactive 
issue resolution.



## Author

- [Kiran Chadde](https://www.github.com/ChaddeKiran)


## Tools that are used

- terraform
- ansible
- Amazon EKS
- kubernetes
- docker
- jenkins
- prometheus
- grafana
- git
- github
- dockerhub


## Tools Installation

 - [docker](https://docs.docker.com/engine/install/ubuntu/)

 - [ansible](https://docs.ansible.com/ansible/latest/installation_guide/installation_distros.html)


  - [jenkins](https://www.jenkins.io/doc/book/installing/linux/)

 - [terraform](https://developer.hashicorp.com/terraform/tutorials/aws-get-started/install-cli)
 
 - [kubernetes](https://kubernetes.io/docs/home/)



## Initailly tested on amazon ec2 instance using ansible

Clone the project

```bash
  git clone https://github.com/ChaddeKiran/java_springboot_deploy_project.git
```

Go to the project directory

```bash
  cd java_springboot_deploy_project
```

build and run docker image locally 

```bash
  docker build -t chaddekiran/springboot_microservice_deployment .
```

```bash
  docker run -p 80:8085 chaddekiran/springboot_microservice_deployment:latest
```
push docker image to DockerHub 

```bash
  docker login -u username -p password
 ``` 

 ```bash
  docker push chaddekiran/springboot_microservice_deployment:latest
 ``` 

deploy on Ec2 instance using ansible playbook

```bash
  ansible-playbook -i 163.184.10.4 playbook.yml

```


## Docker

Created a Dockerfile, It includes instructions to set up the environment to install dependencies, and configure the application java springboot application.



## Terraform 

With Terraform, defined EKS configuration is in hashicorp language. Apply the plan to AWS, creating EKS resources (VPC, IAM, cluster, nodes). EKS orchestrates Kubernetes, enabling scalable containerized app deployment and management.

## Jenkins 

Utilising Jenkins, a CI/CD pipeline automates Java Spring Boot app deployment from GitHub to Amazon EKS via Kubernetes. This streamlined process ensures efficient, reliable, and rapid software delivery, promoting a seamless and professional deployment workflow.


## Kubernetes

Deployed a Kubernetes application using a deployment. Enabled external access via the LoadBalancer service, providing users seamless access to the application through a scalable and reliable endpoint.


## Running Deployments

To deploy on kubernates, run the following command

```bash
  kubectl apply -f eks-deploy-k8s.yaml
```


## Installation

Be make sure that helm kubernetes package manager is installed.   

Installation of Monitoring tools i.e Prometheus and Grafana using helm   

```bash
 helm install stable prometheus-community/kube-prometheus-stack   // -n prometheus
```

Varify that successfully completed the installation

```bash
 kubectl get svc    // -n prometheus
```
    
## Lessons Learned

Effectively addressed and resolved various technical challenges encountered 
during the project.

Gained expertise in DevOps practices, emphasizing automation, 
containerization, and efficient deployment strategies.

 Enhanced skills in deployment and management on Amazon 
EKS.

 Developed proficiency in utilizing CI/CD pipelines, monitoring 
tools, and infrastructure automation

