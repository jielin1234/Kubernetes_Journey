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
	- 
