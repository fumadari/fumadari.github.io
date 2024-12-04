---
layout: default
title: S3 Distributed Vector Index
---

# S3 Distributed Vector Index
# Overview

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

## Technologies Used

- **Programming Languages:** Python, C++
- **AWS Services:** Amazon S3, AWS Lambda, AWS EC2
- **Libraries:** FAISS, HNSWlib
