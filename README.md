# Unsupervised Learning: DBSCAN Clustering on Random Dataset

## Project Overview

This project demonstrates the application of the DBSCAN (Density-Based Spatial Clustering of Applications with Noise) clustering algorithm, a key technique in unsupervised machine learning and knowledge discovery. The algorithm is applied to a synthetically generated dataset to identify clusters of varying shapes and distinguish noise points (outliers).

This notebook was created as part of a final project for a Knowledge Discovery and Data Mining course during a Master's degree program.

## How it Works

1.  **Data Generation**: A 2D dataset is synthetically generated using `sklearn.datasets.make_blobs`. This function creates isotropic Gaussian blobs suitable for clustering analysis.
    * `n_samples`: 2500 points are generated.
    * `centers`: The data is generated around 3 predefined centers: `[[4,3], [2,-1], [-1,4]]`.
    * `cluster_std`: The standard deviation within clusters is set to 0.5.
2.  **Initial Visualization**: The raw generated data points are visualized using `matplotlib.pyplot.scatter` to show their initial distribution.
3.  **Data Preprocessing**: The features (`X`) are standardized using `sklearn.preprocessing.StandardScaler`. This removes the mean and scales the data to unit variance, which is often beneficial for distance-based algorithms like DBSCAN.
4.  **DBSCAN Clustering**: The DBSCAN algorithm (`sklearn.cluster.DBSCAN`) is applied to the standardized data.
    * `eps`: The maximum distance between two samples for one to be considered as in the neighborhood of the other is set to 0.3.
    * `min_samples`: The number of samples in a neighborhood for a point to be considered a core point is set to 8.
    * The model is fitted to the data, and cluster labels are assigned to each point. Points labeled -1 are considered noise/outliers.
5.  **Results Visualization**: The final clustering results are visualized:
    * Points belonging to identified clusters are plotted in different colors.
    * Noise points (outliers) identified by DBSCAN are plotted in black.
    * Core samples and non-core samples within clusters are distinguished visually (though plotted with the same marker and color in the final plot).

## Libraries Used

* NumPy
* Scikit-learn (`sklearn.cluster.DBSCAN`, `sklearn.datasets.make_blobs`, `sklearn.preprocessing.StandardScaler`)
* Matplotlib (`matplotlib.pyplot`)

## How to Run

1.  Ensure you have Python and the necessary libraries installed (`pip install numpy scikit-learn matplotlib jupyter`).
2.  Download the `.ipynb` file (`C. Unsupervised Learning - Clustering DBSCAN Random Dataset.ipynb`).
3.  Run Jupyter Notebook or Jupyter Lab (`jupyter notebook` or `jupyter lab`).
4.  Open the downloaded `.ipynb` file.
5.  Execute the cells sequentially (e.g., using "Run All" or Shift+Enter for each cell).

## Results

The notebook outputs two scatter plots:
1.  The initial randomly generated dataset.
2.  The dataset after applying DBSCAN, showing the identified clusters in distinct colors and noise points in black. This visualization helps understand how DBSCAN groups dense regions and identifies outliers based on the chosen `eps` and `min_samples` parameters.
