# ngraph.coarsen

Given a community structure creates a coarse graph

# usage

``` js
// Let's say you have detected community of a graph using
// ngraph.cw or ngraph.modularity:
var community = detectCommunities(srcGraph);

// To build a coarse graph:
var coarsen = require('ngraph.coarsen');
var coarseGraph = coarsen(srcGraph, community)
```

Each node in the coarse graph is a community inside `srcGraph`. Link between
communities exists if members of each community are connected in the `srcGraph`.

* `node.data` property is a `Set` of node ids from the `srcGraph`;
* `link.data` is a number, that shows total number of connections (or weights)
between members of communities.

Note: each node in the coarse graph can also have a link with itself (a self-reference).
The weight of this link is equal to weight of all weights within community.

# See also

* https://github.com/anvaka/ngraph.graph - graph structure
* https://github.com/anvaka/ngraph.cw - label-propagation based community detection
* https://github.com/anvaka/ngraph.modularity - modularity optimization community
detection

# license

MIT