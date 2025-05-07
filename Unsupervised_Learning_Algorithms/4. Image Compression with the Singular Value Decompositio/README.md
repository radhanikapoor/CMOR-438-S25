# Singular Value Decomposition (SVD) for Image Compression

This notebook explores **Singular Value Decomposition (SVD)** as a method for **compressing grayscale face images**. Using the **Olivetti Faces dataset**, we demonstrate how SVD can reduce image size while preserving the most important visual features.

SVD is a core tool in linear algebra and unsupervised learning, commonly used in:
- Dimensionality reduction
- Latent feature extraction
- Noise filtering
- Low-rank matrix approximation

---

## What is SVD?

Given a matrix $ A $, SVD decomposes it into three components:

$$
A = U \Sigma V^T
$$

Where:
- $ U $: left singular vectors (orthogonal)
- $ \Sigma $: diagonal matrix of singular values
- $ V^T $: right singular vectors (orthogonal)

To compress the matrix, we keep only the top $ k $ singular values and vectors:

$$
A_k = U_k \Sigma_k V_k^T
$$

This produces a **rank-$ k $** approximation that captures the most significant structure in the image, discarding finer details and noise.

---

## Why Use SVD for Images?

Image data (like 64x64 pixel grayscale face images) is naturally stored in matrices. SVD lets us:
- **Retain important visual structure** (edges, shadows, contours)
- **Reduce memory/storage needs** significantly
- Perform **lossy compression** that balances fidelity and efficiency

This is useful in settings like facial recognition, storage-constrained systems, and image transmission pipelines.

---

## Dataset Description: Olivetti Faces

The dataset used in this notebook is the **Olivetti Faces** dataset — a classic benchmark in machine learning and computer vision. It contains:
- 400 grayscale images
- 64 × 64 pixels each
- 40 unique individuals (10 images per person)
- Natural variations in lighting, expressions, and pose

### How It’s Accessed

Unlike typical CSV or image files in the `datasets/` directory, this dataset is **accessed directly via `sklearn.datasets.fetch_olivetti_faces()`**, which downloads the data from an online repository and loads it into memory.

> Although it's not stored in the project's `datasets/` folder, it is freely accessible to anyone with internet access and can be downloaded automatically when the code is run.

---

## Compression Demonstration

For each image:
- We apply SVD and reconstruct it using the top $ k $ singular values (e.g., $ k = 10, 20, 40 $)
- We visualize the tradeoff between **image quality** and **compression ratio**
- We compute compression metrics like storage size and MSE vs. original image

---

## Weaknesses of SVD for Image Compression

Despite its strengths, SVD has a few limitations:

- **Computational cost**: Decomposing large matrices can be slow for large datasets
- **Not content-aware**: It preserves dominant pixel patterns, not semantic meaning
- **Fixed basis**: SVD finds linear features; it may underperform on more complex visual structures
- **Storage not always minimal**: For very sparse images, alternatives like JPEG or wavelet compression may perform better

---

## Conclusion

SVD is a simple yet powerful tool for compressing image data. In this notebook, we demonstrated:
- How SVD reduces images to their most essential components
- How rank-\( k \) approximations affect visual fidelity
- Tradeoffs between compression level and image quality

This method is a valuable addition to the unsupervised learning toolkit and highlights how linear algebra can be applied to real-world data like facial images.

Next steps could include:
- Comparing SVD to PCA- and JPEG-based compression
- Extending to color images or video frames
- Exploring faster, randomized SVD approximations
