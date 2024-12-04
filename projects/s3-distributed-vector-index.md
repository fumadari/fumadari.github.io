---
layout: default
title: S3 Distributed Vector Index
---

# S3 Distributed Vector Index

## Overview

The **S3 Distributed Vector Index** is a cutting-edge cloud indexing system designed to handle billion-scale vector datasets with high efficiency and accuracy. Leveraging Amazon S3's parallelism capabilities, this project surpasses traditional indexing methods like DiskANN by implementing hierarchical clustering with HNSW graphs.

## Features

- **Scalability:** Efficiently manages and queries vector data at a billion-scale.
- **High Recall:** Achieves 90% recall at sub-second latency, ensuring fast and reliable data retrieval.
- **Hierarchical Clustering:** Utilizes HNSW (Hierarchical Navigable Small World) graphs for optimized indexing and search performance.
- **Cloud-Native:** Fully integrated with AWS services, ensuring seamless scalability and fault tolerance.

## Technical Details

- **Parallelism with S3:** Exploits S3's parallel data access to distribute indexing tasks, significantly reducing processing time.
- **Hierarchical Clustering:** Implements multi-level clustering to enhance search accuracy and speed.
- **HNSW Graphs:** Utilizes Hierarchical Navigable Small World graphs to facilitate efficient nearest neighbor searches.

## Performance

- **Recall:** 90% on a dataset of 1.5 million documents.
- **Latency:** Sub-second response times even with billion-scale data.
- **Comparison:** Outperforms DiskANN by X% in recall and Y% in query speed. *(Replace X and Y with actual metrics if available.)*

## Hierarchical Index Visualization

This visualization demonstrates the hierarchical structure of the index, showing how data is partitioned into clusters with centroids and how leaves are stored in S3.

<button id="simulate-query">Simulate Query</button>

{% raw %}
<!-- Visualization Container -->
<div id="hierarchical-index"></div>

<!-- D3.js Library -->
<script src="https://d3js.org/d3.v6.min.js"></script>

<!-- Visualization Script -->
<script>
// Set the dimensions and margins
var margin = {top: 20, right: 90, bottom: 30, left: 90},
    width = 660 - margin.left - margin.right,
    height = 500 - margin.top - margin.bottom;

// Append the SVG object
var svg = d3.select("#hierarchical-index").append("svg")
    .attr("width", width + margin.left + margin.right)
    .attr("height", height + margin.top + margin.bottom),
  g = svg.append("g").attr("transform", "translate(" + margin.left + "," + margin.top + ")");

// Create the tree layout
var treemap = d3.tree().size([height, width]);

var i = 0,
    duration = 750,
    root;

// Load the data
d3.json("{{ '/assets/data/hierarchical_index.json' | relative_url }}").then(function(data) {
  root = d3.hierarchy(data, function(d) { return d.children; });
  root.x0 = height / 2;
  root.y0 = 0;

  // Collapse after the second level
  // root.children.forEach(collapse);

  update(root);
});

