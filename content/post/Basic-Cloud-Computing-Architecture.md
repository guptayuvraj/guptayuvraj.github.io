+++

draft = false
date = "2016-03-24"
categories = ["Cloud Computing","Architecture"]
tags = ["Cloud", "Computing","Enterprise","Aechitecture"]
author = "Yuvraj Gupta"
title = "Basic Cloud Computing Architecture"

+++
When talking about a cloud computing system, it’s helpful to divide it into two sections: the front endand the back end. They connect to each other through a network, usually the Internet. The front end is the side the computer user, or client, sees. The back end is the “cloud” section of the system.

<u>**The front end includes the client’s computer (or computer network) and the application required to access the cloud computing system.**</u> Not all cloud computing systems have the same user interface. Services like Web-based e-mail programs leverage existing Web browsers like Internet Explorer or Firefox. Other systems have unique applications that provide network access to clients.

<u>**On the back end of the system are the various computers, servers and data storage systems that create the “cloud” of computing services.**</u> In theory, a cloud computing system could include practically any computer program you can imagine, from data processing to video games. Usually, each application will have its own dedicated server.

<u>**A central server administers the system, monitoring traffic and client demands to ensure everything runs smoothly.**</u> It follows a set of rules called protocols and uses a special kind of software called middleware. Middleware allows networked computers to communicate with each other. Most of the time, servers don’t run at full capacity. That means there’s unused processing power going to waste. It’s possible to fool a physical server into thinking it’s actually multiple servers, each running with its own independent operating system. The technique is called server virtualization. By maximizing the output of individual servers, server virtualization reduces the need for more physical machines.

If a cloud computing company has a lot of clients, there’s likely to be a high demand for a lot of storage space. Some companies require hundreds of digital storage devices. Cloud computing systems need at least twice the number of storage devices it requires to keep all its clients’ information stored. That’s because these devices, like all computers, occasionally break down. A cloud computing system must make a copy of all its clients’ information and store it on other devices. The copies enable the central server to access backup machines to retrieve data that otherwise would be unreachable. Making copies of data as a backup is called redundancy.
