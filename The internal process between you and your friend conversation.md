# How do messages from your system reach your friend's system?

From the time I started programming, I always used to think, **How did my messages reach his phone?** Link I know through the internet, but how really? text getting sent from one phone to another.

But due to college and all the other stuff not worthy of mention, my mind diverged from the topic. 

Today morning, when I woke up, the thought came: Why am I existing in the universe? Oh, sorry, I got derailed. Today morning, when I woke up, the sun was shining and the flowers were blooming. Yes, I wake up at 6 a.m., so I see this every day again. I got derailed when I woke up after some time. I opened my laptop, and suddenly I got the thought that I had lost my life mission. 

**How does the message from my system reach the girlfriend system?**

After that, I started my research and came to some conclusions, which I will discuss further.

**We will go in very, very depth**

We know that to establish communication between two or more systems, we need an "internet or network.

So, there are some rules to work with internet. Why these rules? As per my knowledge, if I take an example, suppose there is a product, say **a**, and many vendors know how to create or manufacture this product **a**, but all the vendors may be using different methods or following different rules to create the product **a**. So, to avoid this confusion, we can establish some rules, and based on those rules, those vendors can manufacture the product. For me product a will be *rasgulla* tasty... You can comment your fav sweet...

Similary, on the Internet, we have some rules, so all the companies that work with internet in any way should follow some rules.

Thre is something called as  OSI models, This is just a conceptual framework that will help us understand the network.

There are layers in OSI.

**The OSI layers are**  
  
1. Physical layer  
2. DataLink layer  
3. Network Layer  
4. Transport Layer  
5. Session Layer  
6. Presentation Layer  
7. Application Layer

aaahhh, I know it's too much, but don't worry, I will make it simple and sweet, like **rasgulla**.

These layers are just an abstraction to help us understand.

There are the layers that helps messages from the application move to the internet.

At this point, you may be thinking: *abhishek, this is all okay, but how do they tell me how?

Abhishek will say: *wait baba, wait, I will clear your doubts*

So, we have these seven layers, and these layers have some features.

Let's elaborate more about each later.

abouve we wrote the layers from 1 to 7 but for now

**We will learn in reverse order from Layer 7 to Layer 1**, which you will understand later.

### Layer 7: Application Layer

This layer is where you contact. It's your application and you.  
This provides an interface between the user and application or computer. This consists of raw data.

This is the layer where the data is processed. Responsible for providing services to the user.

Implemented in softwares.
  
Now moving to Layer 6

### Layer 6: Presentation later

This layer ensures that data is in usable format and is where data encryption occurs.

This layer is used to convert application layer data into network data later, which is carried by this layer.

For outgoing messages, it converts data into a general format, and for incoming messages, the data is converted, which is understandable by the application.

This helps in converting characters into binary. eg ASCII -> ebcib

now moving to layer 5.

### Layer 5: Session Layer

As the name says, in this session layer, we maintain a session, and between those sessions, we send all the data that we all want.

This is like, for a specific amount of time, we establish the session between the devices, and between those sessions we share information, aka, used to syncronize one host to another.

This helps in setting up connection establishing session, AUthenticatiin and authorization

now Layer 4

### Layer 4: Transport later

This layer manages the transmission of data across a network.

This manages the flow of data between parties by **segmenting** long data streams into smaller chunks, also called **segments**.

To manage the transmission of segments, the layer came up with two methods. `1. TCP` and `2. UDP`

- **TCP** (Transmission Control Protocol)  
- **UDP** (User Datagram Protocol)

These two themselves are another blog to cover. If you need to understand, then you can read after this article.

In short in **TCP** there will be no loss fo data and if data loss take place it provides proper data recovery mehenism and in **UDP** it just share data doent care if it is reaching the destination or not.

This helps communication to be more reliable, and it also works with the **port address**.

The layer helps with data recovery too. suppose while transmitting the data some of the data may get lost due to some glitch, so this helps by requesting to resend the segments that have errors.

This layer consistes of segmentation. flow control, error control, checksum.. etc

now moving on to layer 3.

### Layer 3: Network Layer

This layer decided which physical path the data would take.  
It also divides the data or **segments** from the **transport layer** into a **fixed number of packets**.

