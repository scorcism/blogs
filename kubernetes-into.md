# Kubernetes

## What is the diff betwn Docker and Kubernetes(k8s)

In simple words, 

- Docker is a  **container platform**.
- Kubernets is a  **container orchestration platform**.

Container are  **Ephermeral**  (short living in nature)(can die and revive anytime) in nature, which is a big concern when you want your system to run 27/9.

Yes, for developer its not 24/7 its 27/9.

Docker/Container has some problems when working in production

### Problems with Docker/Container

1.  **Single host** -> Nature of the container platform is scoped to single host.
2. **No auto healing** -> Suppose someone killed one of your container,so application running inside the container will be not accessible. Unless another developer or user starts the container it will not start., which can be done automatically in k8s.
3. **No auto scaling** -> as soon as the load get increased,  _manually_  you increase the container count from 1 to 10, which can be done automaticalyl in k8s.
4. **Minimilistic and simple platform** -> Docker doent support any enterprise level support. Enterprise standards such has having load balancer, firewall, auto scale, healing, api gateways, etc.

So, we can say that docker is good for playing around and learning but we cannot deploy the conatienr to prodction

To solve all those issues **k8s** came has a **super hero**. 

### How Kubernetes solves the problem

1. **Single Host** 
	- By default, kubernetes is a  **cluster (Group of nodes)**. 
	- K8s are installed in a **master/worker node architecture**. means, when ever we install kubernetes we just create one master node and and multiple worker nodes. 
	- If there is one faulty application in the node and  that application is impacting other applications, what k8s will do is, because it has **	multi node arch** immediatly it will put that application/pods in different node.

2.  **Auto Scaling**  
	 - k8c has **replica sets**. 
	 - Suppose we have increase in traffic we have someting called as  `replication.yml`  file, we can mention inside the replica the number of nodes we require.
	 - k8s also has  **HPA**(Horizontal pod autoscalar) using which you can say when ever there is a load just keep increasing.

3.  **Auto healing**  
		- K8s has something called as **replica set** and in that replica set we can descibe the number of container that must be running.
		- If any of the conatiner goes down, the **replica set** will immedialty roll up the new conatiner and will mainting the state 
		- Using the feature of auto-healing, when ever the container is going down, even before the container goes down, k8s will start a new container.
		- you may be thinking heinn what, but that true we will see in future actions.
		- 
4. **[Enterprise nature](https://www.cuelogic.com/blog/kubernetes-for-enterprise)**
	
### Many of the concept here may seems unfamilier, but later in the series you will get all the knowlegede

---

If the article helps you, leave a like, follow, or anything 🙂.  
You can follow me on [LinkedIn](https://www.linkedin.com/in/abhishekpathak32/), [GitHub](https://github.com/scorcism), [Dev.to](https://dev.to/scorcism) and [hashnode](https://scorcism.hashnode.dev/).

**Bye**
