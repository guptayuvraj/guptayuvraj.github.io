+++
date = "2016-04-16"
draft = false
title = "Open Stack Swift"
categories = ["Cloud Computing","Software","Storage"]
tags = ["Cloud", "Computing","OpenStack","Swift","SOS"]
author = "Yuvraj Gupta"
+++
**ELIMINATE VENDOR LOCK-IN** OpenStack Swift is open source. 
Change providers without changing your application. 

**LOW COST** Choice of industry standard hardware that is available from multiple vendors.

**Features**

Deployment Automation- Deployment of availability zones based on hardware.
Centralized Management- Provides diagnostics, monitoring data, alerts to controller.
Capacity Management- Orchestrates capacity additions and removals without interruption.
Monitoring- Monitors 500+ data points per node and integration with ganglia and nagios.

**Hardware Overview:**

Proxy Tier- Proxy nodes handles all incoming API requests. Once a proxy server receives a request, it will determine which storage node to connect to, based on the URL of the object. A minimum of two nodes should be deployed in the proxy tier for redundancy. The proxy tier also includes ssl-terminators and authentication services.

Storage Tier- When a client uploads data to SwiftStack, the proxy tier will write data in three different availability zones in the storage tier. For incoming read requests, one of the three replicas of the data will be served. Subsequently, each storage node and drive that is added to a Swift cluster will not only provide additional storage capacity, but will also increase the aggregate IO capacity of the cluster as there are more drives available to serve incoming read requests.

Networking- A typical SwiftStack deployment will have a front-facing ‘access’ network (to run the proxy and authentication services) and a back-end ‘storage’ network.  As there are three copies of each object, an incoming write is sent to three storage nodes. Therefore network capacity for writes needs to be considered in proportion to overall workload.

**Recommended System Requirement:**


Proxy Tier- Typically, Proxy servers are 1U systems with a minimum of 12 GB RAM. For small SwiftStack clusters, the storage services and proxy services can run on the same physical nodes.

Storage Tier- Storage nodes are typically higher ­density 2U, 3U or 4U nodes with 12-­‐36 SATA disks each. A good rule of thumb is approximately 1 GB of RAM for each TB of Disk.

Drives- 2TB or 3TB 7200 RPM SATA drives.

Networking- Storage nodes can be provisioned with 1GbE (single gigabit) or 10GbE network interface depending on expected workload and desired performance.
