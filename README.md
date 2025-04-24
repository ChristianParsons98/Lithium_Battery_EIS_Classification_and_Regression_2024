# Lithium Battery EIS Classification and Regression (2024)

This repository supports the research article:  
**“Performance Classification and Remaining Useful Life Prediction of Lithium Batteries Using Machine Learning and Early Cycle Electrochemical Impedance Spectroscopy Measurements”**  
by Christian Parsons, Adil Amin, and Prasenjit Guptasarma  
📄 [View on arXiv](https://arxiv.org/abs/2408.03469)

## 🧪 Description

This code implements a lightweight, interpretable pipeline for:
- Classifying lithium-ion batteries into high- and low-performing groups.
- Predicting the **remaining useful life (RUL)** early in the battery's cycle life using only a small subset of EIS measurements.

The standout contribution is that classification and regression are performed using just 1–2 EIS frequencies and temperature, demonstrating **100% classification accuracy** and **R² > 0.96** for RUL prediction—**within the first 20 cycles**.

## 🔧 Techniques Used

- **[Support Vector Machine (SVM)](https://scikit-learn.org/stable/modules/svm.html)**: For high/low performance classification using the 20 kHz impedance feature.
- **[Lasso Regression](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.Lasso.html)**: For RUL prediction from -Im(Z) at 20 kHz and 8.8 Hz + temperature.
- **[Principal Component Analysis (PCA)](https://scikit-learn.org/stable/modules/generated/sklearn.decomposition.PCA.html)**: Used in exploratory data visualization.
- Comparison with **Decision Trees** and **Random Forests** to highlight the SVM’s generalization capabilities.

## 📦 Libraries and Tools

- [scikit-learn](https://scikit-learn.org/)
- [NumPy](https://numpy.org/)
- [Pandas](https://pandas.pydata.org/)
- [Matplotlib](https://matplotlib.org/)
- [Jupyter Notebook](https://jupyter.org/)

## 📁 Project Structure

```plaintext
.
├── Cleaned_Data/
├── DE_Figures/
├── Data/
├── Figures/
├── Classification_Low_Cycles_*.ipynb
├── Regression_Low_Cycles_Cleaned_*.ipynb
├── Data_Cleaning.ipynb
├── PCA_EIS_Exploration.ipynb
└── README.md
```

### Notable Directories

- `Data/`: Raw Zhang dataset and EIS measurements.
- `Cleaned_Data/`: Aligned and processed EIS + RUL data.
- `Figures/`, `DE_Figures/`: Generated figures used in paper and for presentation.
- `*_Low_Cycles_*.ipynb`: Notebooks analyzing each SOC condition (III, V, IX).

## 📊 Highlights from the Paper

- **Single-feature SVM classification** using 20 kHz impedance achieves **100% accuracy**.
- **RUL prediction** using only impedance at 20 kHz and 8.8 Hz + temperature yields **R² > 0.96**.
- Models are robust across **stable and unstable SOC states**.
- **No complex preprocessing** or high-dimensional ML is needed—results are reproducible and interpretable.

## 🔗 Citation

If you use this code or build upon this work, please cite:  
📄 [arXiv:2408.03469](https://arxiv.org/abs/2408.03469)
