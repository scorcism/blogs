
As previously discussed k8s provide us with the following features: 

1.  By-default cluster in nature, which fixes the issue of a single host
2.  Auto-healing, which helps with zero downtime
3.  Auto-scaling helps in scaling the application.
4.  Multiple enterprise-level supports


In k8s the lowest level of deployment is  **pod**. If we compare this to docker, In docker we deploy the **containers**.

In Docker we used to create a **container** and we deploy that container but, in k8s we cannot directly deploy the container, in k8s we will **use** these containers but as a **pod**.

So, now you may be thinking **What is pod?** and  **why we should deploy our container as a pod?**

*hold* let me explain you, 

In docker, if we want to run a continer we execute,  
`docker run -d -it --name containerImae -p x:x ImageName`. 

In this command you can see that, all of these arguments are passed in  command line to run the container. Which becomes quite lengtly most of the time.   

Which is not much supported for enterprise solution and this is one of the fundamental advantage of k8s.

To overcome this, What k8s want us to do is,

Create a `yml` file and mention everything inside that file. Usually the pod manifest file are called as **`pod.yml`**

`In k8s everything is writeen with yml file`. If you are unfamiliar with the `yml`, you can [follow this](https://www.youtube.com/watch?v=9BGWtTahGnw).

*So now we can say*,

**A pod can be described as a defination of how to run a container.** 

Pod basically is a  **wrapper**  or a concept that is similar to container but it abstracts the defined commands / arguments in  **`pod.yml`**

**A pod is just a wrapper over a container**.

**A pod can contain a single container or a multiple container. If pod  contains multiple containers k8s provide some advantages.**

If you put group of container in one single pod, then k8s will **allow** to *share networking*, *share resources* among the containers, this way container a and container b inside a single pod can talk to each other using localhost. Which eventually explains that, there is a pod and **inside** that pod we have a **container**. 

k8s allocates a  **Cluster Ip address**  to the pod and you can **access** the application inside the pod using  **Pod Cluster Ip address**

Ip addresses are **generated for the pods not the conatiner**.  **`kube-proxy`**  will generate the ip address.

## Working with the Pods
In docker when ever we want to run any command we have **docker cli**. Similarly in k8s we have **kubectl**.

**kubectl is command line for k8s**.

You can [follow this](https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/) guild to Install kubectl  
We will use [minkube](https://minikube.sigs.k8s.io/docs/start/) for learning.

To Install minikube  [follow this](https://minikube.sigs.k8s.io/docs/start/)

If you dont know what is minikube, you can [follow this ](https://kubernetes.io/docs/tutorials/kubernetes-basics/create-cluster/cluster-intro/) blog

In simple words, what minikube will do is it will create a VM first, on top of this this will create a single node kubernetes cluster.

### Working with pods 

Start minikube
```bash
minikube start #k8s cluster will be started.
```
![minikube start](https://imgur.com/6uSOwng.png)

Goto your notes directory and create a file **pod.yml**

![](https://imgur.com/GdxurHu.png)

**Now the question? all these are okay, but how and what should be inside the pod.**

If I say you dont need to remeber, what all things should be inside the **pod.yml**, you will be surprised, but this is the truth you should only rember the keyword and rest you can copy from  [this](https://kubernetes.io/docs/concepts/workloads/pods) and change as per your requirement.

Slowly, when you start practicing you will automatically learn all the required args.

This in page mentioned above, you can see a code snippet like this

```yml
apiVersion: v1 
kind: Pod
metadata:
  name: nginx
spec:
  containers:
  - name: nginx
    image: nginx:1.14.2 
    ports:
    - containerPort: 80
```

**Let's understand the file line by line** 

`apiVersion: v1` -> This indicates that the configuration is using the Kubernetes API version 1.

`kind: Pod` -> This specifies that you are creating a Pod.

`metadata` -> This section contains metadata about the Pod, such as its name.

`name` -> This assigns the name "nginx" to the Pod.

`spec` -> The "spec" section defines the desired state of the Pod.

`containers` -> This is where you define the containers that will run inside the Pod. In this case, 
there is one container definition.

`name: nginx` ->  This assigns the name "nginx" to the container.

`image: nginx:1.14.2` -> This specifies the Docker image to be used for the container. In this case, it's the official Nginx image with version 1.14.2.

`ports` -> This section defines the ports that the container will listen on.

`containerPort: 80` -> This specifies that the container will listen on port 80. This is the standard port for HTTP traffic, which is commonly used for web servers like Nginx.

![](https://imgur.com/n5u0sZr.png)

Now, running/executing the pod file
```bash
# Get all the pods
kubectl get pods

# Get brief info about all the pods
kubectl get pods -o wide

# Execute the new create pod,yml
kubectl apply -f pod.yml
```
![](https://imgur.com/68yNh56.png)

**Check status of the pods**

```bash
# Get all the running pods
kubectl get pods 

kubectl get pods -o wide
```

![](https://imgur.com/niBTZ3t.png)

Now, as you can see the **STATUS** of the pods is **running** and **NAME** is **nginx** as mentioned in the yml file and the **Ip** address is also assigned to the pod.

**But,** to access that we need to login into minikube cluster.

As in our case minikube is the **Master node** we need to login into the minikube but in production you will need to login into your master node that can be an ec2 instance or anything.

**To access the application**
```yml
minukube ssh

# as its cmd we can use `curl` to fetch the content
curl <Ip-address>
```
![](https://imgur.com/w0sMG0T.png)

**Verify the application**

```bash
kubectl logs nginx

kubectl descibe pod nginx 
```
You can check all the kubectl commands, here at **[kubectl cheetsheet](https://kubernetes.io/docs/reference/kubectl/cheatsheet/)**

### Now, you may be thinking that, abhishek where is the feature of auto-scaling or auto-healing 

On top of the **pod** we have a wrapper called  **`deployment`**.  So, we have to use  **`deployment`**  to use the features like auto healing and auto scaling.

**In production, you will we deploy pods you will deploy deployments.**

Which we will learn in next blog.


