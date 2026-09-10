---
layout: default
title: Dario Fumarola
description: >-
  Dario Fumarola is an AI researcher and Prototyping Architect at Amazon Web Services in New York City,
  working on reinforcement learning, geometric representation learning, LLM agents, and large-scale vector search.
---

<h2 id="about">About</h2>

<p class="lede">I'm <strong>Dario Fumarola</strong>, a Prototyping Architect at Amazon Web Services (AWS) in New York City. I lead hands-on AI engagements from architecture through production, and I do research on reinforcement learning, the geometry of neural representations, and adaptive inference. Originally from <a href="https://en.wikipedia.org/wiki/Cisternino">Cisternino</a>, a small village in southern Italy, I studied Computer Science and Mathematics at Washington and Lee University.</p>

My research focuses on reinforcement learning, representation learning, and the geometry of neural systems. I'm especially interested in how graph structure and differential geometry can shape more robust, interpretable representations, and how agents can adapt their behavior and computation under uncertainty. Lately I've been working on runtime control and bounded adaptive inference for deployed agents, and on training and evaluating LLM agents. I'm currently technical co-lead on an Amazon Research Award project (Build on Trainium) on safe, social pre-training of LLM agents.

I'm actively seeking research collaborations to apply these directions to real-world problems in learning and decision-making — feel free to [reach out](mailto:dariofumarola90@gmail.com) if you'd like to discuss ideas or build something together :)

<h2 id="research-interests">Research Interests</h2>

<div class="interest-grid">
<div class="interest-card">
<h3>RL &amp; Adaptive Control</h3>
<p>How agents allocate computation and risk under uncertainty — stable learning, long-horizon credit assignment, and interpretable control signals that can be steered at deployment.</p>
</div>
<div class="interest-card">
<h3>Geometric Representation Learning</h3>
<p>Geometric and graph-based perspectives for understanding and shaping neural representations — invariances, robustness, and explanations that map to meaningful structure.</p>
</div>
<div class="interest-card">
<h3>LLM Agents &amp; Evaluation</h3>
<p>Agentic systems and tool use, RL training of LLM agents, and evaluation harnesses that combine deterministic checks, model graders, human review, and production telemetry.</p>
</div>
<div class="interest-card">
<h3>Scalable Retrieval &amp; Inference</h3>
<p>Billion-scale vector search and cloud-native ML — efficient indexing and storage, resource-aware inference and serving, and distributed pipelines with predictable quality at scale.</p>
</div>
</div>

<h2 id="presented-work">Presented Work</h2>

<div class="pill-toggle" role="tablist" aria-label="Presented work categories">
  <button class="pill-btn active" role="tab" aria-selected="true" data-tab="conference">Conference</button>
  <button class="pill-btn" role="tab" aria-selected="false" data-tab="research">Research</button>
</div>

<div id="conference" class="projects-section active">

<div class="project-card">
<h3><a href="./projects/mood-swings.html">Mood Manifolds: Runtime Control Surfaces for Deep RL</a> <span class="venue-badge icml">ICML 2025</span></h3>
<p>Mood Manifolds trains one actor-critic policy whose frozen action map can still be steered at deployment through a bounded mood vector: reward gain, hazard-cost gain, and action temperature. The project separates true runtime control from loss-only training weights, then shows how FiLM conditioning, decomposed critics, and a temperature gate let one policy trace reward-risk frontiers and reroute after hazard alarms without gradient updates. A single steerable policy covers most of the reward-safety frontier spanned by 64 separately trained specialists.</p>
<div class="card-links">
<a href="./projects/mood-swings.html">Project page <svg viewBox="0 0 24 24" fill="none" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true"><path d="M5 12h14M13 6l6 6-6 6"/></svg></a>
<a href="./assets/papers/mood-manifolds-icml.pdf">Paper (PDF)</a>
</div>
</div>

<div class="project-card">
<h3><a href="./projects/elastic-state-models.html">Who Needs Attention Anyway? Elastic State Models</a> <span class="venue-badge neurips">NeurIPS 2025</span></h3>
<p>Elastic State Models add bounded, geometry-aware latent repair to frozen streaming state-space models. A gate chooses how many correction steps a timestep receives, a decoder-induced metric shapes the repair direction, and an accept test prevents unreliable updates from being committed. The result targets streams with sparse hard moments, raising maze-navigation success from 68% to 85% and cutting torsion-chain violations by 64%, while keeping tail latency auditable.</p>
<div class="card-links">
<a href="./projects/elastic-state-models.html">Project page <svg viewBox="0 0 24 24" fill="none" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true"><path d="M5 12h14M13 6l6 6-6 6"/></svg></a>
<a href="./assets/papers/who-needs-attention-anyway.pdf">Paper (PDF)</a>
</div>
</div>