function update(source) {
  // Assigns the x and y position for the nodes
  var treeData = treemap(root);

  // Compute the new tree layout.
  var nodes = treeData.descendants(),
      links = treeData.links();

  // Normalize for fixed-depth.
  nodes.forEach(function(d){ d.y = d.depth * 180});

  // ****************** Nodes section ***************************

  // Update the nodes...
  var node = g.selectAll('g.node')
      .data(nodes, function(d) { return d.id || (d.id = ++i); });

  // Enter any new modes at the parent's previous position.
  var nodeEnter = node.enter().append('g')
      .attr('class', function(d) {
          return 'node' + (d.children ? ' node--internal' : ' node--leaf');
      })
      .attr("transform", function(d) {
          return "translate(" + source.y0 + "," + source.x0 + ")";
      });

  // Add Circle for the nodes
  nodeEnter.append('circle')
      .attr('class', 'node')
      .attr('r', 10)
      .style("fill", function(d) {
          if (d.data.centroid) return "orange"; // Centroid nodes
          else if (d.children || d._children) return "#fff"; // Internal nodes
          else return "lightsteelblue"; // Leaf nodes
      });

  // Add labels for the nodes
  nodeEnter.append('text')
      .attr("dy", ".35em")
      .attr("x", function(d) {
          return d.children || d._children ? -13 : 13;
      })
      .attr("text-anchor", function(d) {
          return d.children || d._children ? "end" : "start";
      })
      .text(function(d) {
          if (d.data.centroid) return d.data.name + " (Centroid)";
          else if (!d.children && !d._children) return d.data.name + " (S3)";
          else return d.data.name;
      });

  // UPDATE
  var nodeUpdate = nodeEnter.merge(node);

  // Transition to the proper position for the node
  nodeUpdate.transition()
      .duration(duration)
      .attr("transform", function(d) {
          return "translate(" + d.y + "," + d.x + ")";
      });

  // Update the node attributes and style
  nodeUpdate.select('circle.node')
      .attr('r', 10);

  // Remove any exiting nodes
  var nodeExit = node.exit().transition()
      .duration(duration)
      .attr("transform", function(d) {
          return "translate(" + source.y + "," + source.x + ")";
      })
      .remove();

  // On exit reduce the node circles size to 0
  nodeExit.select('circle')
      .attr('r', 1e-6);

  // On exit reduce the opacity of text labels
  nodeExit.select('text')
      .style('fill-opacity', 1e-6);

  // ****************** links section ***************************

  // Update the links...
  var link = g.selectAll('path.link')
      .data(links, function(d) { return d.target.id; });

  // Enter any new links at the parent's previous position.
  var linkEnter = link.enter().insert('path', "g")
      .attr("class", "link")
      .attr('d', function(d){
        var o = {x: source.x0, y: source.y0}
        return diagonal(o, o)
      });

  // UPDATE
  var linkUpdate = linkEnter.merge(link);

  // Transition back to the parent element position
  linkUpdate.transition()
      .duration(duration)
      .attr('d', function(d){ return diagonal(d.source, d.target) });

  // Remove any exiting links
  var linkExit = link.exit().transition()
      .duration(duration)
      .attr('d', function(d) {
        var o = {x: source.x, y: source.y}
        return diagonal(o, o)
      })
      .remove();

  // Store the old positions for transition.
  nodes.forEach(function(d){
    d.x0 = d.x;
    d.y0 = d.y;
  });

  // Creates a curved (diagonal) path from parent to the child nodes
  function diagonal(s, d) {
    var path = `M ${s.y} ${s.x}
            C ${(s.y + d.y) / 2} ${s.x},
              ${(s.y + d.y) / 2} ${d.x},
              ${d.y} ${d.x}`;

    return path;
  }
}

document.getElementById('simulate-query').addEventListener('click', simulateQuery);

function simulateQuery() {
  // Reset styles
  svg.selectAll('circle').classed('highlighted', false);
  svg.selectAll('path.link').classed('highlighted', false);

  // Define the query vector (for demonstration)
  var queryVector = [/* query vector values */];

  // Find the closest centroid
  var closestCentroidNode = findClosestCentroid(root, queryVector);

  // Highlight the path to the closest centroid
  highlightPath(closestCentroidNode);

  // Simulate parallel retrieval of leaves
  if (closestCentroidNode.children) {
    closestCentroidNode.children.forEach(function(leafNode) {
      svg.selectAll('circle').filter(function(d) { return d === leafNode; })
        .classed('highlighted', true);
    });
  }
}

function findClosestCentroid(node, queryVector) {
  // For demonstration purposes, we select the first centroid
  return node.children ? node.children[0] : node;
}

function highlightPath(node) {
  while (node) {
    svg.selectAll('circle').filter(function(d) { return d === node; })
      .classed('highlighted', true);
    if (node.parent) {
      svg.selectAll('path.link').filter(function(d) { return d.target === node; })
        .classed('highlighted', true);
    }
    node = node.parent;
  }
}
</script>

<!-- Visualization Styles -->
<style>
.node circle {
  fill: #fff;
  stroke: steelblue;
  stroke-width: 1.5px;
}
.node--internal circle {
  fill: #fff;
}
.node--leaf circle {
  fill: lightsteelblue;
}
.node text {
  font: 12px sans-serif;
}
.link {
  fill: none;
  stroke: #555;
  stroke-width: 2px;
}
.node circle.highlighted {
  stroke: red;
  stroke-width: 3px;
}
.link.highlighted {
  stroke: red;
  stroke-width: 3px;
}
</style>
{% endraw %}

## Installation

*(Provide instructions on how to install and run the project if applicable.)*

```bash
git clone https://github.com/fumadari/s3-distributed-vector-index.git
cd s3-distributed-vector-index
# Additional setup steps

