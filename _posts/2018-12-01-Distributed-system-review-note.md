---
layout:     post
title:      Distributed System Review Note
subtitle:    "\"some answers for the paper and book\""
date:       2018-12-01
author:     demerzel
header-img: img/post-bg-2015.jpg
catalog: true
tags:
    - distributed system
---

# distributed system - review note
#distributed system#

[150114](bear://x-callback-url/open-note?id=F279C50C-42A5-492C-8C0C-D5C3CE88F07E-6897-0000E14D780D7C68&header=answer%20for%20150114)
[160115](bear://x-callback-url/open-note?id=F279C50C-42A5-492C-8C0C-D5C3CE88F07E-6897-0000E14D780D7C68&header=answer%20for%20160115)
[160420](bear://x-callback-url/open-note?id=F279C50C-42A5-492C-8C0C-D5C3CE88F07E-6897-0000E14D780D7C68&header=answer%20for%20160420)
[160822](bear://x-callback-url/open-note?id=F279C50C-42A5-492C-8C0C-D5C3CE88F07E-6897-0000E14D780D7C68&header=answer%20for%20160822)
[170110](bear://x-callback-url/open-note?id=F279C50C-42A5-492C-8C0C-D5C3CE88F07E-6897-0000E14D780D7C68&header=answer%20for%20170110)
[170530](bear://x-callback-url/open-note?id=F279C50C-42A5-492C-8C0C-D5C3CE88F07E-6897-0000E14D780D7C68&header=answer%20for%20170530)
[171102](bear://x-callback-url/open-note?id=F279C50C-42A5-492C-8C0C-D5C3CE88F07E-6897-0000E14D780D7C68&header=answer%20for%20171102)
[180112](bear://x-callback-url/open-note?id=F279C50C-42A5-492C-8C0C-D5C3CE88F07E-6897-0000E14D780D7C68&header=answer%20for%20180112)
## answer for 150114
1. ![](2018-12-01-Distributed-system-review-note/F0651340-B230-4078-B6AF-9FA49AA8D3BD.png)
Transparency is defined as the concealment from the user and the application programmer of the separation of components in a distributed system, so that the system is perceived as a whole rather than as a collection of independent components. 
* /Access transparency/
* /Location transparency/
* /Concurrency transparency/
* /Replication transparency/
* /Failure transparency/
* /Mobility transparency/
* /Performance transparency/
* /Scaling transparency/

2. ![](2018-12-01-Distributed-system-review-note/A961D6B0-1688-4188-99A0-506E8BB1B810.png)

Transient communication:A message is stored by the communication system only as long as the sending and receiving application are executing. 
Synchronous communication: block sending and receiving 

In transient synchronous communication there would scalability problems. Scalability is the ability for a distributed application to expand without affecting any of the application algorithms. The transient synchronous communication would have issues pertaining to geographical scalability. If the client and the server are placed in two far-away geographical locations it would take a considerable amount of time for the client to send a request and receive a reply. Because the client remains idle until it receives the reply there is a considerable waste of time, since the client can only resume after receiving the reply. If the system is always in idle mode all of the time as it is synchronous there would not be any room for scalability. 

This situation is actually simpler. An asynchronous send is implemented by having a caller append its message to a buffer that is shared with a process that handles the actual message transfer. Each time a client appends a message to the buffer, it wakes up the send process, which subsequently removes the message from the buffer and sends it its destination using a blocking call to the original send primitive. The receiver is implemented similarly by offering a buffer that can be checked for incoming messages by an application.

3. 
![](2018-12-01-Distributed-system-review-note/916A78C1-876A-433B-AC48-DFB8FED85E1C.png)

4. 
![](2018-12-01-Distributed-system-review-note/CE371F6C-2C64-4821-BEB2-8351EB608AAD.png)

TODO

2:
a) consistent, not transitless
b) consistent, not transitless
c) in consistent, transitless

5. ![](2018-12-01-Distributed-system-review-note/E59CB1B7-6549-44A7-B257-E90897FAFAC1.png)

P3 will sent 2 messages to P4,P5;
P4 will sent 2 elec message to P5,P6. will sent 1 message to P3

5 message.

6. 
![](2018-12-01-Distributed-system-review-note/030B5D7C-0D20-4B30-9C4D-30633ADB6FD9.png)

Because the process need to judge the priority between the request process and itself. A late timestamp usually means it has low priority.

TODO


7. ![](2018-12-01-Distributed-system-review-note/3D71F732-19E9-4009-812A-F4B59D985B72.png)
Recursive DNS queries occur when a DNS client requests information from a DNS server that is set to query subsequent DNS servers until a definitive answer is returned to the client. The queries made to subsequent DNS servers from the first DNS server are iterative queries.

Recursive DNS query risks

A DNS server that supports recursive resolution is vulnerable to DOS (denial of service) attacks, DNS cache poisoning, unauthorized use of resources, and root name server performance degradation.

8. 
![](2018-12-01-Distributed-system-review-note/9EFCB8AC-155E-48F3-93AF-12B9A44033E0.png)

strictly is the most strong one, and casual is the weak.

Strict: Any read to a memory location X returns the value stored 
by the most recent write operation to X. 

all of them guarantee.

9. ![](2018-12-01-Distributed-system-review-note/4CF9B497-13DB-4EDF-A818-B2456C4A35BA.png)
1）no
2)  yes
![](2018-12-01-Distributed-system-review-note/18931924-7916-4A1E-923B-1E86DD5000D3.png)
change the second line blue and green
3)  
![](2018-12-01-Distributed-system-review-note/82009E85-F801-4D4F-A335-B74CBD4015F2.png)

11. 
![](2018-12-01-Distributed-system-review-note/D36488F7-AFD7-4A17-BC3C-F8C9DFD920CC.png)


## answer for 160115
1. 
![](2018-12-01-Distributed-system-review-note/FE8DE721-6C34-42D8-926B-3D087F204D60.png)
The system can be extended and re- implemented in various ways
 An open system offers services according to standard rules that describe the syntax and semantics of those service. An Open Distributed System is made up of components that may be obtained from a number of different sources, which together work as a single distributed system. 

Scalability of a system can be measured along at least three different dimensions: 
– Size
– Geographically – Administratively 

2. 
![](2018-12-01-Distributed-system-review-note/2D0F4F54-0A2B-4AA7-819F-483CCF40490C.png)

For at least one, to enable reply messages to be re-transmitted without re-executing operations, a server must retain the last reply to each client. So RR need to save the last reply. And RRA will save the reply until the ack.

For at most one, do not need to save reply.

3. 
![](2018-12-01-Distributed-system-review-note/24C5CDE4-0FB6-4ADA-9DE3-ECC4379DCE7E.png)


4. 
![](2018-12-01-Distributed-system-review-note/DDDD6C60-8F28-4187-A635-417E8D0B82B6.png)

![](2018-12-01-Distributed-system-review-note/89FA592C-AAB2-4DCA-AB0A-E76FE9E2AAD4.png)

5. 
![](2018-12-01-Distributed-system-review-note/878F3C73-610F-417E-85DF-644361AE00CE.png)
![](2018-12-01-Distributed-system-review-note/0B09F40C-E2F0-43D2-949C-ECF97381382C.png)
Answer: Ricart and Agrawala’s algorithm multicast-based algorithm multicasts requests, and requires reply from all other processes before entering a critical section, which is expensive when one process needs several access to the critical section before any other process requests for it. One possible solution is to change the state from HELD to TEMP instead of RELEASE when the process is done with the critical section. If it needs access again, it can change the state from TEMP to HELD without sending multicast message.
To satisfy ME2 the process has to change state TEMP to RELEASE if there is any request for the critical section, i.e., its queue is not empty.

6. ![](2018-12-01-Distributed-system-review-note/C3EB305D-71B1-4910-B18A-19EF2A7000B1.png)

For example, suppose the you have a web application where a replication group is implemented within a load balanced web server group. Each request to the web server consists of an update operation followed by read operations (say, from the same client), The read operations naturally expect to see the data from the updates executed by the same request. However, the read operations might have been routed to a replica that did not execute the update.

In such a case, the update request would generate a commit token, which would be resubmitted by the browser, along with subsequent read requests. The read request could be directed at any one of the available web servers by a load balancer. The replica which services the read request would use that commit token to determine whether it can service the read operation. If the replica is current enough, it can immediately execute the transaction and satisfy the request.

7. 
![](2018-12-01-Distributed-system-review-note/2D57AD38-0C88-415D-A578-6CACF8FF1809.png)
In Iterative DNS Query, when a DNS Client asks the DNS server for name resolution, the DNS Server provides the best answer it has. If the DNS Server doesn't know the answer to the DNS Query from Client, the answer can be a reference to another lower level DNS Server also.

ad: Iterative servers are useful when you wish to provide resolution for your own zone, and only your zone. 
avoid the DOS attack.

dis: add the load of the client.

8. 
![](2018-12-01-Distributed-system-review-note/E49F91EE-687F-4D74-A4EE-6C84667ABF84.png)
1) yes
2) yes
3) no

