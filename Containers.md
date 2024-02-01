 **Why do we need Containers ?**

In a project, alot of different technologies are required(e.g. Web server, MongoDB, Ansible) and there will be issues developing the application with all these different components.
- Firstly, their compatibility w/ the underlying OS. Have to ensure all these different services were compatible w/ the version of the OS we are planning to use.
	- There will be time when certain version of these services were not compatible with the OS and we have to go back and look for another OS that are compatible with these services
- Secondly, have to check the compatibility between these services and the libraries and dependencies on the OS. 
	- There will times where one service require 1 version of a dependent library, another service require another version
- Also, the architecture of our application changes over time, we have to upgrade to new version of these components or change the databases, etc.
	- Every time something changes, it have to go through the same process of checking compatibility between these component and the underlying infrastructure, known as Matrix from Hell.
	![[Pasted image 20240131143404.png]]
- New joined developer also had to follow a large set of instructions and run hundreds of command to finally set up the env correctly and make sure they are using the right OS the right version of these components.
- With different development test and production env, it is hard to guarantee that the application we are building would run the same way in different envs.
- Containers will help with the compatibility issues. We can modify/change these components w/o affecting other components and even modify the underlying OS as required.
- With Docker, we can run each component in a separate container w/ its own libraries & own dependencies, all on the same VM and OS, but within separate env or containers![[Pasted image 20240131152746.png]]
- We just have to build the Docker configuration once and all developers can now get started with a simple Docker run command, regardless of what underling OS they run.

**What are containers ?**
- Containers are completely isolated env, as in they can have their own processes or services, own networking interface, etc. except they shared the same OS system kernel
- Setting up container env is hard as they are low level, this is where Docker come in and offer a high lvl tools and make it easy for end users.![[Pasted image 20240131153221.png]]
- To understand better about how Docker works, learn on some [[basic concepts of OS]] first. 
- Let say we have a system w/ Ubuntu OS with docker installed on it, Docker can run any flavor of OS on top of it as long they are based on the same kernel. Meaning docker can run a container based on another distribution like Debian, febian or Centos since it is only the softwares that make these OS different.
- Docker is not mean to run different OS and kernel on same hardware like hypervisors. Main purpose is to containerise application and ship them and run them.![[Pasted image 20240131154231.png]]

**Container VS Image**
- Image is a package/template, use to create one or more containers.
- Containers are running instances of images that are isolated and have their own env and set of processes. 

**Advantage**s of Containers
- New developers can get started with a simple Docker run command, regardless of the underlying OS they run instead of running hundreds of commands and following a list of instructions to setup.
- Operation used to had to follow the set of instructions given by the developers such as how the host must be set up, what prerequisites are to be installed, how to configure, etc. Since the ops team did not develop the app, they will hit issue when setting up and had to work w/ developer to resolve it.
	- With Docker, the guide that the developers built previously to set up can now easily be put together in the form of a Docker file to create an image for the applications.
	- The image can now run on any container platform and is guarantee to run the same way everywhere. So operations team can simply use the image to deploy the application. 
	- Since the image are already working when the developer built it and the ops are not modifying it, it will continue to work the same way when deploying in production.

- Now we have our application packaged into a Docker Container, how do we run it in production ? What if the application relies on other containers such as db or messaging services or backend services ? What if number of users increase/decrease and we need to scale the application ?
	- We will need an underlying platform w/ a set of resources and capabilities. The platform needs to orchestrate the connectivity between the containers and auto scale up/down based on the load. The whole process of auto deploying and manging containers is called Container Orchestration
- Next, learn on Container orchestration 