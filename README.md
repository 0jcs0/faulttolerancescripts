# Analyze the fault tolerance of Virtual Police Stations

# Cite Us
```
Development of an Ontology to Address the Phishing Technique in Computer Crime: A contribution to Public Security Security
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

### didactic repository for pattern recognition:

-	It is not within the scope of this package to create the database. A third party has already created the learning repository. This structure follows the methodology of the ELM inventors.
-	In the path **dataset/classification/diabetes_train**, you can see the structure of the repository as shown in Fig. 5. 
    - **First column**: 1; the sample (row) belongs to the class. 0; the sample (row) belongs to the counter-class.
    - **Other columns**: input attributes (neurons) referring to features of the target application. In this diabetes_train, there are 8 input neurons. For example, in the first sample (row), the first neuron has a value of 0.11764700.
- At the end of learning (training), the ELM neural network will be capable of generalization. The ELM will classify the unseen sample as either class (1.0) or counter-class (0.0). An unseen sample refers to a sample not presented during training.

### Authorial repository for pattern recognition:

-	In the path **dataset/classification/Antivirus_Dataset_PE32_Citadel_mELM_format.csv**, you can see the structure of the repository as shown in Fig. 6.
    - **First column**: The application's name. The applications and their respective raw analyses are in the [Citadel repository](https://github.com/DejavuForensics/Citadel).
 	- **Second column**: 1; the sample (row) belongs to the class malware (Citadel). 0; the sample (row) belongs to the counter-class (serious app).
    - **Other columns**: input attributes (neurons) referring to features of the target application. In this diabetes_train, there are 430 input neurons. For example, in the first sample (row), the first neuron has a value of 0.
- At the end of learning (training), the ELM neural network will be capable of generalization. The ELM will classify the unseen sample as either class (1.0) or counter-class (0.0). An unseen sample refers to a sample not presented during training.

### Parameters of the extreme learning machine:

-    -tr: learning repository reversed to the training phase.
-    -ts: learning repository reversed to the testing phase.
-    -tall: learning repository, this includes the training and testing phase.
-    -ty:
        -    1: classification (pattern recognition). 
        -    0: regression (prediction: prediction with scientific-methodological rigor).
-    -nh: number of neurons in the hidden layer.
-    -af: activation function.
        - Kernel Linear (default): linear
        - Kernel mELM Dilation: dilation
        - Kernel mELM Erosion: erosion
        - Kernel Fuzzy-Erosion: fuzzy-erosion or fuzzy_erosion
        - Kernel Fuzzy-Dilation: fuzzy-dilation ou fuzzy\_dilation
        - Kernel Bitwise-Erosion: bitwise-erosion ou bitwise\_erosion
        - Kernel Bitwise-Dilation: bitwise-dilation ou bitwise\_dilation
        - Kernel Sigmoid: sig or sigmoid
        - Kernel Sine: sin or sine
        - Kernel Hard Limit: hardlim
        - Kernel Triangular Basis Transfer Function: tribas
        - Kernel Radial Basis Function: radbas
-    -sd: random number generator seed.
-    -v: verbose output.
-    In the console, use the extreme neural network in didactic repository. Here's an example:
```
python melm.py -tr dataset/classification/diabetes_train -ts dataset/classification/diabetes_test -ty 1 -nh 100 -af dilation -v
```
-    In the console, use the extreme neural network in a real repository. Here's an example:
```
python melm.py -tall dataset/classification/Antivirus_Dataset_PE32_Citadel_mELM_format.csv -ty 1 -nh 500 -af dilation -v
```
