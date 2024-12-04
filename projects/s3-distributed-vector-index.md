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

This visualization illustrates the hierarchical structure of the index, showing how data is partitioned into clusters with centroids and how leaves are stored in S3.

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

var i = 0;

// Load the data
d3.json("{{ '/assets/data/hierarchical_index.json' | relative_url }}").then(function(data) {
  var root = d3.hierarchy(data, function(d) { return d.children; });

  update(root);
});

function update(source) {
  var treeData = treemap(source);

  // Compute the new tree layout.
  var nodes = treeData.descendants(),
      links = treeData.links();

  // Normalize for fixed-depth.
  nodes.forEach(function(d){ d.y = d.depth * 180});

  // ****************** Nodes section ***************************

  // Update the nodes...
  var node = g.selectAll('g.node')
      .data(nodes, function(d) { return d.id || (d.id = ++i); });

  // Enter any new nodes at the correct position.
  var nodeEnter = node.enter().append('g')
      .attr('class', function(d) {
          return 'node' + (d.children ? ' node--internal' : ' node--leaf');
      })
      .attr("transform", function(d) {
          return "translate(" + d.y + "," + d.x + ")";
      });

  // Add Circle for the nodes
  nodeEnter.append('circle')
      .attr('class', 'node')
      .attr('r', 10)
      .style("fill", function(d) {
          if (d.data.centroid) return "orange"; // Centroid nodes
          else if (d.children) return "#fff"; // Internal nodes
          else return "lightsteelblue"; // Leaf nodes
      });

  // Add labels for the nodes
  nodeEnter.append('text')
      .attr("dy", ".35em")
      .attr("x", function(d) {
          return d.children ? -13 : 13;
      })
      .attr("text-anchor", function(d) {
          return d.children ? "end" : "start";
      })
      .text(function(d) {
          if (d.data.centroid) return d.data.name + " (Centroid)";
          else if (!d.children) return d.data.name + " (S3)";
          else return d.data.name;
      });

  // ****************** Links section ***************************

  // Update the links...
  var link = g.selectAll('path.link')
      .data(links, function(d) { return d.target.id; });

  // Enter any new links at the correct position.
  link.enter().insert('path', "g")
      .attr("class", "link")
      .attr('d', function(d){
        return diagonal(d);
      });
}

// Creates a curved (diagonal) path from parent to the child nodes
function diagonal(d) {
  return "M" + d.source.y + "," + d.source.x
       + "C" + (d.source.y + d.target.y) / 2 + "," + d.source.x
       + " " + (d.source.y + d.target.y) / 2 + "," + d.target.x
       + " " + d.target.y + "," + d.target.x;
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
</style>
{% endraw %}

## Installation

*(Provide instructions on how to install and run the project if applicable.)*

```bash
git clone https://github.com/fumadari/s3-distributed-vector-index.git
cd s3-distributed-vector-index
# Additional setup steps