9. 
![](2018-12-01-Distributed-system-review-note/5B947AE0-99AC-407F-8AB2-BB39A7A9C627.png)

![](2018-12-01-Distributed-system-review-note/5F3CB8D6-217D-4400-B9C4-21071B59BC20.png)

10. 
![](2018-12-01-Distributed-system-review-note/0A46564E-B73E-47B5-A16F-960B202AD084.png)


没处理完的是open

11. 
![](2018-12-01-Distributed-system-review-note/0142307D-B969-41BA-8439-E9E1E582892A.png)


## answer for 160420
1. 
![](2018-12-01-Distributed-system-review-note/E68321E1-99ED-4753-8A1B-07A1850D5AC1.png)
Aiming at the highest degree of transparency may lead to a considerable
loss of performance that users are not willing to accept.

sometimes users need to get the real address of the resources.

2. 
![](2018-12-01-Distributed-system-review-note/563F6FC7-9B0A-4241-8E41-7DEC93F611B5.png)


3. 
![](2018-12-01-Distributed-system-review-note/0047B6D9-7895-42E6-85D8-E0898F169344.png)


![](2018-12-01-Distributed-system-review-note/8B362566-4A0D-41E1-96BA-F77055019C50.png)
![](2018-12-01-Distributed-system-review-note/1BD257E9-63D6-4219-887F-592401FFBC2C.png)

