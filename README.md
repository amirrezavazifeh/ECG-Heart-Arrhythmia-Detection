# ECG Visualization and Analysis using Dimensionality Reduction

## 📂 Dataset

The dataset used is the [MIT-BIH Arrhythmia Database](https://www.physionet.org/content/mitdb/1.0.0/).  
Please download it from the link above.

---

## 🚀 How to Run

1. **Download the MIT-BIH dataset** and place it either in your Google Drive or local machine.

2. **Run the notebook:**  
   [`ECG_on_Colab_Generating_Results.ipynb`](ECG_on_Colab_Generating_Results.ipynb)  
   This notebook will:
   - Process the ECG signals
   - Apply dimensionality reduction
   - Generate all the results used in the paper
   - Save the output variables in a pickle file named `ECG2.pkl`

   ⚠️ Note: Due to the stochastic nature of dimensionality reduction methods like UMAP and t-SNE, results may vary slightly in terms of cluster orientation or positioning.

---

## 📁 Precomputed Results

All results used in the paper are available in this  
[Google Drive folder](https://drive.google.com/drive/folders/1_-ElNT6jLkNbGXl9NJIfkdNNlEMBC6G-?usp=sharing).

---

## 📊 Visualization

To visualize the generated results and reproduce the figures in the paper (along with additional plots), run:  
[`ECG_on_CPU_visualzing_results.ipynb`](ECG_on_CPU_visualzing_results.ipynb)
