---
layout: default
---

## About Me

Hey! I’m Dario, a Computer Science and Mathematics graduate from Washington and Lee University. Originally from a [small village in Italy](https://en.wikipedia.org/wiki/Cisternino), I’m currently a Prototype Architect at Amazon Web Services in New York City, crafting large-scale AI solutions that harness the cloud to handle massive datasets.

My research interests sit at the intersection of deep learning, mathematics, and geometry. I’m fascinated by how concepts like graph structures, differential geometry, and topological analysis can enhance neural representations, making models more interpretable and robust. By tapping into these mathematical frameworks, I aim to develop techniques that offer clear, principled insights into complex data, pushing AI towards more transparent and flexible solutions.

I am actively seeking PhD opportunities to deepen my understanding of these approaches and apply them to real-world challenges in scalable machine learning and data-driven discovery.

[Download CV](assets/dario_fumarola_cv.pdf)

*Last updated: January 2026*

### Research Interests

- **Mathematical Foundations of Deep Learning**: Using concepts from geometry, information theory, and topology to guide model design, ensuring more stable and interpretable neural representations.
- **Graph-Based Models and Structures**: Employing graph neural networks and manifold learning to capture rich relational information in data, improving accuracy and transparency.
- **Scalable AI on the Cloud**: Integrating distributed training, efficient architectures, and resource-aware approaches to tackle billion-scale datasets, accelerating innovation while maintaining model integrity.

### Education

**Washington and Lee University** (2019 - 2023)  
Computer Science and Mathematics - *Davis Scholar*

Relevant Coursework: Deep Learning, Machine Learning and Big Data, Real Analysis, Network Security, Differential Geometry, Differential Equations

### Experience Highlights

 - **Amazon Web Services (AWS) – Prototyping Architect**:  
Developed large-scale cloud pipelines integrating advanced deep learning architectures, including attention mechanisms and graph-based models, to accelerate bioinformatics workloads. Employed distributed training and resource-aware scaling strategies to handle massive datasets and implemented retrieval-augmented frameworks with topological insights for enhanced interpretability and recall.

 - **Amazon Science – Research Assistant**:  
Explored geometric and topological approaches for organizing high-dimensional embeddings at billion-scale. Contributed to next-generation indexing and storage methods that improved retrieval efficiency and data integrity while collaborating with researchers to document and refine strategies grounded in mathematical principles.

**Professional Memberships**:
- Institute of Electrical and Electronics Engineers (IEEE)
- Association for Computing Machinery (ACM)
- Association for the Advancement of Artificial Intelligence (AAAI)

### Presented Work

#### Conference Publications

##### [Elastic State Models: Geometry-Aware Adaptive Compute](./projects/elastic-state-models.html)
*NeurIPS 2025*

Elastic State Models (ESM) add adaptive computation to a streaming state-space backbone by converting per-step error into an integer refinement depth under an explicit compute penalty. When activated, ESM performs latent-space updates using metric-preconditioned gradients with trust-region clipping to stabilize correction. The method concentrates compute on difficult timesteps, improving performance in maze navigation and protein loop repair while using lower average compute than Transformer baselines.

##### [Broadcast-Gain: Minimal Control Plane for Cooperative MARL](./projects/broadcast-gain.html)
*NY-RL 2025*

Broadcast-Gain (BG) is a fixed-rate, neighbor-only overlay that improves coordination in cooperative MARL under lossy communication. Each agent broadcasts two bytes per cycle (a signed residual and a meta tag) without modifying the base PPO+GAE learner; receivers compute a confidence-weighted consensus that gates a phase scheduler and applies a clipped, distance-decayed bias to the MOVE logit near junctions. At ~0.24 kbit/s per agent, BG reduces tail wait by ~5 steps and increases near-gate flow by +392 per 1k steps on hard evaluation cells.

##### [Mood Swings: Neuromodulatory Control for Deep RL Agents](./projects/mood-swings.html)
*ICML 2025*

Mood Swings introduces a compact control interface for actor–critic agents using three global scalars: dopaminergic gain on TD error and two serotonergic coefficients controlling entropy drive and threat discounting. These scalars define a continuous "mood" manifold outside the network, enabling behavior shifts by writing three floats rather than retraining. Experiments in Pac-Mind and MiniHack trace smooth safety–performance frontiers, with higher dopamine accelerating learning but increasing collision risk, and higher serotonin improving survival while moderating returns.

#### Research Projects

##### [Selective Replication for Efficient k-NN Retrieval](./projects/vectors-replication.html)
We propose selective vector replication to improve k-nearest neighbor retrieval in clustered high-dimensional indexes. The method identifies boundary vectors likely to be relevant across neighboring clusters and replicates only those vectors into the adjacent partitions they connect. This targeted replication increases recall while reducing the number of vectors scanned per query, yielding better retrieval quality with bounded storage overhead.

##### [Hierarchically Partitioned Cloud-Native Vector Search](./projects/s3-index.html)
This work adapts graph-based ANN search to object storage by combining hierarchical graph partitioning with parallel S3 reads. Large HNSW graphs are partitioned into size-bounded subgraphs optimized for object fetch and caching behavior, and queries retrieve only the subgraphs required for traversal, in parallel. The result is lower tail latency while maintaining high recall at billion-scale, with predictable storage and compute costs.

##### [GeoGAT: Geometry-Aware Graph Attention for Molecular Property Prediction](./projects/gat-drug-discovery.html)
GeoGAT integrates bonded connectivity, 3D geometry, and electronic descriptors in a sparse molecular graph attention model. A global context node captures molecule-level effects while invariant pair and angle features modulate attention to distinguish conformers and long-range interactions. Across tasks such as solubility, LogP, and binding-related prediction, GeoGAT improves accuracy and yields interpretable attention patterns that localize influential atoms and functional groups.

### Contact

I'm always eager to discuss research opportunities or collaborate on interesting projects. Feel free to reach out!

Email: [dariofumarola90@gmail.com](mailto:dariofumarola90@gmail.com)  
LinkedIn: [Dario Fumarola](https://www.linkedin.com/in/fumarolad)
