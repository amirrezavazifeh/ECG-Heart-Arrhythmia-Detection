## 🩺 Problem Statement

Automated heartbeat analysis is a crucial step in arrhythmia detection, yet most existing methods rely heavily on **supervised learning**, which depends on large, labeled datasets. This approach faces three main challenges:

1. **Lead Variability** – A standard 12-lead ECG records twelve distinct waveforms for each heartbeat (see Figure 1). Models trained for one lead do not directly generalize to another. Many datasets, including the **MIT-BIH Arrhythmia Database**, contain only two leads per recording—Lead II (MLII) and a second lead (either V1, V2, V4, or V5)—making it difficult to develop lead-independent models. Even small electrode placement changes during testing can alter signal morphology enough to cause model failure.

2. **Patient Variability** – ECG signals with the same arrhythmia label can differ substantially between individuals (see Figure 2). This inter-patient variability reduces robustness to unseen patients.

3. **Dataset Bias** – In MIT-BIH, more than **80%** of beats are normal, and most arrhythmic beats are premature ventricular contractions (PVCs). This imbalance leads many models to overfit common patterns while performing poorly on rare arrhythmias. Further, label standards differ between datasets, limiting cross-dataset transferability.

---

## 💡 Our Approach

We address these challenges by combining **unsupervised dimensionality reduction** with **heartbeat-level analysis**:

1. **Heartbeat Segmentation & Preprocessing** – Using our pipeline (Figure 1), we detect R-peaks, segment heartbeats, remove baseline wander, and filter noise.  
2. **Per-Patient Analysis** – Instead of pooling data across patients, we apply **UMAP** or **t-SNE** to each patient's heartbeats individually, enabling clearer visualization of beat types without label supervision.  
3. **Clustering & Visualization** – We cluster the low-dimensional embeddings (Figure 2) to reveal beat categories directly from morphology.  
4. **Cross-Patient Comparison** – When heartbeats from multiple patients are mixed and embedded together, the beats naturally group by patient (Figure 3). This finding confirms that inter-patient differences are strong enough to create separable clusters without labels.

---

## 📷 Figures

**Figure 1 – ECG preprocessing and dimensionality reduction pipeline**  
![methods](methods.png)

**Figure 2 – Dimensionality reduction and clustering for Recording 207**  
![recording-207](207_all.png)

**Figure 3 – Clustering showing patient-specific beat groupings in mixed datasets**  
![segmentation](Segmentation.png)
