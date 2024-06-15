- Replications controller are the Brain behind K8S.
- They are the processes that monitor K8S object and respond accordingly
- Helps to run mutiple instances of a single pod in the cluster. In case if one of the pods, it provides high availability.
- Even with a single pod, the contorller will auto bring up a new pod when the existing one fail.
- It ensure the specified number of pods are running at all times, regardless 1 or 100.
- Also, it help to create mutiple pods to share the load across them (load balancing & scaling)
- It can also deploy additional pods across other nodes in the cluster if demand increases.
- Replication controller is the older technology and Replicaset has replaced it.

YAML:
apiVersion: v1                                  apiVersion: apps/v1
kind: replicationCrontoller              kind: ReplicaSet
metadata:                                         metadata:
spec:                                                 spec:
   template:                                       template:
    
    (pod definitation)        (pod definitation) 

replicas: 3                                          replicas: 3
                            selector:
                               matchLabels:
                                 type: front-end

