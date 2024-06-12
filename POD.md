- K8S does not deploy containers directly on the worker nodes.
- The containers are encapsulated into a K8S object known as Pods.
	- [[Why so?]] 
- Pod is a single instance of an application,
- it is the smallest object we can create in K8S
- Pod usually have a 1 to 1 relationship w/ containers running the application.
		- To scale up, create new pod and delete existing pod when scaling down. Do not add additional containers to an existing pod to scale the application
- A single pod can have multiple containers except for that fact that they are usually not multiple containers of the same kind. 
	- e.g. a helper container that is doing some support task such as processing a user entered data, etc. and we want these help containers to live alongside side the application container.
	- When 1 container die, the other also died since in the same pod
	- 2 containers can communicate directly w/ each other by referring to each other as local host since they sahre the same network space
	- they can share the same storage space as well

- When a pod is created, we can only access it internally from the node, will have to configure such that external user can access

