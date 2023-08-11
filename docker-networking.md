  

**Networking allows containers to communiate with each other, and the host system.**
 
Suppose we have,
2 Docker containers on the host system  
`backend` and `frontend` and they want to connect each other, and they need to surely interact with the host system.  

To manage and establish the connection between the participants, we need `docker netwoking`

We have two 2 quetions 
1. How Docker container will take to host
2. How container will have 1:1 chat

### How a container can talk to the host OS?

Whenever you create a container, 
Docker creates a **virtual eth (docker0)**. 

Without this, Docker cannot talk to the host. This is called **Bridge Networking**, which is the **default** in Docker.

Similar to bridge networks, we have different types of networks, which we will see soon.

Till then,

You can check the networks with
```bash
docker network ls
```
![docker network](https://imgur.com/1dFmUbe.png)
  
  We have **two** types of network **bridge network** and **host network**
  
**Bridge Network**
- As explained above, the bridge act as an interface between the docker conatiner and host OS.
	

![Bridge networking](https://imgur.com/IXsw17Q.png)


**Host Networking** 
- Containers will directly use the network of the host. Which is not prefereed

- here, when you create a container, docker will directly bind  your container with the ip address(eth0) of the host.

**[Overlay network](https://docs.docker.com/network/drivers/overlay/)** 
- This is very usefull when you have multiple hosts.

 **[Macvlan](https://docs.docker.com/network/drivers/macvlan/)**
 - Macvlan networking in Docker enables containers to have their own unique MAC addresses and appear as separate physical devices on the network.

**Containers inside the same bridge network will share the same network subnet. so, there will be a direct connection between both**
In our case, **container 1** and   **container 2** can directly talk with each other.

---
Till now, we have discussed different types of different networks,  
  
but we have an **underlying issue**.  
  
suppose, 
that when we have two Docker containers that are connected using the bridge network, they will have to share the `docker0 bridge`, 
which becomes the common path between both the container and host. 

This will make the conatiners  **not secure**,

For example, we have 3 containers: `backend`, `frontend`, and `payment`. 

Here, the backend and frontend can be kept in one network, 
but the `payment` must be in another network to maintain anonymity.  
  
### How do you achieve logical isolation?

This can be achieved using the `bridge` networking itself.

**Docker allows you to create custom bridge networks.**

So, in our scenario, one container can talk to the host with Veth or Docker 0, and the other container will talk using the custom bridge network. 


![Custom bridge network](https://imgur.com/87D8njr.png)

As you can see in the diagram, there is no connection between payment and the frontend and backend; therefore, payment is secure.
 
#### DEMO

#### Inspect Container
```bash
docker  inspect  container_name  # Inspect container
```
#### List Networks
```bash
docker  network  ls
```
#### Create new network
```bash
docker  network  create  new_name  # new bridge netwok will be created
```
### Attach new network to conatiner
```bash
docker  run  -d  --network=new_name  --name  payment_container  payment # attachh new_network to the container
```


#### However, you can at any point of time, attach the container to bridge network and enable communication
```bash
docker  network  connect  bridge  web
```

### Container with the host network
```bash
docker  run  -d  --name  demo-host  --network=host  image
```
### Remove network
```bash
docker  network  rm  test
```
  ---
There are many things to learn about docker network, more about hosts,overlay, etc., but for a beginner's experience, this much is sufficient.

If the article helps you, leave a like, follow, or anything 🙂.  
You can follow me on [LinkedIn](https://www.linkedin.com/in/abhishekpathak32/), [GitHub](https://github.com/scorcism), [Dev.to](https://dev.to/scorcism) and [hashnode](https://scorcism.hashnode.dev/).

**Bye**