4. 
![](2018-12-01-Distributed-system-review-note/558DC7CC-34FA-4F05-994F-54C143334C79.png)

![](2018-12-01-Distributed-system-review-note/F1F6AC17-6CB5-4256-AA61-DA40915C5D88.png)
![](2018-12-01-Distributed-system-review-note/447DA820-3872-45DD-A6E5-DECC97EBAFAA.png)
![](2018-12-01-Distributed-system-review-note/E595818A-ED91-4103-BEFB-DFCAA5A4B9B2.png)


5. 
![](2018-12-01-Distributed-system-review-note/5B6F7FC5-A487-4C4D-984B-2986888C6D70.png)

In case of network partitions, subgroups will be formed. Each subgroup can run Bully algorithm and elect a coordinator with the highest ID in the subgroup. When the network heals, the subgroups should merge and elect one coordinator with the highest ID.


6. 
![](2018-12-01-Distributed-system-review-note/B9C6CE2F-66B3-43F2-B44C-77576B6550F2.png)


![](2018-12-01-Distributed-system-review-note/38B545D1-B649-4A2B-856C-019A86D8CE73.png)


7. ![](2018-12-01-Distributed-system-review-note/54DC2420-C38D-46E8-8D7A-A072CD96C105.png)
In Iterative DNS Query, when a DNS Client asks the DNS server for name resolution, the DNS Server provides the best answer it has. If the DNS Server doesn't know the answer to the DNS Query from Client, the answer can be a reference to another lower level DNS Server also.
 Root name server 

