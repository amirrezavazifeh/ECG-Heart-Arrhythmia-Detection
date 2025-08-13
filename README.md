## 🩺 Problem Statement

Automated heartbeat analysis is a crucial step in arrhythmia detection, yet most existing methods rely heavily on **supervised learning**, which depends on large, labeled datasets. This approach faces three main challenges:

1. **Lead Variability** – A standard 12-lead ECG records twelve distinct waveforms for each heartbeat (see Figure 1). Models trained for one lead do not directly generalize to another. Many datasets, including the **MIT-BIH Arrhythmia Database**, contain only two leads per recording—Lead II (MLII) and a second lead (either V1, V2, V4, or V5)—making it difficult to develop lead-independent models. Even small electrode placement changes during testing can alter signal morphology enough to cause model failure.

2. **Patient Variability** – ECG signals with the same arrhythmia label can differ substantially between individuals. This inter-patient variability reduces robustness to unseen patients.

3. **Dataset Bias** – In MIT-BIH, more than **80%** of beats are normal, and most arrhythmic beats are premature ventricular contractions (PVCs). This imbalance leads many models to overfit common patterns while performing poorly on rare arrhythmias. Further, label standards differ between datasets, limiting cross-dataset transferability.

---

## 💡 Our Approach

We address these challenges by combining **unsupervised dimensionality reduction** with **heartbeat-level analysis**.

### 1. Heartbeat Segmentation & Preprocessing

The first step in real-world analysis is to segment the ECG signals into isolated heartbeats. This requires detecting **R-peaks** from the raw signal. Although many algorithms exist—such as Christov, Pan–Tompkins, and NeuroKit2—a recent study found NeuroKit2 to be the most accurate. Since MIT-BIH already provides annotated R-peak locations, we use these directly.

After detecting R-peaks, we segment each heartbeat using a **constant division ratio** between consecutive beats:  
- The first two-thirds of the upcoming RR interval  
- Plus the last one-third of the previous RR interval  

This method (Figure 2) avoids contamination from overlapping beats, even when heart rates vary. All beats are then **resampled to 256 points** for consistency, and baseline wandering is removed by subtracting a median-filtered version of the waveform (kernel size = 127).

**Figure 2 – ECG heartbeat segmentation method**  
![segmentation](Segmentation.png)

---

### 2. Dimensionality Reduction per Patient

Rather than pooling beats from all patients, we apply **UMAP** or **t-SNE** to each patient individually. This makes it easier to visualize and cluster beat types without supervision, as shown in Figure 3.

**Figure 3 – Dimensionality reduction and clustering for Recording 207**  
![recording-207](207_all.png)

---

### 3. Cross-Patient Comparison

When mixing beats from multiple patients, the embeddings naturally cluster by patient. This highlights how strong inter-patient variability is—even without labels.

**Figure 4 – Pipeline for ECG preprocessing and analysis**  
![methods](methods.png)
