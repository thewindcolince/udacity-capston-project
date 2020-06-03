                                                   UDACITY-CAPSTONE-PROJECT

                                                       PROJECT OVERVIEW 

Capstone is the final project on udacity cloud devops engineer nanodegrees. you have to apply the skill and knowledge which were developed throughout the Cloud Devops Nanodegree program. These include: 
working  in AWS 
Using Jenkins to implement Continuous Integration and Continuous Deployment 
Building pipelines
Working with Ansible and CloudFormation to deploy clusters
Building Docker containers in pipelines 
building Kubernetes clusters

                                                 My Capstone project 

As capstone project, I develop CI/CD pipeline for microservice application ( simple maven project) with rolling deployment. using Git, Jenkins, ansible, docker, kubernetes. 

                                                 Architecture 
    
             maven app → github  → Jenkins → ansible → docker →kubernetes

as you can see in the architecture, I have a simple maven project that will be push on github, jenkins will then trigger the project to integrate, test, build then will send the build file to ansible ansible will then create the docker container and push it in my docker hub account. through ansible, kubernetes server will pull the docker image and deploy it to a small kubernetes cluster. 

     		                                       	Requirement 

to successful deploy this project, we need a git install in our local computer, github account where to create our repository, Jenkins server ( I use EC2 for that) where to configure our CI/CD pipeline, ansible server where to create 
and execute our playbooks, kubernetes master server where to deploy our app in cluster.

                                                   Setup 

1-  github account.
 
 	just create a repository and push the maven project int it

2- Jenkins server

   In Jenkins server, I first install java( the newest version) and maven8, after that I configure ansible ssh server connexion to allow jenkins connect to my ansible server, I also install some usefull plugin( PublishSsh, blue ocean, maven invoker, git plugin, etc), I then create a pipeline and sync it with my project repository in my github account. all the rest to do I did it in my Jenkinsfile

3- ansible server 
	
	In my ansible server, I install ansible and configure it to passwordless communicate with
	kubernetes master server. I also create all my playbooks in the ansible server to automate 
	configuration in kubernetes. 

4- Kubernetes server

	In my kubernetes server I install python so ansible can act well. I install kops and kubectl. 
	I then create my kubernetes deploymet file and kubernetes services file to deploy pod and service.


 








