One day, when I was having my tea with some biscuits, I was watching YouTube, and a thought suddenly came into my mind: what is the entire process of fetching the data from the web server? That time, I did not search for this because I was eating bicus.

Today, suddenly, I thought, Why not do some research on this?

Below is the detailed exploration.

## Step 1: Parsing the URL


As soon as you type a web address like "https://dev.to/scorcism/" and hit Enter, the web browser gets to work. It breaks down the web address into its parts: 

The way it talks to the website (HTTP/HTTPS), the main address (dev.to), and any extra parts like folders or search questions.

## Step 2: DNS Resolution

Once the browser breaks down the URL, it needs to change the easy-to-understand domain name (like dev.to) into a computer-friendly **IP address**. 

This job is handled by the **Domain Name System (DNS)**, a network of servers spread out across the internet that works like a digital address book.

The DNS server transforms the domain name into an IP address, which helps your browser find the right web server in the huge online world.

## Step 3: Initiating the Connection

Now that the IP address is ready, your browser sets off on a mission to link up with the web server where the wanted stuff is kept.

If the URL starts with "https," the browser uses something called the Secure Sockets Layer (SSL) protocol. 

This fancy tech makes sure the communication between your browser and the server is safe and hidden from prying eyes.

## Step 4: The HTTP Request

With the connection all set, your browser gets ready to ask for stuff from the web server. It sends what's called an **HTTP request**, like a special message. 

This message says what thing you want (like a picture), how you want to get it (GET/POST), and other important stuff.

When the web server gets this message, it gets ready to give you what you asked for. It's like getting ready to reply to your question.

## Step 5: The Web Server's Response

Once the web server gets the request, it starts doing its job. 

It creates an **HTTP response**, which is like a special reply. 

This reply has a few parts, like a code that shows if things went well or not (success or error). 

It also has the thing you asked for, like a webpage, pictures, or styles. And there are more details in the headers that tell you about the server and the reply.

## Step 6: Parsing and Rendering

Now comes an important part for your browser. 

It takes the reply and starts to understand it. The text (HTML) in the reply is turned into something called a "Document Object Model" or DOM. 

It's like a map that shows where everything is on the webpage. Then, your browser uses the styles (CSS) to make things look nice, and any special codes (scripts) are run to make the page do cool things, like buttons that work or animations.

## Step 7: Asset Retrieval

While your browser understands the webpage's structure, it also finds links to other things like pictures, styles, and special codes. 

For each of these, your browser asks the web server for them.

## Step 8: Putting it all together

Once everything is gathered, your browser arranges everything and shows you the final webpage. 

This includes text, pictures, videos, buttons, and any moving parts that scripts made happen.

## Step 9: Now you are the owner

Now, the webpage is yours to explore. 

You can fill out forms, click on links, send information, and ask the server for more stuff. This makes it easy to move around the website and see different parts.

## Step 10: Browser Caching

Modern browsers make things faster by using a trick called **caching**. 

This means they save some stuff like pictures and scripts on your computer. 

When you go back to the same page, your browser can use these saved things, so it doesn't have to keep asking the server for them again and again. 

This speeds things up and makes your experience smoother.

**This all steps occurs after you click on the search**

---

If you have interest in **open source** you can contribue to my projects 
1. [One Liner](https://github.com/asPerReqirements/oneliner)

2. [Click Counter](https://github.com/asPerReqirements/click-counter)

---
If the article helps you, leave a like, follow, or anything 🙂.  
You can follow me on [LinkedIn](https://www.linkedin.com/in/abhishekpathak32/), [GitHub](https://github.com/scorcism), [Dev.to](https://dev.to/scorcism) and [hashnode](https://scorcism.hashnode.dev/).

**Bye**
