# Similarity Analysis: Gene Prediction and Molecular Analysis for Type II Diabetes Mellitus (T2DM)

This project aims to predict genes associated with the progression of Type II Diabetes Mellitus (T2DM) using bioinformatics tools, focusing on sequence similarity analysis and moment of inertia derived from the physiochemical characteristics of amino acids. The project uses two different distance metrics, Mahalanobis and Euclidean, to analyze protein sequences and evaluate the similarity between candidate genes and established T2DM genes.

## Project Structure

```plaintext
├── notebook/
│   ├── mahabolis.ipynb         # Mahalanobis distance-based analysis notebook
│   └── euclidean.ipynb         # Euclidean distance-based analysis notebook
├── results/
│   ├── mahabolis/              # Results for Mahalanobis distance-based analysis
│   └── euclidean/              # Results for Euclidean distance-based analysis
├── asset/
│   ├── ppt.pptx               # PowerPoint presentation
│   └── report.pdf             # Detailed project report
├── README.md                  # Project overview and instructions
├── LICENSE                    # Project license
```

## Project Overview

**Project Overview**
The goal of this project is to prioritize candidate genes involved in Type II Diabetes Mellitus (T2DM) using similarity-based techniques. The analysis process involves transforming protein sequences into vector representations and calculating their pairwise similarities using distance metrics such as Mahalanobis and Euclidean distances. The final goal is to identify genes with a high frequency of similarity to known T2DM genes.

**Key Steps**:
  1. Data Collection: Gathered protein sequences related to T2DM.

  2. Feature Extraction: Calculated the moment of inertia based on the amino acid properties.

  3. Distance Metric Calculation: Implemented both Mahalanobis and Euclidean distances to calculate pairwise similarities.

  4. Logarithmic Transformation: Since the distance values exhibited irregular and uneven ranges, I applied a logarithmic transformation to normalize the range of the distance matrix and convert it into an even scale.

  5. Distance Matrix Prioritization: After computing the distance matrix, I converted it into a binary matrix by applying a threshold.

The threshold was determined using the formula:

```python
  max_val = int(df.to_numpy().max() - df.to_numpy().min())  # difference between max. dist and min dist
  threshold = 0.01 * m
```

This step was essential to classify distances as closer (1) or farther (0), enabling me to focus on similar genes for further analysis.

  6. Gene Prioritization: I then calculated the frequency of each gene being predicted as similar to a known T2DM gene. This helped in sorting and prioritizing genes based on their similarity and frequency. I only considered those gene groups with a frequency of 14 or above, to ensure the analysis focused on the most consistently predicted genes.

  7. Results Evaluation: The Mahalanobis distance method provided more accurate results compared to Euclidean distance, with the former showing a better alignment with known T2DM genes.
Results. 

## Results

The Mahalanobis distance-based analysis outperformed the Euclidean distance approach in terms of prediction accuracy. The Mahalanobis method showed better alignment with the known T2DM genes, indicating a more precise identification of candidate genes related to the disease.

- **Mahalanobis Results**: 
    - The Mahalanobis distance provided a more accurate representation of the genetic similarities and led to better prioritization of candidate genes.

- **Euclidean Results**:
    - The Euclidean distance method provided useful insights but was less accurate in comparison to the Mahalanobis method.

## Conclusion

In this project, I used both the Mahalanobis and Euclidean distance metrics to analyze protein sequences associated with T2DM. After comparing the results, I found that the Mahalanobis distance method performed better, providing more accurate predictions for gene prioritization.

## Technology Used

- **Programming Languages**: Python
- **Libraries/Frameworks**: Biopython, NumPy, Pandas, Matplotlib, Seaborn
- **Distance Metrics**: Mahalanobis, Euclidean
- **Tools**: Jupyter Notebook, Git

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
