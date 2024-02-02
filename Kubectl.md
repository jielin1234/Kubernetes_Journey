Use to deploy and manage applications on a cluster. To get cluster info, status of others nodes, and manage a lot other things etc. 

<kubectl run nginx>
This command will deploys a Docker container by creating a pod.
It create a pod automatically and deploy an instance of Nginx docker image.

<kubectl run nginx --image nginx>
To get the application image, add the image name using the image parameter. The image is downloaded from Docker Hub repo.

<kubectl get pods>
To see the lists of pods available in our cluster.