<div class="project-card">
<h3><a href="./projects/broadcast-gain.html">Broadcast-Gain: Minimal Control Plane for Cooperative MARL</a> <span class="venue-badge nyrl">NY-RL 2025</span></h3>
<p>Broadcast-Gain (BG) is a fixed-rate, neighbor-only overlay that improves coordination in cooperative MARL under lossy communication. Each agent broadcasts two bytes per cycle (a signed residual and a meta tag) without modifying the base PPO+GAE learner; receivers compute a confidence-weighted consensus that gates a phase scheduler and applies a clipped, distance-decayed bias to the MOVE logit near junctions. At ~0.24 kbit/s per agent, BG reduces tail wait by ~5 steps and increases near-gate flow by +392 per 1k steps on hard evaluation cells.</p>
<div class="card-links">
<a href="./projects/broadcast-gain.html">Project page <svg viewBox="0 0 24 24" fill="none" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true"><path d="M5 12h14M13 6l6 6-6 6"/></svg></a>
<a href="./assets/nyrl-poster.pdf">Poster (PDF)</a>
</div>
</div>

</div>

<div id="research" class="projects-section">

<div class="project-card">
<h3><a href="./projects/vectors-replication.html">Selective Replication for Efficient k-NN Retrieval</a></h3>
<p>We propose selective vector replication to improve k-nearest neighbor retrieval in clustered high-dimensional indexes. The method identifies boundary vectors likely to be relevant across neighboring clusters and replicates only those vectors into the adjacent partitions they connect. This targeted replication increases recall while reducing the number of vectors scanned per query, yielding better retrieval quality with bounded storage overhead. The patented method now underpins Amazon S3 Vectors, serving tens of billions of vectors in production.</p>
<div class="card-links">
<a href="./projects/vectors-replication.html">Project page <svg viewBox="0 0 24 24" fill="none" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true"><path d="M5 12h14M13 6l6 6-6 6"/></svg></a>
<span>Patent &middot; Amazon S3 Vectors</span>
</div>
</div>

<div class="project-card">
<h3><a href="./projects/s3-index.html">Hierarchically Partitioned Cloud-Native Vector Search</a></h3>
<p>This work adapts graph-based ANN search to object storage by combining hierarchical graph partitioning with parallel S3 reads. Large HNSW graphs are partitioned into size-bounded subgraphs optimized for object fetch and caching behavior, and queries retrieve only the subgraphs required for traversal, in parallel. The result is lower tail latency while maintaining high recall at billion-scale, with predictable storage and compute costs.</p>
<div class="card-links">
<a href="./projects/s3-index.html">Project page <svg viewBox="0 0 24 24" fill="none" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true"><path d="M5 12h14M13 6l6 6-6 6"/></svg></a>
</div>
</div>

<div class="project-card">
<h3><a href="./projects/gat-drug-discovery.html">GeoGAT: Geometry-Aware Graph Attention for Molecular Property Prediction</a></h3>
<p>GeoGAT integrates bonded connectivity, 3D geometry, and electronic descriptors in a sparse molecular graph attention model. A global context node captures molecule-level effects while invariant pair and angle features modulate attention to distinguish conformers and long-range interactions. Across tasks such as solubility, LogP, and binding-related prediction, GeoGAT improves accuracy and yields interpretable attention patterns that localize influential atoms and functional groups.</p>
<div class="card-links">
<a href="./projects/gat-drug-discovery.html">Project page <svg viewBox="0 0 24 24" fill="none" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true"><path d="M5 12h14M13 6l6 6-6 6"/></svg></a>
</div>
</div>

</div>

<h2 id="experience">Experience</h2>

<div class="xp-item">
<h3>Amazon Web Services — Prototyping</h3>
<p class="xp-org">Prototyping Architect &middot; New York City &middot; 2023 – present</p>
<p>I own enterprise AI engagements from discovery through production as the hands-on technical lead across architecture, implementation, and evaluation. Recent work includes an LLM agent that automates model deployment for pharmaceutical ML teams, an evaluation-driven deployment framework now reused across AWS Prototyping, inference optimizations for production Amazon Bedrock workloads (dynamic batching, request scheduling, streaming, custom CUDA and Trainium kernels), and a diffusion-based camera-to-radar synthesis pipeline for an autonomous-driving perception team.</p>
</div>

<div class="xp-item">
<h3>Amazon Research Award — Safe, Social Pre-training of LLM Agents</h3>
<p class="xp-org">Technical co-lead &middot; Build on Trainium &middot; 2026 – present</p>
<p>Building the RL training and evaluation stack for LLM agents, including checkpoint evaluations across reasoning, social inference, and training dynamics, plus the Neuron/XLA and NKI infrastructure it runs on.</p>
</div>

<div class="xp-item">
<h3>Amazon Science — Research</h3>
<p class="xp-org">Independent research agenda &middot; 2023 – present</p>
<p>Research rotation with Amazon Scholars on billion-scale similarity search for Amazon S3 Vectors, where I co-invented the patented selective-replication method now serving tens of billions of vectors in production. Alongside that, I developed an independent agenda on neuromodulated reinforcement learning and adaptive compute, presented externally at Amazon's conference booths and written up as the NeurIPS and ICML work above.</p>
</div>

<h2 id="education">Education</h2>

<div class="xp-item">
<h3>Washington and Lee University</h3>
<p class="xp-org">B.S. Computer Science and Mathematics &middot; 2019–2023 &middot; <em>Davis UWC Scholar</em></p>
<p>Relevant coursework: Deep Learning, Machine Learning and Big Data, Real Analysis, Network Security, Differential Geometry, Differential Equations.</p>
</div>

<h3>Professional Memberships</h3>

<ul class="memberships">
<li>IEEE</li>
<li>ACM</li>
<li>AAAI</li>
</ul>
