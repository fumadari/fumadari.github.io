---
layout: default
---

## About Me

Hey! I’m Dario, a Computer Science and Mathematics graduate from Washington and Lee University. Originally from a [small village in Italy](https://en.wikipedia.org/wiki/Cisternino), I’m currently a Prototype Architect at Amazon Web Services in New York City, crafting large-scale AI solutions that harness the cloud to handle massive datasets.

My research interests sit at the intersection of deep learning, mathematics, and geometry. I’m fascinated by how concepts like graph structures, differential geometry, and topological analysis can enhance neural representations, making models more interpretable and robust. By tapping into these mathematical frameworks, I aim to develop techniques that offer clear, principled insights into complex data, pushing AI towards more transparent and flexible solutions.

I am actively seeking research collaborations to deepen my understanding of these approaches and apply them to real-world challenges in scalable machine learning and data-driven discovery.

I'm always eager to discuss research opportunities or collaborate on interesting projects. Feel free to reach out!

[Download CV](assets/dario_fumarola_cv.pdf) ・ [dariofumarola90@gmail.com](mailto:dariofumarola90@gmail.com) ・ [LinkedIn](https://www.linkedin.com/in/fumarolad)

*Last updated: January 2026*

### Research Interests

- **Reinforcement Learning and Adaptive Control**: I study how agents allocate computation and risk under uncertainty, with a focus on stable learning, long-horizon credit assignment, and interpretable control signals.
- **Geometric and Structured Representation Learning**: I use geometric and graph-based perspectives to understand and shape neural representations, targeting invariances, robustness, and explanations that map to meaningful structure.
- **Scalable Retrieval and Learning Systems**: I work on billion-scale embedding systems and cloud-native ML, including efficient indexing/storage, resource-aware inference, and distributed pipelines that keep quality predictable at scale.

### Education

**Washington and Lee University** (2019 - 2023)  
Computer Science and Mathematics - *Davis Scholar*

Relevant Coursework: Deep Learning, Machine Learning and Big Data, Real Analysis, Network Security, Differential Geometry, Differential Equations

### Experience Highlights

- **Amazon Web Services (AWS) — Prototyping**:
Delivered customer-facing applied AI systems on AWS, spanning multimodal and agentic workflows and end-to-end architectures across services such as SageMaker, Lambda, Step Functions, S3, and DynamoDB/OpenSearch. Built systems with infrastructure-as-code, automated evaluation, and production-style observability, and shipped outcomes that influenced multi-million-dollar sales motions.

- **Amazon Science — Research (Independent Agenda)**:
Conducted research with increasing independence, developing and executing a personal research agenda alongside core embedding/indexing work. Presented research outcomes externally, including demos and technical discussions at Amazon's conference booth, and collaborated with researchers on experimental design, writing, and invention work across embedding systems and learning-driven mechanisms.

**Professional Memberships**:
- Institute of Electrical and Electronics Engineers (IEEE)
- Association for Computing Machinery (ACM)
- Association for the Advancement of Artificial Intelligence (AAAI)

### Presented Work

<p class="section-subtitle">Conference Publications</p>

<div class="project-card">
<h5><a href="./projects/elastic-state-models.html">Elastic State Models: Geometry-Aware Adaptive Compute</a></h5>
<span class="venue-badge neurips">NeurIPS 2025</span>
<p>Elastic State Models (ESM) add adaptive computation to a streaming state-space backbone by converting per-step error into an integer refinement depth under an explicit compute penalty. When activated, ESM performs latent-space updates using metric-preconditioned gradients with trust-region clipping to stabilize correction. The method concentrates compute on difficult timesteps, improving performance in maze navigation and protein loop repair while using lower average compute than Transformer baselines.</p>
</div>

<div class="project-card">
<h5><a href="./projects/broadcast-gain.html">Broadcast-Gain: Minimal Control Plane for Cooperative MARL</a></h5>
<span class="venue-badge nyrl">NY-RL 2025</span>
<p>Broadcast-Gain (BG) is a fixed-rate, neighbor-only overlay that improves coordination in cooperative MARL under lossy communication. Each agent broadcasts two bytes per cycle (a signed residual and a meta tag) without modifying the base PPO+GAE learner; receivers compute a confidence-weighted consensus that gates a phase scheduler and applies a clipped, distance-decayed bias to the MOVE logit near junctions. At ~0.24 kbit/s per agent, BG reduces tail wait by ~5 steps and increases near-gate flow by +392 per 1k steps on hard evaluation cells.</p>
</div>

<div class="project-card">
<h5><a href="./projects/mood-swings.html">Mood Swings: Neuromodulatory Control for Deep RL Agents</a></h5>
<span class="venue-badge icml">ICML 2025</span>
<p>Mood Swings introduces a compact control interface for actor–critic agents using three global scalars: dopaminergic gain on TD error and two serotonergic coefficients controlling entropy drive and threat discounting. These scalars define a continuous "mood" manifold outside the network, enabling behavior shifts by writing three floats rather than retraining. Experiments in Pac-Mind and MiniHack trace smooth safety–performance frontiers, with higher dopamine accelerating learning but increasing collision risk, and higher serotonin improving survival while moderating returns.</p>
</div>

<p class="section-subtitle">Research Projects</p>

<div class="project-card">
<h5><a href="./projects/vectors-replication.html">Selective Replication for Efficient k-NN Retrieval</a></h5>
<p>We propose selective vector replication to improve k-nearest neighbor retrieval in clustered high-dimensional indexes. The method identifies boundary vectors likely to be relevant across neighboring clusters and replicates only those vectors into the adjacent partitions they connect. This targeted replication increases recall while reducing the number of vectors scanned per query, yielding better retrieval quality with bounded storage overhead.</p>
</div>

<div class="project-card">
<h5><a href="./projects/s3-index.html">Hierarchically Partitioned Cloud-Native Vector Search</a></h5>
<p>This work adapts graph-based ANN search to object storage by combining hierarchical graph partitioning with parallel S3 reads. Large HNSW graphs are partitioned into size-bounded subgraphs optimized for object fetch and caching behavior, and queries retrieve only the subgraphs required for traversal, in parallel. The result is lower tail latency while maintaining high recall at billion-scale, with predictable storage and compute costs.</p>
</div>

<div class="project-card">
<h5><a href="./projects/gat-drug-discovery.html">GeoGAT: Geometry-Aware Graph Attention for Molecular Property Prediction</a></h5>
<p>GeoGAT integrates bonded connectivity, 3D geometry, and electronic descriptors in a sparse molecular graph attention model. A global context node captures molecule-level effects while invariant pair and angle features modulate attention to distinguish conformers and long-range interactions. Across tasks such as solubility, LogP, and binding-related prediction, GeoGAT improves accuracy and yields interpretable attention patterns that localize influential atoms and functional groups.</p>
</div>

