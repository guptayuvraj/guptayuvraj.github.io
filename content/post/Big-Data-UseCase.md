+++
date = "2016-08-05"
draft = false
title = "Big Data Testing - Use Case"
categories = ["Big Data","Testing"]
tags = ["Big Data","Testing","Hadoop","Automation","Python"]
author = "Yuvraj Gupta"
+++

**Use Case 1: You are deploying a Hadoop cluster of 200 nodes in production.**

This blog is the second blog in the series of Big Data Testing. Kindly visit the first blog (http://guptayuvraj.github.io/post/Big-Data-Testing/) to know about Big Data Testing along with various scenarios to test in Big Data ecosystem.

In this blog we will look at a common use-case used for testing in production environment. It is a fairly easy practical scenario which you can face. We will cover the following topics in this blog:-

- [Problem Statement](#PS)
- [Traditional Method of Testing](#TT)
- [Challenges in Traditional Method of Testing](#CTT)
- [Use of Automation](#UA)
- [What will Script do?](#SD)
- [Creating Automation Script as Sample](#AS)
  - [Structure of Configuration File](#SCF)
  - [Python Script](#PSC)
  - [Explanation of Python Script](#EPS)
- [Advantages of Automation Script](#AAS)

<a name="PS"> **Problem Statement**</a>

You need to validate that all the configuration files (5 configuration files in every server) across multiple servers in cluster is correct and consistent. Verify the configuration files are in desired location and content of each configuration files are same across every server. 

<a name="TT"> **Traditional Method of Testing?**</a>

Login into every server and check whether all the configuration files are present is desired directory location and manually check the content of all configuration files present in every server across cluster. 

<a name="CTT"> **Challenges in Traditional Method of Testing**</a>

- Time Consuming 
- Tedious work
- Impossible to verify contents of each configuration file across each server
- Impossible to find difference in configuration files across servers
- Tough to find the problem post production and fixing it will require downtime and loss in data affecting business significantly. 
- Tough to find the cause of problem and tougher to know whether problem is due to configuration files or not and if via configuration files then which configuration file on which server. 

<a name="UA">**Use of Automation**</a>

Create a script and a configuration file for the script. Configuration file will contain list of servers, list of files to check and directory in which files will be present. 

<a name="SD">**What will Script Do?**</a>

Initially, It will fetch the first server host address from configuration file and login into that server, fetch the file from the server as per the location of the file mentioned in configuration file, copy file from that server to local machine. Again it will fetch the second server host address from configuration file and login into that server, check whether configuration file is present in desired location as mentioned in configuration file, copy configuration files from second server to local machine and compare the configuration files received from both servers. The process continues for all the servers as mentioned in configuration file where it will fetch files and compare the files to validate whether there is any mismatch between files present across each server. Also this process continues for checking multiple files across each server.

<a name="AS">**Creating Automation Script as Sample**</a>

We will be creating scripts using Python in this use-case. You will require to create 2 files i.e. 1 configuration file and 1 script file.

<a name="SCF">**Structure of Configuration file:**</a>
```
[server]
server1=nameofserver1.com
server2=nameofserver2.com
server3=nameofserver3.com 
server4=nameofserver4.com
.......
.......
.......
server200=nameofserver200.com
[file]
file1=/name/of/file/file1.properties
file2=/name/of/file/file2.xml
.......
.......
file5=/name/of/file/file5.json
```
Let us save the configuration file as servers_files.txt

<a name="PSC">**Python Script**</a>

```
import os							
import ConfigParser						
config = ConfigParser.ConfigParser()				
config.readfp(open(r'servers_files.txt')) 				        
path1 = config.get('server','server1') 						  
for (file_key, file_val) in config.items("file"): 			        
FILE_NAME= "$(echo {} | sed 's!.*/!!')".format(file_val)
	os.system("mkdir -p /home/yuvraj/Desktop/{}".format(FILE_NAME))	
	for (server_key, server_val) in config.items("server"):
		os.system("scp -oStrictHostKeyChecking=no username@{}:{} /home/yuvraj/Desktop/{}/{}".format(server_val,file_val,FILE_NAME,server_val)) 	
		os.system("diff -q /home/yuvraj/Desktop/{}/{} /home/yuvraj/Desktop/{}/{}".format(FILE_NAME,path1,FILE_NAME,server_val))

```

<a name="EPS">**Explanation of Python Script**</a>

Line1 & Line 2 are used to import library for os operations and configuration parsing.

Line 3 is used to call configparser object.

Line 4 is used to open the txt file which is read by configparser.

Line 5 is used to fetch the value of server1 key.

Line 6 is used to create a loop to fetch file key & file value from configuration file.

Line 7 is used to fetch only the filename from the filelocation present in configuration file.

Line 8 is to create the directory based on filename fetched.

Line 9 is used to create a loop to fetch server key & value.

Line 10 is used to provide scp to copy file from server to local.

Line 11 used to find differences between all the files copied to local.


<a name="AAS">**Advantages of Automation Script**</a>

- No manual task 
- Easy to catch the problem by catching proper exception such as file not present in desired location or file contents differ 
- Verify within minutes that cluster of 200 node contains correct configuration files 
- Easy to verify whether contents of configuration file are same or not
- Easy to fix the problem as cause of problem is known and minimum downtime will be required to fix the problem if caused 

This usecase is not limited to the following scenarios:-

- Addition of nodes in cluster
- Removal of nodes in cluster 
- Setting up new cluster 
- Upgrading the version of the software used in cluster across the nodes 
- Downgrading the version of the software used in cluster across the nodes 
- Installing new software requiring setting up configuration files across the nodes 

At the end of this blog you will understand the ideology behind using automation for Big Data Testing. You will discover the benefits of using automation to test in Big Data ecosystem which will reduce the manual intervention of work to an extent. At the end a sample Python Script was shown which solved the problem in a simple yet elegant manner.
