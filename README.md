# Analyze the fault tolerance of Virtual Police Stations

# Cite Us
```
Development of an Ontology to Address the Phishing Technique in
Computer Crime: A contribution to Public Security Security
```

# Theoretical background 

A theoretical background is essential to explain why virtual police stations lack preparation. At the dawn of the Internet, users accessed a server via IP addresses. IP addresses are also known as Internet Protocol Addresses.
To simplify human-machine interaction, domains replaced IP addresses. In contemporary times, users type the domain into the browser, like _www.example.com_. This makes the experience more accessible and user-friendly.
The DNS (Domain Name System) protocol determines the IP address of the web server. It does this when someone types a domain like www.example.com into a browser. The web server (_www_) associates the IP address. In this case, it’s for the domain _example.com_.
This search proceeds recursively between servers at different levels. It continues until one provides the requested address. When the server receives a request, it searches its registry for the mapping. If it can't find one, it tells you what server to use for the domain.

The DNS protocol aims to provide a mapping between domain names and IP addresses. This functionality allows a server with just one IP address to have several domains. This is also called _domain aliasing_. Too, DNS makes it possible to access a single web server via different domains. 
Figure~\ref{fig:botnet_protocolo_dnd} illustrates this. 
Furthermore, the DNS protocol allows distributing the same domain among different servers.
If one of these servers fails, the others continue to offer the same service on the World Wide Web. The DNS protocol enables _n:m_ mapping between IP addresses and domains. 1 (one) IP address can be linked to _n_ domains and 1 (domain) can be linked to _m_ IP addresses. The DNS protocol allows for mirroring the same content on different servers. Storing the same content on several servers is essential for high-demand, high-volume data. It's an aspect of fault tolerance. 
If one server stops working, the others will continue to provide the same service on the World Wide Web. Load balancing is also an advantage. If a server becomes overloaded, the servers can balance the workload. Response times are also reduced. The system chooses the server closest to the request by default. This optimizes the service's response time.
We developed scripts to examine the number of servers at each police station.


## Follow the instructions:
### Installation and handling of auxiliary libraries:

-	In the console, install the _dnspython_ library responsible for requesting DNS servers.
```  pip install dnspython  ```