8. 
![](2018-12-01-Distributed-system-review-note/F14122B7-598A-4305-9197-190AEF66DFF6.png) 2 Phase commit
– /voting phase/: coordinator asks all participants if they can commit 
* if yes, participant records updates in permanent storage and then votes 
– /completion phase/: coordinator tells all participants to commit or abort 

The coordinator of the top-level transaction communicates with the coordinators of its child sub-transactions, Each participant collects the replies from its
descendants before replying to its parent. 
if the participant has some provisionally committed sub transactions:
• Check that they do not have aborted ancestors in the
“abortList”. Then prepare to commit;
• Those with aborted ancestors are aborted.
• Send a Yes vote to the coordinator.

 Compared with hierarchy protocol
 In hierarchy protocol, at each stage, the participant only need look for sub-transactions according to the information in the second argument.
 Flat protocol needs to use the abort list to remove transactions whose parents have aborted
 The advantage of flat protocol: coordinator of top-level transaction can directly communicate with all the participants. 

9. 
![](2018-12-01-Distributed-system-review-note/AB1C5955-E374-4912-8A98-8BF287D5AB5C.png)

## answer for 160822
1. ![](2018-12-01-Distributed-system-review-note/D8170844-18C2-4789-BB98-18774554B500.png)

Structured P2P networks overcome the limitations of unstructured networks by maintaining a Distributed Hash Table (DHT) and by allowing each peer to be responsible for a specific part of the content in the network. These networks use hash functions and assign values to every content and every peer in the network and then follow a global protocol in determining which peer is responsible for which content. This way, whenever a peer wants to search for some data, it uses the global protocol to determine the peer(s) responsible for the data and then directs the search towards the responsible peer(s).

 The problem is that we are dealing only with logical paths. It may very well be the case that two nodes A and B which are neighbors in the overlay network are physically placed far apart. As a consequence, the logically short path between A and B may require routing a message along a very long path in the underlying physical network.

2. 
![](2018-12-01-Distributed-system-review-note/21AF937F-1FAC-4C77-A296-5D56560E3D9F.png)
Persistent connections between a web client and a server can be reused for more than one exchange of a request and a response.

Persistent connections improve network performance because a new connection does not have to be established for each request. Establishing a new connection consumes significant additional network resources compared to making a request using an existing connection.

3. 
![](2018-12-01-Distributed-system-review-note/E7E9730F-E74F-4453-94C0-86F75BCBB0B9.png)

![](2018-12-01-Distributed-system-review-note/5E3EF8C8-EA10-44F6-A4C8-B717253F56BD.png)

4. 
![](2018-12-01-Distributed-system-review-note/2550AFC4-C09C-4B61-9901-65942FA06C09.png)

 The relation  ’ on the set of events of a system is the smallest relation satisfying the following three conditions:
1) If a and b are events in the same process, and a was executed before b then a  b. 
2) If a is the event of sending a message by one process and b is the event of receiving that message by another process, then a  b. 
3) If a  b and b  c then a  c. 

7. 
![](2018-12-01-Distributed-system-review-note/A9763A84-D62C-4366-9EE4-EACADCFC5839.png)
A write operation by a process on a data item x is completed before any successive write operation on x by the same process.
Hence: A write operation on a copy of item x is performed only if that copy has been brought up to date by means of any preceding write operation, which may have taken place on other copies of x. If need be, the new write must wait for old ones to finish.

Example: Updating a program at server S2, and ensuring that all components on which compilation and linking depends, are also placed at S2.

8. 
![](2018-12-01-Distributed-system-review-note/FE8FC450-19AE-42F4-A2AA-D0EB692ED0E8.png)
In both cases, we consider the normal case with no time outs.

In the decentralised version of the two-phase commit protocol:

No of messages:

Phase 1: coordinator sends its vote to N workers = N
Phase 2: each of N workers sends its vote to N others (N-1) workers + coordinator = N*N.
Total = N*N + N.

No. of rounds:

coordinator to workers + workers to others = 2 rounds.
Advantages: the number of rounds is less than for normal two-phase commit protocol which requires 3.

