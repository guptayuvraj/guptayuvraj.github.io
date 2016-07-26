+++
date = "2016-04-08"
draft = false
title = "Implement Storage Virtualization"
categories = ["Virtualization","Storage"]
tags = ["Virtualization","Storage","Array","Host","Network","Implementation"]
author = "Yuvraj Gupta"
+++
Why do we need to implement Storage Virtualization?

* Increasing Storage Demands
* Too long to do backup and restore.
* Limited Space in Data Center.
* Need to improve DR capabilities.

Approach for implementation of Storage Virtualization?

*  **Host Based:**  Physical drives are handled by traditional device driver, while a software layer above device driver intercepts I/O requests, looks up metadata and redirects I/O.

    **Pros:**

    *    Simple to design and code.
    *    Supports any storage type.
    *    Improves storage utilization without thin provisioning restrictions.

    **Cons:**

    *    Replication and data migration only possible locally to that host.
    *    Traditional data recovery following a server disk crash is impossible.
    *    Storage utilization optimized only on per host basis.

* **Network Based:**  Storage virtualization is viewed as a network-based device using fibre channel networks connected as SAN. A fibre channel switch which is in between the host and storage will virtualize all requests. Interestingly operating system on the host doesn’t know it’s happening as it this method doesn’t rely on operating system.

    **Pros:**

   *    Simple Management Interface.
   *    Replication services across heterogeneous devices.

    **Cons:**

    *   Difficult to implement fast metadata updates in switches.
    *   Out-of-band requires specific host based software.
    *   In-band adds latency to I/O.

**Implementation of Network based**

* **Appliance Based:** an appliance residing between client and storage array implements storage virtualization layer and becomes new storage target. When the data is sent to appliance via client storage virtualization features can be enabled such as snapshot, thin provisioning and data replication.

    **Pros:**

    *    Versatility
    *    Cost

* **Switch Based:** an application that resides in server connected to fibre channel SAN switch. Though it sits in between host and storage but it may use different techniques for metadata mapping.

    **Pros:**

    *    Faster Speed.

    **Cons:**

    *    Expensive.
    *    Lacks features such as thin provisioning.

* **Storage Device Based:** the primary storage controller allows direct attachment of other storage controllers and provides virtualization services. It will provide pooling and metadata management services.

    **Pros:**

    *    No additional hardware or infrastructure requirement.
    *    Provides most of the benefits of storage virtualization.
    *    Does not add latency to individual I/O.

    **Cons:**

    *    Storage utilization optimized only across the connected controllers
    *    Replication and data migration only possible across the connected controllers and same vendors device for long distance support

* **Array Based:** storage virtualization layer lives entirely within storage array.
