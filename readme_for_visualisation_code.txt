README for plot_communities_xx.py file

REQUIREMENTS: 1. python3
              2. The very latest version of matplotlib (for good color scheme), and 
              3. networkx.
              If matplotlib is not the latest version, you can upgrade it using pip3 install --upgrade matplotlib


The python file has 2 main functions with which we will interact with. Others are auxiliary functions.

1. align_communities()
  This function relabels the nodes so that all nodes of one community are bunched together spatially. 
  In the original graph, the nodes of a community can be scattered anywhere from 1 to 100.
  
  * Usage: out_commu, ml_network, translation = align_communities(in_commu, ml_network) 
  * Input: in_commu & ml_network is simply the communities that we read from ml_network.pickle files
  * Output:
      out_commu is a dict of the form commu[node] = communitynumber. It stores community of each node.
      ml_network is the undirected networkx graph
      translation is the most crucial element here. While aligning communities, nodes have been relabeled.
      translation is a dict which stores this relabeling information - translation[oldlabel] = newlabel

2. draw_graph_from_nx(ml_network, commu, plotname, title)
   
   This function will draw the two layer plot. The ml_network is the network returned by align_communities 
   function earlier. 

NETWORK INPUT: network file paths can be specified in the variables from lines 214 to 220

The pickle files for ground truth, Louvain and GN were each slightly different. 
To read these 3 kinds of files and draw network, codes, with comments are on the following lines:
Ground Truth : Line 221
GN : Line 240
Louvain : Line 253
