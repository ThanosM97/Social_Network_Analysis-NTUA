# Study and Analysis of Complex Topological Networks
In this lab exercise we create complex topologies using the networkx library and study them using multiple metrics. Furthermore, we examine the threshold behavior of the topologies in regard to their connectivity and the evolution of the Watts-Strogatz model in regard to the probability of rewiring. Finally, we examine the analogy between the Gilbert and the Erdos-Renyi model for Random Graphs.

## Network models and parameters

<table width="80%">
    <thead>
    <tr>
        <th>Network type</th>
        <th>Model</th>
        <th>ID</th>
        <th>Parameters</th>
    </tr>
    </thead>
    <tbody>
        <tr>
            <td style="background-color:#F2F4F7" rowspan="2">Grid</td>
            <td style="background-color:#F2F4F7" rowspan="2">Finite</td>
            <td style="background-color:#F2F4F7" rowspan="2">REG</td>
            <td style="background-color:#F2F4F7">Nodes <b>n</b></td>   
        </tr>
        <tr>
            <td style="background-color:#F2F4F7">Degree <b>d</b></td>
        </tr>
        <tr>
            <td style="background-color:#FFFFFF" rowspan="2">Random Graph</td>
            <td style="background-color:#FFFFFF" rowspan="2">Erdos-Renyi</td>
            <td style="background-color:#FFFFFF" rowspan="2">RG(ER)</td>
            <td style="background-color:#FFFFFF">Nodes <b>N</b></td>   
        </tr>
        <tr>
            <td style="background-color:#FFFFFF">Edges <b>M</b></td>
        </tr>
        <tr>
            <td style="background-color:#F2F4F7" rowspan="2">Random Graph</td>
            <td style="background-color:#F2F4F7" rowspan="2">Gilbert</td>
            <td style="background-color:#F2F4F7" rowspan="2">RG(G)</td>
            <td style="background-color:#F2F4F7">Nodes <b>n</b></td>   
        </tr>
        <tr>
            <td style="background-color:#F2F4F7">Edge probability <b>p</b></td>
        </tr>
        <tr>
            <td style="background-color:#FFFFFF" rowspan="3">Random Geometric Graph</td>
            <td style="background-color:#FFFFFF" rowspan="3">Flat</td>
            <td style="background-color:#FFFFFF" rowspan="3">RGG</td>
            <td style="background-color:#FFFFFF" >Area <b>L x L</b></td>   
        </tr>
        <tr>
            <td style="background-color:#FFFFFF" >Radius <b>R</b></td>
        </tr>
        <tr>
            <td style="background-color:#FFFFFF">Nodes <b>n</b></td>  
        </tr>
        <tr>
            <td style="background-color:#F2F4F7" rowspan="2">Scale-free</td>
            <td style="background-color:#F2F4F7" rowspan="2">Barabasi-Albert</td>
            <td style="background-color:#F2F4F7" rowspan="2">SF(BA)</td>
            <td style="background-color:#F2F4F7">Nodes <b>n</b></td>   
        </tr>
        <tr>
            <td style="background-color:#F2F4F7">Degree of the initial grid <b>d</b></td>
        </tr>
        <tr>
            <td style="background-color:#FFFFFF" rowspan="3">Small-world</td>
            <td style="background-color:#FFFFFF" rowspan="3">Watts-Strogatz</td>
            <td style="background-color:#FFFFFF" rowspan="3">SW(WS)</td>
            <td style="background-color:#FFFFFF">Nodes <b>n</b> </td>   
        </tr>
        <tr>
            <td style="background-color:#FFFFFF" >Degree of the initial grid <b>d</b></td>
        </tr>
        <tr>
            <td style="background-color:#FFFFFF">Probability of rewiring <b>g<sub>p</sub></b></td>  
        </tr>
    </tbody>
</table>

## Metrics
- Node degree
- Node strength
- Average path length
- Clustering coefficient
- Node centralities:
  - Degree centrality
  - Closeness centrality
  - Betweenness centrality
  - Eigenvector centrality
- Ego-betweenness centrality

In order to calculate the ego-betweenness centrality we use the algorithm described in the paper [Ego network betweenness](https://www.sciencedirect.com/science/article/abs/pii/S037887330400067X) by Martin Everett and Stephen P.Borgatti

## Connectivity and Threshold Behavior
Using the parameters below, we study the connectivity of each graph from the table above.
<table width="80%">
    <thead>
        <tr>
            <th width="20%">Topology</th>
            <th width="20%">Range</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td >REG</td>
            <td rowspan=6><b>n = {100,200}</b></td> 
            <td><b>d &#8712; [2,10] </b> with step <b>2</b></td>
        </tr>
        <tr>
            <td>RGER</td>
            <td><b>M &#8712; [100,800]</b> with step <b>100</b></td>
        </tr>
        <tr>
            <td>RG</td>
            <td><b>p &#8712; [0.1,0.9]</b> with step <b>0.1</b></td>
        </tr>
        <tr>
            <td>RGG</td>
            <td><b>R &#8712; [0.025,0.25]</b> with step <b>0.025</b> and <b>L=1</b></td>
        </tr>
        <tr>
            <td>SF</td>
            <td><b>d &#8712; [2,10]</b> with step <b>2</b></td>
        </tr>
        <tr>
            <td>SW</td>
            <td><b>d &#8712; [2,10]</b> with step <b>2</b> and <b>g<sub>p</sub> &#8712; [0.1,0.7]</b> with step <b>0.1</b></td>
        </tr>
    </tbody>
</table>


