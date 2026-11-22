<div align="center">
<h1>Manifold Learning for Personalized and Label-free<br>Heart Arrhythmia Detection</h1>

<p>
<a href="https://amirrezavazifeh.github.io/ECG-manifold-viewer/index.html"><img src="https://img.shields.io/badge/Software_Demo-ECG_Manifold_Viewer-blue?style=flat-square" alt="Software Demo"></a>
<a href="https://doi.org/10.1016/j.imu.2026.101770"><img src="https://img.shields.io/badge/Journal-Informatics in Medicine Unlocked-808080?style=flat-square&labelColor=808080&color=D2691E" alt="Informatics in Medicine Unlocked Journal"></a>
</p>

<p>
  <a href="https://github.com/amirrezavazifeh">Amir Reza Vazifeh</a><sup>a,b</sup>
  &nbsp;·&nbsp;
  <a href="https://ece.princeton.edu/people/jason-w-fleischer">Jason W. Fleischer</a><sup>a,b,c</sup>
</p>

<sup>a</sup> Department of Electrical and Computer Engineering, Princeton University, Princeton, 08544, New Jersey, USA<br>
<sup>b</sup> Princeton Precision Health, Princeton University, Princeton, 08544, New Jersey, USA<br>
<sup>c</sup> Omenn-Darling Bioengineering Institute, Princeton University, 35 Ivy Lane, Princeton, 08540, New Jersey, USA

<p><em>Informatics in Medicine Unlocked</em>, 2026</p>
</div>

---

## Repository Structure

```
ECG-Heart-Arrhythmia-Detection/
├── index.html                                  # Project page
├── assets/                                     # Figures used by the project page
├── Code/
│   ├── ECG_Segmentation.ipynb                  # R-peak detection and heartbeat segmentation
│   ├── Personalized_Arrhythmia_Detection.ipynb # Per-person embedding, clustering and k-NN evaluation
│   ├── Population_Analysis.ipynb               # Embedding of heartbeats pooled across people
│   └── Clustering Algorithms.ipynb             # Clustering comparison on toy datasets
└── README.md
```

## Datasets

- [MIT-BIH Arrhythmia Database](https://physionet.org/content/mitdb/1.0.0/)
- [MIT-BIH Normal Sinus Rhythm Database](https://physionet.org/content/nsrdb/1.0.0/)
- [MIT-BIH Atrial Fibrillation Database](https://physionet.org/content/afdb/1.0.0/)

## Citation

```bibtex
@article{vazifeh:26,
title = {Manifold learning for personalized and label-free detection of cardiac arrhythmias},
journal = {Informatics in Medicine Unlocked},
volume = {64},
pages = {101770},
year = {2026},
issn = {2352-9148},
doi = {https://doi.org/10.1016/j.imu.2026.101770},
url = {https://www.sciencedirect.com/science/article/pii/S2352914826000407},
author = {Amir Reza Vazifeh and Jason W. Fleischer},
}
```