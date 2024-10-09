# MNIST Digit Classification with MLP (Multilayer Perceptron)

## Overview
This project focuses on classifying a subset of the MNIST dataset containing handwritten digits **3, 4, and 5** using a **Multilayer Perceptron (MLP)** neural network. The classification task is enhanced by various feature extraction techniques applied to the images. Instead of using raw pixel values, we extract specific characteristics from the image columns and use them as input features for the model.

The feature extraction methods include statistical and structural techniques, providing an alternative approach to working directly with pixel intensities. The input data is processed into 28 features per image, where each feature represents a unique statistic derived from one of the 28 columns of the MNIST image.

## Feature Extraction Methods
We employ five different feature extraction techniques to transform each image into a more compact and informative representation:

1. **Median**: 
   - Calculates the median pixel value for each column of the image. This approach reduces the influence of outliers and noise by focusing on the central tendency of pixel intensities.
   
2. **Variance**:
   - Measures the variability in pixel values for each column. High variance indicates that the column contains a wide range of pixel intensities, often signifying the presence of edges or detailed features.
   
3. **Entropy**:
   - Computes the entropy for each column by analyzing the distribution of pixel intensities. Higher entropy values suggest more randomness or complexity in the column, often corresponding to areas with detailed textures or patterns.
   
4. **Interquartile Range (IQR)**:
   - Extracts the spread of pixel intensities by calculating the difference between the 75th and 25th percentiles. IQR is another measure of dispersion that, like variance, indicates the spread of pixel values but is more resistant to outliers.
   
5. **Correlation**:
   - Measures the Pearson correlation between each column of an image and a reference column derived from the average of all images in the training set. This method captures how closely each column follows the general pattern of the dataset, making it useful for identifying columns that behave consistently across images.

## Instructions to Run
Follow these steps to run the project:

1. **Clone the repository**:
    ```
    git clone https://github.com/lfelipecas/ann-mlp-mnist-345.git
    ```

2. **Install the dependencies**:
    ```
    pip install -r requirements.txt
    ```

3. **Open the Jupyter notebook**:
    ```
    jupyter notebook ANN_MLP_Mnist_345.ipynb
    ```

4. **Run the notebook**:
    - The notebook includes code for loading the filtered MNIST dataset (containing only digits 3, 4, and 5), applying feature extraction techniques, and training an MLP model on the extracted features.
    - The notebook also generates visualizations, including accuracy and loss curves, confusion matrices, and random sample predictions.

## Results
For each feature extraction method, the following results are generated:

- **Training and Validation Accuracy**: Plotted over the course of training epochs, this shows how well the model is learning to classify the digits based on the extracted features.
  
- **Training and Validation Loss**: This plot tracks the model's loss function, showing how well it is minimizing errors over time.

- **Confusion Matrix**: A matrix that visualizes the classification performance by comparing the predicted digit classes with the actual ones. It provides a detailed view of how many times each digit is misclassified.

- **Predicted vs Actual Labels**: Random test images are displayed with their predicted and actual labels, allowing for visual comparison of the model’s predictions against the ground truth.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.