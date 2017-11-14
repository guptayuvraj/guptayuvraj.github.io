+++
date = "2017-11-14T19:35:13+05:30"
draft = false
title = "Introduction to Consul"
categories = ["Consul", "HachiCorp","DevOps","ConfigurationManagement"]
tags = ["Consul", "HachiCorp","DevOps","ConfigurationManagement"]
author = "Yuvraj Gupta"
+++

This Blog explores Consul as a tool for Configuration Management. The scope of this Blog is limited to the Installation and Usage of Consul for Configuration Management.

Consul is a tool developed by HashiCorp which has prior developed world-class tools such as Vagrant. Consul is a multi-featured tool providing various features out of which Configuration Management is one of the features. The evaluation of Consul is limited to Configuration Management itself.

For Configuration Management we require to use Consul as a server along with Consul-Template which provides templates for configuration files which runs as a client/agent and connects to the Consul server. Importantly, Consul-Template runs on the systems which should have direct connectivity with Consul server. 

**Working of Consul for Configuration Management**

* Consul provides a UI via which you can handle the Consul server.
* We create Key Value Pair combination and store the combinations in the directory which persists all the Key Value Pairs even in cases of consul restart.
* Key Value Pairs can be created via terminal or via UI. (UI makes it easier to create ;) )

**Working of Consul-Template**

* Consul-Template requires to create a configuration file template which has keyholders such as {{ key "elasticsearch/node-name-3" }} (The key and value it derives from Consul wherein we created Key Value pairs)
* Consul-Template requires a running Consul server to work/connect else it gives an error of unable to connect to consul server.
* Consul-Template reads the template file and replaces the values in the template file and copies it to the configuration file as specified. In addition you can mention the command to run once it detects a configuration is changed.
* Whenever the value of a key changes, Consul-Template runs the command issued to it such as restart the service etc.

