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
Figure 1 illustrates this. 
Furthermore, the DNS protocol allows distributing the same domain among different servers.
If one of these servers fails, the others continue to offer the same service on the World Wide Web. The DNS protocol enables _n:m_ mapping between IP addresses and domains. 1 (one) IP address can be linked to _n_ domains and 1 (domain) can be linked to _m_ IP addresses. The DNS protocol allows for mirroring the same content on different servers. Storing the same content on several servers is essential for high-demand, high-volume data. It's an aspect of fault tolerance. 
If one server stops working, the others will continue to provide the same service on the World Wide Web. Load balancing is also an advantage. If a server becomes overloaded, the servers can balance the workload. Response times are also reduced. The system chooses the server closest to the request by default. This optimizes the service's response time.
We developed scripts to examine the number of servers at each police station.

![Illustrated operation of the DNS protocol](https://github.com/0jcs0/faulttolerancescripts/blob/main/Images/1.png)
Figure 1.: Illustrated operation of the DNS protocol. 

## Follow the instructions:
### Installation and handling of auxiliary libraries:

-	In the console, install the _dnspython_ library responsible for requesting DNS servers.
```  
pip install dnspython
```

-	In the console, install the _pygeoip_ library responsible for detecting the geolocation of an IP address..
```  
pip install pygeoip
```

-	Install the _mgrs_ library in the console. It detects the geolocation of an IP address using MGRS, the Military Grid Reference System. MGRS was developed by the NATO military. The benefit of MGRS is that it allows grid designation of **a geographic point below one square metre**.
```  
pip install mgrs
```

-	Install the _pytz_ library in the console. The library calculates the time zone of a given region where the IP address is located.
```  
pip install pytz
```

-	In the console, install the _berserker_resolver_ library. It determines all the IP addresses linked to a given domain.
```  
pip install berserker_resolver
```

### Parameter to use the authorial script.

We developed scripts to examine the number of servers at each police station in Brazilian Northeast. The findings reveal that the State Technology Agencies administer the Virtual Police Stations. The states with these stations include Ceará, Paraíba, Pernambuco, and Maranhão. These precincts face delays, as noted. This is due to insufficient load balancing and lack of data replication. This increases the risk of service downtime due to agency failures. Also, these systems lack data replication. This makes them more susceptible to denial of service attacks. Yet, police stations in Alagoas, Bahia, Piauí, Rio Grande do Norte, and Sergipe use Service Data Process (SERPRO) in Brasilia. They had no delays and have data replication.  

- In the console, to analyse the virtual police stations in the states of; Alagoas, Bahia, Piauí, Rio Grande Do Norte and Sergipe.
```
python FFanalyse.py -d delegaciavirtual.sinesp.gov.br 
```

- In the console, to analyse the virtual police stations of Pernambuco state.
```
python FFanalyse.py -d servicos.sds.pe.gov.br > Pernambuco.txt
```

- In the console, to analyse the virtual police stations of Paraíba state.
```
python FFanalyse.py -d delegaciaonline.pb.gov.br 
```

- In the console, to analyse the virtual police stations of Ceará state.
```
python FFanalyse.py -d www.delegaciaeletronica.ce.gov.br
```

- In the console, to analyse the virtual police stations of Maranhão state.
```
python FFanalyse.py -d delegaciaonline.policiacivil.ma.gov.br
```
## Feature Extraction


The extraction should catalogue the number of IP addresses linked to the audited domain. Server mirroring is a practice used by both legitimate and illegitimate servers. This observation is particularly relevant. Distributed denial of service attacks can coordinate multiple servers in a synchronized manner. This coordination can be exploited to promote industrial sabotage. It poses a significant threat to the integrity and operation of the target server. A thorough understanding of IP address characteristics contributes to cyber security. It also highlights the need for preventative strategies to counter potential coordinated attacks.

### Domain with multiple servers

Figure 2 shows that a domain can be linked to _n_ multiple servers with the same replicated content. 

![A domain can be linked to _n_ different servers with the same replicated content](https://github.com/0jcs0/faulttolerancescripts/blob/main/Images/2.png)

</center>

Figure 2.: A domain can be linked to _n_ different servers with the same replicated content. 

### TTL(Time to Live)

TTL (Time to Live) is the number of hops packets can make in a computer network before being discarded. It refers to the number of jumps between machines. The TTL value and service efficiency have an inverse relationship. This is an important consideration. A higher TTL indicates that packets may take longer to travel across the network. This suggests a possible slowdown in the service. This slowness can be attributed to the absence of effective fault tolerance mechanisms. Understanding the impact of TTL provides insights into the importance of proactive measures. This is to optimize the performance and resilience of the network infrastructure. Services concentrated on a single IP address can have a high TTL. Consequently, they can have a slow response time.

### Geolocalisation of IP address(es)

We are working on geolocalising IP addresses. This script provides information about IP addresses. It includes mapping for 250 countries. It also includes latitude, longitude and other geoinformation related to an IP address.

### Timezone

The term "Timezone" refers to the geographical location of the IP address's time zone. In this context, Greenwich Meridian Time (GMT) acts as a central reference point. It represents the zero base value. The assignment of values to each time zone is determined by its distance from GMT.
Figure 3 illustrates the Greenwich Meridian timezones. 

![Illustration of the Greenwich Meridian timezones](https://github.com/0jcs0/faulttolerancescripts/blob/main/Images/3.png)

</center>

Figure 2.: Illustration of the Greenwich Meridian timezones.

### UTM

### MGRS
