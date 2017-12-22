# Single-Source-Shortest-Distance-using-Spark

Spark program in Scala project4/Source.scala to solve the single source shortest distance problem using Spark: for each node in a directed graph, calculate the shortest distance from the node with id=0 to this node. The input directed graph is a dataset of edges, where an edge from the node i to the node j is represented in the input text file as:

i,d,j
where d is the distance from node i to node j. (Numbers i,j, and d are long integers.) Let distance[i] be the shortest distance from the node with id=0 to the node with id=i. The pseudo-code to calculate distance[i] is as follows:
distance[0] = 0
for each node i <> 0:
    distance[i] = Long.MAX_VALUE
repeat 4 times:
    for each edge (i,d,j):
        if distance[j] > distance[i]+d
           distance[j] = distance[i]+d
Your code that calculates the new distances from the old must be repeated 4 times only.
Hint: You may want to group edges by their destination as a triple (j,distance[j],{(i1,d1),(i2,d2),...}), which are derived from the edges (i1,d1,j),(i2,d2,j),...
, where distance[j] is initially Long.MAX_VALUE.
An empty project4/Source.scala is provided, as well as scripts to build and run this code on Comet. You should modify Source.scala only. Your main program should take two arguments: args(0) is the input graph and args(1) is the output. The output should look like:

i,d
where d is the shortest distance from node 0 to node j. The small graph small-graph.txt is used for testing in local mode and the moderate-sized graph large-graph.txt is used for testing in distributed mode. The output for the small graph should be:
0 0
1 2
2 3
3 5
