e.g. 3 instances of front end web application as 3 pods.
So we would like to create a replication controller or replicaset to ensure there is 3 active pods at any time

Replicaset can be use to monitor existing parts if the pods are created already. If not created, it will create the pods for us. The role of replicaset is to monitor the pods and deploy new one if any of them fail. In fact, replicaset is a process that monitors the pods.

So how does the replicaset know what pods to monitor ? There would be 100+ of pods in the cluster running different applications. So labeling the pods during creation comes in handy, it can be use as a filter to know which pods to monitor.

Ques: So do it still require to provide a template section in the replicaset specification if the number of pods r
