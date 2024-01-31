SOCIAL NETWORK ANALYSIS

In this project, we will see the process of generating a social network graph and how we analyze 
the Facebook social network by using a tool called NetworkX in Python.
Social network analysis (SNA) studies the relationships and interactions among 
individuals, groups, organizations, or any other social entities. It involves the analysis of social 
networks, which are composed of nodes (representing social entities) and edges (representing 
relationships or connections between entities). SNA examines how these networks are structured, how 
information or resources flow through them, and how behaviors, ideas, or influence spread within 
them.

DATASET 

https://snap.stanford.edu/data/ego-Facebook.html
This dataset is collected through a survey by Stanford University. Facebook data was collected from 
survey participants using this Facebook app. The dataset includes node features (profiles) and edges.
Facebook data has been anonymized by replacing the Facebook-internal IDs for each user with a new 
value. And, the edges will have no direction. 
This dataset is not a .csv file it is network data and to read this kind of file and to work on it 
there is a Python library “NetworkX”. Let us see about it.

NetworkX

https://networkx.org/
NetworkX is a Python package for the creation, manipulation, and study of the structure, dynamics, 
and functions of complex networks. NetworkX allows users to create and manipulate networks 
represented as graphs, which consist of nodes connected by edges. It provides functions for adding, 
removing, and modifying nodes and edges, as well as for computing various network properties such 
as degree, centrality, clustering coefficient, and more.

Basic features of the dataset

Graph Information:
Number of nodes: 4039
Number of edges: 88234

Graph statistics: 

Density: 0.010819963503439287
Average degree: 43.69101262688784
Number of connected components: 1
Is connected: True
NODE: Nodes represent individual entities, in this case in our data it represents individuals.
EDGE: Edge is a connection between two nodes.
DIRECTED: For every network the edge might or might not represent a direction, in this network it is 
undirected.
DENSITY: Ratio of number of edges in the graph to the total number of possible edges in the graph.
AVERAGE DEGREE: Total number of edges divided by total number of nodes.

SHORTEST PATHS

In any social network, it is crucial to find out the shortest paths between two nodes or two individuals 
to make a possible and effective connection between the nodes. For instance, in social networks, 
finding the shortest path between two individuals can help identify the most efficient path for 
spreading information, influence, or resources between them.

We have created a dictionary that has the lengths of the shortest paths 
between all pairs of nodes. The mean represents the average connectivity of each node to the 
number of edges, to state this simply on average a single node is connected to 44 other nodes.


This insight can be very useful when we would know what is the path between two nodes and this 
could be very helpful in social networks for suggesting friends or suggesting content on social media. 
In the code, we can enter the source node and the target node dynamically at the runtime.
Diameter:
diameter = max(nx.eccentricity(GI, sp=shortest_path_lengths).values())
diameter
Output:
8
This 8 represents to travel between any two nodes in the network we may travel 8 edges or fewer.

CENTRALITY MEASURES

Centrality measures are mathematical metrics used to identify and quantify the importance or 
significance of individual nodes within a network. Simply we can say Node importance.
Node importance:
"Node importance" also known as node centrality is a measure of how crucial a node can be in forming 
the network or graph. There are quite a few ways to know the node importance in networks but in this 
project, we are limiting it to four, they are:
1. Degree Centrality
2. Betweenness Centrality
3. Closeness Centrality
4. Community Detection
   
DEGREE CENTRALITY

Degree centrality is defined as the number of edges or connections that a node has in a network. This 
is often used to identify the most connected or influential nodes in a network. Nodes with high degree 
centrality are considered more central, as they have more connections and are likely to have more 
influence over the flow of information, resources etc. they are very crucial for spreading information, 
controlling the flow of information within the network.

Degree Centrality of a node = No. of edges connected to the node / (Total number of nodes in the 
network - 1)

BETWEENNESS CENTRALITY

Betweenness centrality is a measure of the importance or centrality of a node in a network based on 
the concept of shortest paths. It quantifies the extent to which a node lies on the shortest paths 
between pairs of other nodes in the network. It can be used in various applications, such as identifying 
important individuals in social networks, critical nodes in transportation networks, or key proteins in 
biological networks.

CLOSENESS CENTRALITY

Closeness centrality measures how easily a node can access other nodes in the network. Nodes with 
higher closeness centrality values are typically located in central or well-connected areas of the 
network and can quickly transmit information or influence to other nodes. It simply quantifies the 
average shortest path distance from a node to all the other nodes in the network.
The closeness centrality measure is very important for the monitoring of the spread of false 
information (e.g., fake news). Let us examine the example of fake news. If the user with the highest 
closeness centrality measure started spreading some fake news information (sharing or creating a 
post), the whole network would get misinformed the quickest possible. However, if a user with very 
low closeness centrality would try the same, the spread of the misinformation to the whole network 
would be much slower. That is because the false information would have to firstly reach a user with 
high closeness centrality that would spread it to many different parts of the network.

COMMUNITY DETECTION

Community detection, also known as clustering or partitioning. This is used to identify groups or 
communities of nodes that are densely connected within themselves but less connected with nodes 
outside the group. These communities are often considered as "modules" or "clusters" within the 
network, and their identification can provide insights into the underlying structure and organization of 
the network.

In our network we observed the network is divided into 15 communities. The communities are 
detected by modularity which basically is the measure of structure of graphs, measuring the density 
of connections within the module or community. Community detection can help identify groups or 
communities within social networks, such as groups of friends, interest groups, or communities of 
practice. This can provide insights into the structure and dynamics of social relationships, information 
diffusion, and social influence processes.

