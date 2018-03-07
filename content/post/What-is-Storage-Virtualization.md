+++
date = "2016-04-05"
draft = false
title = "What is Storage Virtualization"
categories = ["Virtualization","Storage"]
tags = ["Virtualization","Storage","Block","File","Abstraction"]
author = "Yuvraj Gupta"
+++
It is the abstraction of physical media (hard disks or solid state drives etc) from the attaching servers which treats the storage as a single logical entity without regard to the hierarchy of physical media that is involved. Storage virtualization means adding an abstraction layer of software that hides the physical devices from the user and allows all devices to be managed as a single pool.
It adds a new layer of software or hardware in between the storage systems and servers so that the applications would not require to know to which logical drive, partitions or storage subsystems the data resides in.

Within the context of a storage system, there are two primary types of virtualization that can occur:

**Block virtualization** used in this context refers to the abstraction (separation) of logical storage (partition) from physical storage so that it may be accessed without regard to physical storage or heterogeneous structure. This separation allows the administrators of the storage system greater flexibility in how they manage storage for end users. The act of applying virtualization , to one or more block based (storage) services for the purpose of providing a new aggregated, higher level, richer, simpler, secure, etc., block service to clients. Block virtualization functions can be nested. A disk drive, RAID system or volume manager all perform some form of block address to (different) block address mapping or aggregation

**File virtualization** addresses the NAS challenges by eliminating the dependencies between the data accessed at the file level and the location where the files are physically stored. This provides opportunities to optimize storage use and server consolidation and to perform non-disruptive file migrations. File virtualization is the creation of an abstraction layer between file servers and the clients that access those file servers. Once deployed, the file virtualization layer manages files and file systems across servers, allowing administrators to present clients with one logical file mount for all servers
