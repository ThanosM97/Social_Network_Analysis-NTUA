# Genetic Algorithms
This lab exercise was split into two parts.

## Part A: ONEMAX problem
The ONEMAX is a toy problem designed for introduction to Genetic Algorithms. It gives a basic intuition of how we construct a genetic algorithm and the ways with which we can optimize its performance.

**ONEMAX**: Find the binary sequence (x<sub>1</sub>, x<sub>2</sub>, ..., x<sub>n</sub>) that maximizes the sum (x<sub>1</sub>, x<sub>2</sub>, ..., x<sub>n</sub>). 

We analyze the effect of the population size, the crossover probability and the mutation probability in the performance of the algorithm's solution (how close it is to the optimal solution).

### Parameters

| Variable              |           Range           |
|-----------------------|:-------------------------:|
| Population size       |   [10,100] with step 10   |
| Crossover probability |  [0.3,0.9] with step 0.1  |
| Mutation probability  | [0.01,0.2] with step 0.01 |

## Part B: Community detection in Social Network Graphs using Genetic Algorithms
In this part of the lab we implemented a community detection genetic algorithm ([GA-Net](https://link.springer.com/chapter/10.1007/978-3-540-87700-4_107)). Then we used this algorithm in order to detect communities in real networks and compared our results with the results of the algorithms in Lab2.

### Networks
Real topologies found on <a style=text-decoration:none href="http://www-personal.umich.edu/~mejn/netdata/">http://www-personal.umich.edu/~mejn/netdata/</a> 

<table style=width:100%>
<tr>
    <th style=text-align:left>Topology</th>
    <th style=text-align:left>File</th>
    <th style=text-align:left>Description</th>
</tr>
<tr>
    <td style=text-align:left>American College Football</td>
    <td style=text-align:left><a style=text-decoration:none href='http://www-personal.umich.edu/~mejn/netdata/football.zip'>football.gml</a></td>
    <td style=text-align:left><p style=text-align:justify> The file <b>football.gml</b> contains the network of American football games between Division IA colleges during regular season Fall 2000, as compiled by M. Girvan and M. Newman. The nodes have values that indicate to which conferences they belong.</p>
    </td>
</tr>
<tr>
    <td style=text-align:left>Les Miserables</td>
    <td style=text-align:left><a style=text-decoration:none href='http://www-personal.umich.edu/~mejn/netdata/lesmis.zip'>lesmis.gml</a></td>
    <td style=text-align:left><p style=text-align:justify> The file <b>lesmis.gml</b> contains the weighted network of coappearances of
characters in Victor Hugo's novel "Les Miserables".  Nodes represent characters as indicated by the labels and edges connect any pair of characters that appear in the same chapter of the book.  The values on the edges are the number of such coappearances.  The data on coappearances were taken from D. E. Knuth, The Stanford GraphBase: A Platform for Combinatorial Computing, Addison-Wesley, Reading, MA (1993)</p>
    </td>
</tr>  
<tr>
    <td style=text-align:left>Dolphin social network</td>
    <td style=text-align:left><a style=text-decoration:none href='http://www-personal.umich.edu/~mejn/netdata/dolphins.zip'>dolphins.gml</a></td>
    <td style=text-align:left><p style=text-align:justify> The file <b>dolphins.gml</b> contains an undirected social network of frequent associations between 62 dolphins in a community living off Doubtful Sound, New Zealand, as compiled by Lusseau et al. (2003)</p>
    </td>
</tr> 
</table>

### Parameters for the Genetic Algorithm

<table style=width:100%>
<tr>
    <th style=text-align:left>Parameter</th>
    <th style=text-align:left>Values</th>
</tr>
<tr>
    <td style=text-align:left>Crossover <b>p<sub>c</sub></b></td>
    <td style=text-align:left><b>[0.7,0.9]</b> with step <b>0.1</b></td>
</tr>
<tr>
    <td style=text-align:left>Mutation <b>p<sub>M</sub></b></td>
    <td style=text-align:left><b>{0.1,0.2}</b></td>
</tr>
<tr>
    <td style=text-align:left>Elitism <b>x</b></td>
    <td style=text-align:left><b>[1,3]</b> with step <b>1</b></td>
</tr>
</table>

### Common Community Detection Algorithms
<table style=float:left;width:70%>
    <tr>
        <th style=text-align:left> Community detection algorithm</th>
        <th style=text-align:left>Function</th>
    </tr>
    <tr>
        <td style=text-align:left>Spectral Clustering</td>
        <td style=text-align:left><a style=text-decoration:none href='http://scikit-learn.org/stable/modules/generated/sklearn.cluster.SpectralClustering.html'>SpectralClustering</a></td>
    </tr>
       <tr>
        <td style=text-align:left>Newman-Girvan</td>
        <td style=text-align:left><a style=text-decoration:none                               href='https://networkx.github.io/documentation/latest/reference/algorithms/generated/networkx.algorithms.community.centrality.girvan_newman.html'>girvan_newman</a></td>
    </tr>
    <tr>
        <td style=text-align:left>Modularity Maximization</td>
        <td style=text-align:left><a style=text-decoration:none                               href='https://networkx.github.io/documentation/latest/reference/algorithms/generated/networkx.algorithms.community.modularity_max.greedy_modularity_communities.html'>greedy_modularity_communities</a></td>
    </tr>
</table>

### Performance metric

Modularity - [networkx.algorithms.community.quality.modularity](https://networkx.github.io/documentation/stable/_modules/networkx/algorithms/community/quality.html)

### Results

| Community Detection Algorithm \ Graph | American College Football                                | Les Miserables                                         | Dolphins                                                |
|-------------------------------|----------------------------------------------------------|--------------------------------------------------------|---------------------------------------------------------|
| Genetic Algorithm             | **10 communities** with modularity score **0.42777610712964126** | **9 communities** with modularity score **0.5330305660611323** | **5 communities** with modularity score **0.519382144693642**   |
| Girvan-Newman                 |  **10 communities** with modularity score **0.5996290274077911** | **11 communities** with modularity score **0.538068076136153** | **6 communities** with modularity score **0.4949764645385849**  |
| Spectral Clustering           |  **11 communities** with modularity score **0.6022010863056777** | **7 communities** with modularity score **0.5382230764461532** | **4 communities** with modularity score **0.49549068470392815** |
| Modularity Maximization       | **6 communities** with modularity score **0.5497406651426727**   | **5 communities** with modularity score **0.5005967511935037** | **6 communities** with modularity score **0.49202958743720376** |


We can see that the modularities calculated for the communities given by the genetic algorithm are quite similar to the modularities of the common community detection algorithms of Lab2 for all of the topologies. 


