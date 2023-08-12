Kubernetes offers four fundamental advantages over Docker.

1. By-default cluster in nature, which fixes the issue of a single host
2. Auto-healing, which helps with zero downtime
3. Auto-scaling helps in scaling the application.
4. Multiple enterprise-level supports

## Understanding the architecture of K8s

We will understand the architecture in conjunction with the docker component.

In K8s, we create a **master node** and **multiple worker nodes**.

In K8s, we **don't** directly send the request to the **worker**; the request goes through the **master**.

Your request always goes through something called the control plane, or master node.

![request flow](https://imgur.com/j0LzP11.png)

## Data Plane / Worker Node

In K8s, the smallest level of deployment is **pod**. In Docker, we deploy a **container**.

### What are pods?

A pod is just a **wrapper** over a container, which has some advanced capabilities.

When the user tries to deploy a pod, similar to a container, your pod gets deployed. 

In Docker, we have a **Docker engine** called **Dockershim** which is used to run containers. 

In K8s we have a **container runtime**.

The difference is that Docker is **not** mandatory. In docker have **Dockershim** as a runtime, but in K8s, we can either use Dockershim, Containerd, or Crio; these are all competators of Dockershim. In k8s we can you any other container runtime that implements the K8s container interface.

We have a component in pods called **Kubelet**, which is responsible for **running the pod** in the *worker node*.

**Kubelet**, which is responsible for maintaining this Kubenetes pod, always looks for containers that are inside the pod; if the pod is running or not, using the feature of auto-healing, it maintains the environment.

In Docker, we have **docker0**, or we have **default** networking in Docker, which will make the communication between containers and host easier.

Mostly we work withbridge networking, so in K8s we have **`kube-proxy`** which will provide networking in K8s.

So, till now, we talked about 3 component

1. **Kube-proxy**, which provides networking, IP addresses, and load balancing. It uses [ip tables](https://medium.com/skilluped/what-is-iptables-and-how-to-use-it-781818422e52) on the Linux machines.
2. **kubelet**: actually responsible for **creation** of the _pod_ and also responsible for **running** the application. If the application is not running, then Kubelet informs one of the components in the control plane that something is going wrong.

3. **Container runtime**: which actually runs your container

![data plane](https://imgur.com/MuYnXCA.png)

## Master Node/Control Plane

Why do you need the control plane, master component, or master node?

So for any application or component, there are some standards; a **cluster** is one specific standard.

Till now we got to know that in k8s architecture we have a master know which is also called as control place and multiple worker node called as Control Plane.

So, who will decide where the pod will be created, in node 1, node 2, etc. coz we have multiple nodes? 

This is one specific instruction; there can be multiple instructions, and there should be a core component that has to deal with such types of instructions. Components, which act as core components, take all the requests. There has to be a core component that is basically doing everything in the K8s, and that core component is called **API server**, and this component is present in your **master component**.

**API server** is a component that basically exposes your K8s to the external world. The **heart** of the K8s is the API server.

Now, suppose the user is trying to create a pod. He tries to access the **API server**, and from the API server, the K8s API server decides that node 1 is free, but to schedule the container in node 1, we have a component called **'scheduler'**.

**Scheduler** -> Scheduler is responsible for **scheduling** your pod or your resources on K8s.

_The API server decides the information, and the controller acts on that information_.

Now that we have deployed, we need a component that should act as a backup service, acting as a backup store for the entire cluster information.

In K8s, we have **`etcd`**.

**etcd** -> A key value store is where the entire cluster information is stored as objects, etc. Without etcd, we don't have cluster-related information in backup.

and the most attractive feature of the k8s is auto-scaling and auto-healing. To manage this features, K8s have some components, we have **controllers**. Which are used to maintaing the state of the cluster. e.g of controller, **replica sets**, used for maintaining the state of the pods.

Those controllers are managed by the **controller manager**.

So, till now, we talked about 4 components in the control place.

1. **API Server**: All the communication that will happen in the cluster will be via the API Server; it exposes a restfull API over https.

2. **Scheduler**: Responsible for physically scheduling the objects and stuff. Listen to the API server. The scheduler will be responsible for scheduling it on the worker node. Manages new requirements.

3. **ETCD** -> It's a database that stores information about the cluster. If api wants any info, it communicates with the etcd db and can get any information, including configuration about the cluster.

4. **Controller Manager**: The controller manager manages controllers and has four functionalities.
	1. Maintaining the desired state
	2. Maintaining the current state
	3. Check the difference in sttae.
	4. Make the changes.

![control plane](https://imgur.com/eB5xrg7.png)

## Summary: Components of K8s

The K8S architecture is divided into **two** parts.

**control plane** (master node) and **data plane** (worker node)

Data plane: executing the actions

1. kube-proxy
2. Container runtime
3. kubelet

Control plane: controlling the actions.

1. API server
2. etcd
3. schedular

---

### Many of the concept here may seems unfamilier, but later in the series you will get all the knowlegede

For video tutorial you must follow [Abhishek.Veeramalla](https://www.youtube.com/@AbhishekVeeramalla)

---
f the article helps you, leave a like, follow, or anything 🙂.  
You can follow me on [LinkedIn](https://www.linkedin.com/in/abhishekpathak32/), [GitHub](https://github.com/scorcism), [Dev.to](https://dev.to/scorcism) and [hashnode](https://scorcism.hashnode.dev/).

**Bye**
