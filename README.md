# Project
Implementing and Optimizing Spectral Clustering with a Custom Kernel

This project presents a from-scratch implementation of Spectral Clustering using a custom similarity kernel, followed by a performance comparison with scikit-learn’s SpectralClustering.
The focus is on mathematical understanding, numerical stability, and empirical evaluation rather than relying solely on off-the-shelf methods.

 Project Objectives

Implement the full spectral clustering pipeline from first principles

Design and apply a custom similarity kernel

Construct and analyze the graph Laplacian

Perform spectral embedding using eigen decomposition

Evaluate clustering quality using Adjusted Rand Index (ARI)




Methodology
Synthetic Dataset Generation

Generated multi-modal, overlapping Gaussian clusters using make_blobs

Designed to be challenging for standard K-Means

Custom Similarity Kernel

Implemented a Thresholded RBF (Gaussian) Kernel

Small similarity values are removed to sparsify the graph

 Graph Laplacian Construction

𝑊
W is the similarity matrix

𝐷
D is the degree matrix

 Spectral Embedding

Computed the first 
𝑘
k eigenvectors of the Laplacian

Embedded data into a lower-dimensional spectral space

 Clustering in Embedded Space

Applied K-Means on the spectral embedding

Produced final cluster assignments

 Performance Evaluation

Compared results with scikit-learn’s SpectralClustering

Metrics used:

Adjusted Rand Index (ARI)

Execution Time

 Experimental Results

The script evaluates clustering performance across different kernel width values (σ):

Metric	Description
ARI	Measures similarity between predicted clusters and ground truth
Execution Time	Measures computational efficiency

Results are printed in the following format:

Sigma | Custom ARI | Custom Time | Sklearn ARI | Sklearn Time

 Challenges & Observations

Very small σ values can lead to disconnected graphs

Eigen decomposition is computationally expensive for large datasets

Thresholding improves sparsity but requires careful tuning

Numerical instability may occur when degree values approach zero

 How to Run

Install dependencies:

pip install numpy scipy scikit-learn


Run the script:

python spectral_clustering.py

 Key Learning Outcomes

Deep understanding of spectral clustering mechanics

Hands-on experience with graph-based learning

Practical insight into kernel design and numerical stability

Performance trade-offs between custom vs library implementations

 Future Enhancements

Sparse matrix optimization for scalability

Visualization of spectral embeddings

Alternative kernels (Polynomial, k-NN graphs)

Approximate eigen solvers for large datasets