This layer moves the packets from source to destination. So, we can say that the actual transmission takes place at this layer.

The other main responsibility of this layer is that it appends the **logical address** to the packets headers.

This works for trasmission of received data segments from one computr to another in different network.

now moving to the data link layer

### Layer 2: Datalink Layer

The DataLink later, or layer 2, defines the format of data on the network.

The **packets** that came from the network later are further divided into **frames**.

This layer is also responsible for appending a header to the framers, a **mac address**. which is the physical address of the machine

This appends the physical address of the receiver to the header.

This allows direct communication with computer.

now moving to the last layer, i.e., the first later physical layer.

### Layer 1: Physical Layer  
The task of layer 1 is to transmit a raw bit of data or stream the data over a physical medium. Its like a real bit of that 8-bit we used to hear about that one. are transmitted over the medium. That medium can be wired or wireless.

To be precise, Layer 1, i.e., Physical Later, converts frames or bits into electonic signals for outgoing messages and also converts electonic signals into bits for incoming messages.

**Now,** you got why I started in reverse order.

The layers are from 1 to 7, but in the practical case, we go from 7 to 1 from our end.

This is the basic information about the OSI layers. 

You may be wondering, Okay, Abhishek, I got it, **but what about the receiver end?**

The diagram below will explain everything.

![network](https://imgur.com/TQcVHna.png)

As you can see, when you send the message, it starts with application layer, but from your friend's side, it starts with the physical layer.

Its like you starting with layer 7 and tthe frend system will start the process from layer 1.

I have something that will help you to learn this layers

1. Physical layer : **P**lease
2. DataLink layer: **D**o
3. Network Layer: **N**ot
4. Transport Layer : **T**hrow
5. Session Layer : **S**aussages
6. Presentation Layer: **P**izza  
7. Application Layer: **a**way

The credit goes to [this cannel](https://www.youtube.com/@TCMSecurityAcademy)

This will help you to learn easily

**NOTE: ** Till now we were talking about the OSI model, but in a practical use case we use the **TCP/IP** model, which is similar to the OSI model, but in this some layers are merged.

At this point, we got to know how the message from text is converted into bits. Now, **what about the internet sharing?** What about how bits will be send to the frend ?

That will also be covered, so be ready.

We will cover this too, point-wise.

### 1. Getting ready

It all begins with you typing out your message on your mobile device. The message could be a simple text, an image, a video, or any multimedia content. Once you hit send, the message starts its journey.

Its message contains all the headers, such as the receiver IP address, the Mac 
address, and all those things.

### 2. Message to the network

When you hit send, your mobile device communicates with your mobile service provider (also known as a carrier) to initiate the sending process. Your message is then handed over to the carrier's network.

At this point all the levels have done their work very well.

### 3. From tower to data center

The carrier's network plays a critical role in transmitting your message. Your message is first transmitted from your mobile device to the nearest cell tower. From there, it's sent to the carrier's data centre.

### 4. **Routing the Message**

At the data centre, the carrier's infrastructure routes the message to its destination. This involves determining the most efficient path for the message to travel through the network.

### 5. Interconnection Between Networks

If your friend is on a different carrier's network, the message needs to be passed from one carrier's network to another. 

This interconnection between different carrier networks is made possible through agreements and protocols.

### 6. **Routing to the Friend**

Once the message reaches the carrier's data centre serving your friend's area, it's sent to the cell tower nearest to your friend's location.

### 7. **Receiving the Message**

The message is then received by your friend's mobile device. The message is delivered to your friend's messaging app, ready to be read.

### 8. **Response**

Once your friend reads the message, they can compose a response and start the process all over again, sending their response back to you with all the layers attached.


  
**So, this is how you and your friend can talk with each other.**
  
If you want to get practical knowledge of this, you can send me a connection [here](https://www.linkedin.com/in/abhishekpathak32/) and we can talk, so all the processes will work automatically. hahah, just a joke I tried

---

If the article helps you, leave a like, follow, or anything 🙂.  
You can follow me on [LinkedIn](https://www.linkedin.com/in/abhishekpathak32/), [GitHub](https://github.com/scorcism), [Dev.to](https://dev.to/scorcism) and [hashnode](https://scorcism.hashnode.dev/).

**Bye**
