 **Why do we need Containers ?**

In a project, it would be required to use lot of different technologies(e.g. Web server, MongoDB, Ansible) and it will have a lot of issues developing the application with all these different components)
- Firstly, their compatitbility w/ the underlying OS. Have to ensure all these different services were compatible w/ the version of the OS we are planning to use.
	- There will be time when certain version of these services were not compatible with the OS and we have to go back and look for another OS that are compatible with these services
- Secondly, have to check the compatibility between these services and the libraries and dependencies on the OS. 
	- There will times where one service require 1 version of a dependent library, another service require another version
- Also, the architecture of our application changed over time, we have to updgrade to new version of these components or change the databases, etc.
	- Every time something change, it have to go thorugh the same process of checking compatibility between these component and the underling infrastucture. Know as Matrix from Hell
	![[Pasted image 20240131143404.png]]
- New join developer also had to follow a large set of instructions and run hundreds of command to finally set up the env correctly and make sure they are using the right OS the right version of these components.
- With different development test and production env, it is hard to guarantee that the application we are building would run the same way in different envs.
- Containers will help with the compatibility issues. We can modify/change these components w/o affecting other components and even modify the underlying OS as required.
- With Docker, we can run each component in a seperate container w/ its own libraries & own dependencies, all on the same VM and OS, but within seperate env or containers![[Pasted image 20240131152746.png]]
- Just have to build the Docker configuration once and all developers can now get started with a simple Docker run command, regardless of what underling OS they run.

**What are containers ?**
- Containers are completely isolated env, as in they can have their own processess or services, own networking interface, etc. except they shared the same OS system kernel
- Setting up container env is hard as they are low level, this is where Docker come in and offer a high lvl tools and make it easy for end users.![[Pasted image 20240131153221.png]]
- To understand better about how Docker works, learn on some [[basic concepts of OS]] first. 
- Let say we have a system w/ Ubuntu OS with docker installed on it, Docker can run any flavor of OS on top of it as long they are based on the same kernel. Meaning docker can run a container based on another distribution like Debian, febian or Centos since it is only the softwares that make these OS different.
- Docker is not mean to run different OS and kernel on same hardware like hypervisors. Main purpose is to containerise application and ship them and run them.![[Pasted image 20240131154231.png]]
- Container VS Image
-