Disadvantages: the number of messages is far more: N*N + N instead of 3N.

## answer for 170110
1. 
![](2018-12-01-Distributed-system-review-note/22703E18-78E8-4C82-B046-B35A55EC79FC.png)

Middleware
Additional layer atop of NOS implementing general- purpose services
The system can be extended and re- implemented in various ways
 An open system offers services according to standard rules that describe the syntax and semantics of those service.

2. 
![](2018-12-01-Distributed-system-review-note/B536D3A4-11A7-47A0-998A-07FBB40B4321.png)


Transient communication:A message is stored by the communication system only as long as the sending and receiving application are executing. 
Synchronous communication: block sending and receiving 

In transient synchronous communication there would scalability problems. Scalability is the ability for a distributed application to expand without affecting any of the application algorithms. The transient synchronous communication would have issues pertaining to geographical scalability. If the client and the server are placed in two far-away geographical locations it would take a considerable amount of time for the client to send a request and receive a reply. Because the client remains idle until it receives the reply there is a considerable waste of time, since the client can only resume after receiving the reply. If the system is always in idle mode all of the time as it is synchronous there would not be any room for scalability. 

This situation is actually simpler. An asynchronous send is implemented by having a caller append its message to a buffer that is shared with a process that handles the actual message transfer. Each time a client appends a message to the buffer, it wakes up the send process, which subsequently removes the message from the buffer and sends it its destination using a blocking call to the original send primitive. The receiver is implemented similarly by offering a buffer that can be checked for incoming messages by an application.

3. 
![](2018-12-01-Distributed-system-review-note/CD8DF069-089D-4C58-AF33-E03F22A6611C.png)

4. 
![](2018-12-01-Distributed-system-review-note/6452C47D-7D3E-464C-A296-38C51A5EA34B.png)

5. 
![](2018-12-01-Distributed-system-review-note/C0DD1024-A568-4EBC-9803-3838DA5504BC.png)

6. 
![](2018-12-01-Distributed-system-review-note/2733D805-DE6B-4093-BD8D-B69199EAEDB2.png)

7. 
![](2018-12-01-Distributed-system-review-note/F96253B9-03EE-41D3-983F-7107FE8B4DC6.png)

8. 
![](2018-12-01-Distributed-system-review-note/5532CF10-8F21-4F72-A322-9E809DF62C5C.png)

9. 
10.   

## answer for 170530
1. 
![](2018-12-01-Distributed-system-review-note/3455F8D3-99A0-49E3-A035-AFB91B638DF4.png)

Scalability
Scalability of a system can be measured along at least three different dimensions: 
– Size
– Geographically – Administratively 

skype


2. 

![](2018-12-01-Distributed-system-review-note/1F83FE79-C322-471D-8C25-872DE56E2FB7.png)


![](2018-12-01-Distributed-system-review-note/897233EA-8081-4CB3-A906-02C90BBD558B.png)

![](2018-12-01-Distributed-system-review-note/2E39DE97-D088-4834-B656-BF1D12957C24.png)


3. 
![](2018-12-01-Distributed-system-review-note/9B3F4F01-3D92-41A7-A5D0-B235546CFE2E.png)

4. 
![](2018-12-01-Distributed-system-review-note/230992A7-D4EB-4413-82B8-E89387032E9C.png)

5. 
![](2018-12-01-Distributed-system-review-note/F2E36F5C-30FF-42FE-B11E-DC44091F9D88.png)

6. 
![](2018-12-01-Distributed-system-review-note/400AE234-BEF5-4369-BC88-61C3F60FB35F.png)

7. 
![](2018-12-01-Distributed-system-review-note/E309DE82-FCB3-49FB-8EFF-75341DCAA82B.png)


lower than it.
and the bigger one.


## answer for 171102
1. 
![](2018-12-01-Distributed-system-review-note/DD481E56-4972-431A-9AD6-D17FA3AF71D9.png)

Geographically  transparency

