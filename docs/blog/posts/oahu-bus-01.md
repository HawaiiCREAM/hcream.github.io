---
date: 2024-12-30
authors: [alan]
categories:
  - Bus Transit
---

# Using Network Analysis to Research the Oahu Bus Network
## Motivation
The Downs---Thompson paradox states the following: the equilibrium speed of car traffic on a road network is determined by the average door-to-door speed of equivalent journeys taken by public transport. In other words, the speed of all traffic on a road is controlled by the speed of the public transportation along that road. It is a paradox because worsening the road for private driver to improve public transportation will create more motivation to use public transportation, improving private transportation as well. This motivates research improving bus transportation in high traffic areas, such as that of Honolulu, Hawai'i. Honolulu ranks 18th worst city in the United States for the annual global traffic scorecard for 2023 by INRIX.

City bus networks are comprised of a set amount of bus stops and bus routes carrying passengers between the bus stops according to a fixed time schedule. This schedule is publicly available for almost every city bus system, with Honolulu as no exception. Therefore, Honolulu is a valid choice to perform a network analysis on.

One may perform a network analysis on a bus network by setting bus stops as vertices and bus routes connecting bus stops as edges. This creates a directed graph with multiple edges between vertices. With this structure, one may then perform a mathematical analysis of the graph and its structure.

## Method
Our work revolves around the public General Transit Feed Specification (GTFS) schedule provided by the Oahu Transportation Service. This information details bus stops by an identification number, longitude, latitude, and a street name label---this derives the vertices for a bus network. The information also details bus routes connecting the stop identification numbers, with a corresponding bus route identification number and a time table---this derives the edges for the bus network.

We created a code that allows one to convert a GTFS directory into two comma separated values files (.csv), a vertices list and edge list. These files may then be imported into a graph visualization program, such as that of Gephi, a free open source software. From here, a proper graph file may be exported (.graphml), then imported into iGraph on R. From here, calculations are done strictly in R.

This process creates a multi-edge directed network. For now, we are more interested in the topology of the network and not specific times or scheduling; we may simplify the network, collapsing parallel edges and removing self-loops. We then create edge weights based on the physical distance calculated by longitude and latitude.

This network may be plotted, using a layout determined by the longitude and latitude of the vertices. This creates a geographic layout of the bus stops. with edges directly connecting between them.

From here, standard network analysis metrics may be computed, such as that of the vertex count, edge count, mean degree, and rankings by degree. This allows up to highlight important bus stops relevant to the graph.

Comparison to similar random generated network models will explain the important properties of the natural bus network. This allows us to determine that some properties of the bus network are not inherit from the properties used to generate the random graphs.

A degree distribution and power-law fit is necessary, as transportation systems often use the word hub to describe transit centers. Therefore, one may expect to see the network follow a power law.

Centrality metrics may be compared. These centrality metrics measure importance of vertices in different ways. Therefore, we may determine the importance of bus stops through these different metrics.

The Leiden community detection algorithm will be applied to the network to determine the communities as seen through the lens of the urban transit system. Analysis of communities through the lens of transit systems is an effective way of loosely partitioning a state. Society functions through movement; the movement of people can be recognized as the routes of public transportation, so community detection of bus transit networks describes districts in terms of movement.

## Results
Will post later.
