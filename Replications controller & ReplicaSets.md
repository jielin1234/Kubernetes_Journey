- Replications controller are the Brain behind K8S.
- They are the processes that monitor K8S object and respond accordingly
- Helps to run multiple instances of a single pod in the cluster. In case if one of the pod fails, it provides high availability.
- Even with a single pod, the controller will auto bring up a new pod when the existing one fail.
- It ensure the specified number of pods are running at all times, regardless 1 or 100.
- Also, it help to create multiple pods to share the load across them (load balancing & scaling)
- It can also deploy additional pods across the other nodes in the cluster if the demand increases.
- Replication controller is the older technology and Replicaset has replaced it.

YAML:
apiVersion: v1                                  apiVersion: apps/v1
kind: replicationController             kind: ReplicaSet
metadata:                                         metadata:
spec:                                                 spec:
   template:                                       template:
    
    (pod definitation)        (pod definitation) 

replicas: 3                                          replicas: 3
                            selector:
                               matchLabels:
                                 type: front-end


- What is selector for in ReplicaSet ?
Main difference in Replicaset and ReplicationController is selector.
Replicas can also manage pod that are not created as part of the replica set creation
e.g. there are pods created before the creation of replicaset that matches the labels specified in the selector, it will also take those pods into consideration when creating.

- How to update our replicaset to scale it ?
There are a few ways.
1. Change the replicaset number and run kubectl replace -f replicaset-definition.yml
2. Run kubectl scale --replicas=6 -f replicaset-definition.yml
3.  ...
Next, why do we need [[Why do we need Labels and Selectors ?]]
