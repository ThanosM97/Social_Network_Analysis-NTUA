# Analysis of Real Topologies and Community Detection
This lab exercise was split into two parts. 

## Part A: Analysis of Real Topologies
In the first part we created the artificial topologies of Lab 1, but also imported some real topologies found on [Network Data](http://www-personal.umich.edu/~mejn/netdata/). The goal was to analyze both the artificial and the real complex topologies using the metrics from Lab 1 and some additional metrics in order to study the social structure of those networks.

### Real Topologies
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

Then, for each of the real topologies we had to find the artificial model that best simulates it. <br>
**Results:**
|       Real Topology       | Artificial Model |
|:-------------------------:|:----------------:|
| American College Football |    Small World   |
|       Les Miserables      |    Scale Free    |
|          Dolphins         |    Small World   |

## Part B: Community Detection
In the second part of this lab we used the community detection algorithms in the table below on all of the graphs, both real and artificial. Then we compared their performances using the following metric: <br>
**Modularity** - [networkx.algorithms.community.quality.modularity](https://networkx.github.io/documentation/stable/_modules/networkx/algorithms/community/quality.html)

### Community Detection Algorithms
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
