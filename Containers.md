Why do we need Containers ?

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