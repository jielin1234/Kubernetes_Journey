- K8S does not deploy containers directly on the worker nodes.
- The containers are encapsulated into a K8S object known as Pods.
- Pod is a single instance of an application,
- it is the smallest object we can create in K8S
- Pod usually have a 1 to 1 relationship w/ containers running the application.
		- To scale up, create new pod and delete existing pod when scaling down. Do not add additional containers to an existing pod to scale the application
- A single pod can have multiple containers except for that fact that they are usually not multiple containers of the same kind. 
	- e.g. a helper container that is doing some support task such as processing a user entered data etc.
	