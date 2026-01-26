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

#### [Selective Replication for Efficient k-NN Retrieval](./projects/vectors-replication.html)
This work proposes a selective vector replication method to boost k-nearest neighbor search performance in high-dimensional spaces. By identifying and replicating only the “boundary” vectors that connect multiple clusters, we significantly improve recall while reducing the number of vectors accessed during queries. The result is a more efficient and accurate large-scale search solution, striking an optimal balance between storage overhead, query speed, and overall retrieval quality.

#### [Hierarchically Partitioned Cloud-Native Vector Search](./projects/s3-index.html)
This research redesigns vector similarity search for cloud environments, leveraging S3’s parallelism and a hierarchical graph partitioning approach. By breaking large HNSW graphs into optimally sized subgraphs and retrieving them in parallel, we achieve lower query latency and maintain high recall at billion-scale. The result is a cloud-native vector index that balances scalable performance, storage efficiency, and search quality.

#### [GeoGAT: Geometry-Aware Graph Attention for Molecular Property Prediction](./projects/gat-drug-discovery.html)
GeoGAT combines bonded connectivity, 3D geometry, and electronic descriptors in a molecular graph model. Using attention on sparse molecular graphs with a global context node, the network captures both local chemistry and long-range interactions. Geometry influences attention through invariant pair and angle features, enabling the model to distinguish conformers and focus on chemically meaningful regions. The approach improves accuracy on tasks like binding affinity, solubility, and LogP prediction while providing interpretable attention patterns for drug discovery and materials science.

#### [Elastic State Models: Geometry-Aware Adaptive Compute](./projects/elastic-state-models.html)
Elastic State Models (ESM) add adaptive computation to a streaming state-space backbone. At each timestep, a gate converts per-step error into an integer inner depth under an explicit compute penalty. When refinement is activated, ESM performs latent updates using metric-preconditioned gradients and trust-region clipping. The method allocates compute by timestep difficulty—concentrating refinement around bottlenecks in maze navigation and distorted regions in protein loop repair—achieving improved performance at lower average compute than Transformer baselines.

#### [Broadcast-Gain: Minimal Control Plane for Cooperative MARL](./projects/broadcast-gain.html)
Broadcast-Gain (BG) is a fixed-rate, neighbor-only overlay that reduces long-tail latency in cooperative multi-agent reinforcement learning under lossy communication. Each agent broadcasts just two bytes per cycle—a signed residual and a meta tag—without modifying the base learner. Receivers form a confidence-weighted consensus to gate a phase scheduler and apply a clipped, distance-decayed push to the MOVE logit near junctions. At ~0.24 kbit/s per agent, BG reduces tail wait by ~5 steps and increases near-gate flow by +392 per 1k steps on hard evaluation cells.



### Contact

I'm always eager to discuss research opportunities or collaborate on interesting projects. Feel free to reach out!

Email: [dariofumarola90@gmail.com](mailto:dariofumarola90@gmail.com)  
LinkedIn: [Dario Fumarola](https://www.linkedin.com/in/fumarolad)
