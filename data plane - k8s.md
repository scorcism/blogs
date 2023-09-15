
When I started learning about the K8S architecture, the basic building blocks were the control plane, which is the master node, and the data plane, which is the worker node.

I thought, Why not share what I have learned?

  
This will be a three-part post: 1) Data Place 2) Control Place; and 3) The entire arch, which will be a combination of the data plane and the control plane.

  
So here it is:

## Data Plane/Worker Node Simplified

In Kubernetes (K8s), the smallest unit of deployment is called a pod.

Pod ?

Pod is a "wrapper" over the containers, which has advanced capabilities. Think of it as a little package that can contain your application.

When you run a pod, it's pretty much like starting a container.

In Docker, you have a thing called the "Docker engine", which runs the container, while in K8s, we have a similar thing called the "container runtime." This runtime takes care of running the actual container inside the pod.

Here's where it gets interesting. A pod can actually hold multiple containers. So, while Docker does containers, K8s does pods with containers inside them.

In Docker, we have the trusty **Dockershim** for running containers. But in K8s, we're more flexible. We can use **Dockershim**, **Container**, or **Crio**; these are all like different flavours of the same ice cream, competing to be your runtime. K8s allow you to pick the one you like.

Now, let's talk about the magic happening inside a pod on a K8s worker node. We have a little helper called Kubelet. This Kubelet is like a caretaker for your Kubernetes pod. It keeps an eye on whether your pod is running smoothly or not, and if not, it raises the alarm.

In Docker, we've got **docker0** and some network tricks to make sure containers talk to each other and to the host. In K8s, we've got something called **kube-proxy** doing similar network magic. It helps pods communicate with each other, sort of like a networking wizard.

So far, we've met three main characters in our K8s story:

1. **kube-proxy**: The networking guru. It handles IP addresses and load balancing, and it loves using something called "iptables" to work its magic on Linux machines.  
  
2. **Kubelet**: The pod creator and babysitter It gets pods up and running, and if something goes wrong, it raises a flag to the control plane.  
  
3. **Container runtime**: The workhorse It's the one that actually runs your container, making sure your application is alive and kicking.  

That's a glimpse into the world of worker nodes and pods in Kubernetes, where containers and pods work together in harmony.

This is the architecture of the data plane. Simple
Check the diagram, will help you understand more.
![diagram](https://res.cloudinary.com/practicaldev/image/fetch/s--57SV6tDD--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://imgur.com/MuYnXCA.png)
