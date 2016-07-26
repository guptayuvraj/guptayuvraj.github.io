+++
draft = false
title = "Cloud Enterprise Applications: 12 principles of operational readiness"
date = "2016-03-21"
categories = ["Cloud Computing","Enterprise"]
tags = ["Cloud", "Computing","Enterprise","Applications","Operational"]
author = "Yuvraj Gupta"
+++
# Enterprise service operational principles

These dozen statements describe how an enterprise service should be. If all these statements apply to my new enterprise service, I can happily stamp my operational approval on it.

I have provided a few examples to make these statements a little clearer, but I have not described the actions required to get there. As you can imagine, putting these principles into practice for enterprise services is complicated. It’s almost impossible to get everything right.

Many cloud innovatorprovide services in one or two of these areas, to ease an organization’s workload. You can pay Green Hat to provide cloud-based performance testing tools, Core Cloud Inspect to check security, and Cloudkick to monitor infrastructure. A few big players like EMC and Novell have enough tools to take all the responsibility. The bigger your wallet, the more responsibility you can avoid.

## My enterprise service:

  1.  **Has been functionally tested**:- If a new business application has not yet been signed off by the guy paying the bills, I will waste my time carrying out operational tests.
  2.  **Has capacity**:- Sysadmins may want to scale up the disk space for a storage service and the bandwidth for a video chat service. They may scale down to a pocket calculator for a monitoring service.
  3. **Is resilient**:- This is the world of High Availability: double up on single points of failure, improve code quality, and even if something does fail, make sure the service handles it gracefully.
  4.  **Is recoverable**:- If the student deletes half the files or the computer room catches fire, service can be restored.
  5.  **Is reliable**:- Customers use Internet services 24 hours a day, but an intranet may only be needed during office hours. An intranet that is down every night may still be perfectly reliable.
  6.  **Is scalable**:- What if the new service has traffic spikes or gets really popular? I may need to scale out by adding more servers. Wading through treacle is not attractive.
  7.  **Is monitored**:- The operational support people must be alerted immediately if someone breaks into the computer room, if upstream services disappear, and if a process goes berserk.
  8.  **Is supportable**:- If an architect designs an Internet bank that only runs on one server, how pleased will customers be when an operator turns off the bank to upgrade the memory?
  9.   **Is secure**:- Vulnerabilities get patched, an IDS (Intrusion Detection System) watches the network, and the security team have signed on the dotted line.
 10.  **Has been pushed to the limit**:- The whole system has been thrashed, bottlenecks fixed and the system thrashed again and again. The service owner then knows how much performance can be squeezed out of her service.
 11.  **Has integrity**:- The customer support people won’t be plagued by calls from customers whose data is inconsistent, whose files have disappeared, or whose transactions were duplicated.
 12.  **Will operate within the SLA**:- The people sponsoring this service deserve to know how their investment is doing. The service builders automate the measurement and reports of the service level. Stakeholders can then help a failing service to succeed.