2. 
![](2018-12-01-Distributed-system-review-note/AF31171A-14FB-4A2B-B177-8F6E6ADD3F70.png)
?
6. 
![](2018-12-01-Distributed-system-review-note/51DD5DFC-194E-45F6-AB14-69EE09F52F47.png)

a:
3*(n-1).  
2*(n-1)
n

b:
?

7. 
![](2018-12-01-Distributed-system-review-note/2CE3A2AF-090A-4DDA-B87B-BD2C2E8D27C4.png)

Writes Follow Reads

A data store is said to provide writes-follow-reads consistency, if the following holds:
A write operation by a process on a data item x following a previous read operation on x by the same process is guaranteed to take place on the same or a more recent value of x that was read.

Hence: any successive write operation by a process on a data item x will be performed on a copy of x that is up to date with the value most recently read by that process.

Example: See reactions to posted articles only if you have the original posting (a read .pulls in. the corresponding write operation).

8. 
![](2018-12-01-Distributed-system-review-note/268AF2D6-0CFE-46EB-B483-83912FDC6BC8.png)


11. 
![](2018-12-01-Distributed-system-review-note/FCC77B87-8BBC-4768-92A3-1ABFEC800FB2.png)
1. A coordinator multiasts a sync order CHECKPOINT- REQUEST 
2. When receiving it, taking a local checkpoint, queues any subsequent message and block the processes. 
3. ACK to coordinator
4. Coordinator multicast CHECKPOINT-DONE and 
allow all processes stop block. 

Recovery line is a most recent consistent global state from local available stable storages.. If these local states jointly do not form a recovery line, further rolling back is necessary.


## answer for 180112
1. 
![](2018-12-01-Distributed-system-review-note/B240DEDA-3D40-4DD8-859A-A8BC3FF1BE30.png)

2. 
![](2018-12-01-Distributed-system-review-note/513FCF9D-2E5F-465D-B45E-102B2AC2FF46.png)

 Consider a synchronous send primitive. A simple implementation is to
send a message to the server using asynchronous communication, and subsequently
let the caller continuously poll for an incoming acknowledgement or
response from the server. If we assume that the local operating system stores
incoming messages into a local buffer, then an alternative implementation is
to block the caller until it receives a signal from the operating system that a
message has arrived, after which the caller does an asynchronous receive.

7. 
![](2018-12-01-Distributed-system-review-note/52853590-8E3D-4B6C-8399-02A378DBBDC6.png)
A write operation by a process on a data item x is completed before any successive write operation on x by the same process.
Hence: A write operation on a copy of item x is performed only if that copy has been brought up to date by means of any preceding write operation, which may have taken place on other copies of x. If need be, the new write must wait for old ones to finish.

Example: Updating a program at server S2, and ensuring that all components on which compilation and linking depends, are also placed at S2.

8. 
![](2018-12-01-Distributed-system-review-note/3FA8B1A0-49B8-40FA-8957-7C43EF318FB3.png)
After a write operation, the corresponding data cached in clients other than the one performing the write is invalid (since it does not reflect the current contents of the file on the NFS server), but the other clients will not discover the discrepancy and may use the stale data for a period of up to 3 seconds (the time for which cached  blocks  are  assumed  to  be  fresh).  For  directories,  the  corresponding  period  is  30  seconds,  but  the consequences are less serious because the only operations on directories are to insert and delete file names.
Scenario:  any  programs  that  depend  on  the  use  of  file  data  for  synchronization  would  have  problems.  For example, program A checks and sets two locks in a set of lock bits stored at the beginning of a file, protecting records within the file. Then program A updates the two locked records. One second later program B reads the same locks from its cache, finds them unset, sets them and updates the same records. The resulting values of the two records are undefined

![](2018-12-01-Distributed-system-review-note/5C2ECCDF-288E-4B76-B904-87355F8B2877.png)

Failure masking by redundancy
 – Information redundancy* EX: FEC  forward error correction
– Time redundancy* EX: Actomatic repeat request, RR protocol 
 – Physical redunancy
EX: group processes, extra servers, replicating services. 

