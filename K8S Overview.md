- First is to understand [[Containers]] + [[Container Orchestration]]

Architecture:
- Node
	- Node is a machine, phsyical or virtual on which K8S is installed
	- Node is a worker machine and that is where containers will be launched by K8S
	- Need to have more than 1 node, if only 1 node and it fails, then the app will go down
- Cluster
	- Cluster is a set of nodes grouped together, so even if 1 node fail, the app is still accessible from the other nodes and helps in sharing loads as well
- Master
	- Another node with K8S installed and is configured as master
	- Master watches over the nodes in the cluster and is responsible for the actual orchestration of containers on the worker nodes.
- Components
	- When install K8S on a system, it is actually installing the following components:
		- API server: acts as front end for K8S. The users, device, CLI all talk to the API to interact w/ the K8S cluster.
		- etcd: reliable key value store to store all data used to manage the cluster
		- kubelet
		- Container Runtime: The underlying sw used to run containers (e.g. Docker)
		- Controller: The brain behind orchestration. Reponsible for noticing and reponsding when nodes or endpoint goes down. It make decision to bring up new containers in such cases.
		- Schedular: Distribute works/containers across multiple nodes. Look for newlt created containers and assign them to nodes.
