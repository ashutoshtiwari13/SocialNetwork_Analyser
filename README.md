# Analysis of Centrality -Finding Most Influential Person in a Social Network 

## Problem Statement

> If we want to know who is most central in a network, that seems like an easy question, just count how many people they are linked to, right? But what if they are only linked to people who are disconnected themselves? This provides a solution to this.



## Motivation
The edges described in the problem statement could be of any form: friendship, collaboration, following or mutual interests. Here, we specifically study and build our model over Facebook's social network, with the following areas of motivation:

* General application of friends recommendation to a particular user.
* Predicting hidden links in a social network group formed by terrorists along with identification of their leaders/ key influencers.
* Targeted marketing of products: Marketing through highly influential individuals and also identifying plausible customers.
* Suggesting promising interactions or collaborations that have not yet been identified within an organization. 

The following model can be extended or modified to cater to the needs of various other social networks like Twitter, Google+, Foursquare, etc.

Discussed below are the four major Tasks:

### Acquisition & Learning
##### Data: 
* Acquired from http://snap.stanford.edu/data/egonets-Facebook.html

* This dataset consists of 'circles' (or 'friends lists') from Facebook.

* This anonymized dataset includes node features (profiles), circles, and ego networks.

* The edges are **undirected** .

*  10 ego-networks, consisting of 193 circles and 4,039 users.

*  Features of various nodes are described in the following format:` [Type]:[Subtype]:attributeName` 

*  Following figure represents an example of the attributes and the procedure of feature array formation.




##### Task: 

> Given an unweighted, undirected graph `G = ⟨V,E⟩`  representing the topological structure of a social network in which each edge `e = ⟨u,v⟩ ∈ E`  represents an interaction between u and v that took place at a particular time `t(e)` , the two task can be described as:
>
> * **To find the highly influencing/ central node set N.**


### Representation:
##### Data: 

* In order to represent complex data structure of a graph with various features attached to each node, `python-igraph` has been used.
* `Dictionary Data Structure` is deployed to store the corresponding features of each node.

### Development and Explanation:
##### Approach:

* ***Measures for Centrality***  : As our part of analysis, we used the following 4 centrality measures:
  * `Degree of nodes` : 
    - Core idea: To find the nodes that have highest number of  immediate neighbors (degree)
    - Input: Graph and a node 
    - Output: Degree of nodes.
  * `Closeness Centrality` : 
    * Core idea: A central node is one that is close, on average, to other nodes.
    * Input: Graph and a node 
    * Output: value [0,1] after standardization (1 being highly central)
  * `Betweeness Centrality` :
    * Core Idea: A central actor is one that acts as a bridge, broker or gatekeeper.
    * Input: Graph and a node 
    * Output: value [0,1] after normalization (1 being highly central)
  * `Eigenvector centrality` :
    * Core Idea: A central actor is connected to other central actors.
    * Input: Graph
    * Output: value [0,1] 


##### Python Libraries used:

* `Plotly` : Graphing library for making interactive, publication-quality graphs online. 
* `python-iGraph` : igraph is a collection of network analysis tools with the emphasis on efficiency**, **portability and ease of use. igraph is open source and free. 
 - pip install <from here https://www.lfd.uci.edu/~gohlke/pythonlibs/#python-igraph >


## Replicating the results

In order to run the code provided :

* Download and Unzip the file or Clone the Repo 

* Setting up the environment for execution:

  * Python version 3 or above.
  * Install the python libraries as described in the previous section.

* Setting up the dataset and plotly account. Replace the usename and API key with your own. 


* To get the centrality measures and visualize the network:

  ```python
  python Centrality.py or open in Jupyter Notebook
  ```
