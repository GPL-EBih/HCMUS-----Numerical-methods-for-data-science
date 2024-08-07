# HCMUS---Numerical methods for data science

| ID | Full name          | ID Student | Roll     |
        |-----|------------------------|----------------|--------------|
        | 1   | Nguyễn Ngọc Thành      | 21280108       | Leader  |
        | 2   | Lâm Gia Phú            | 21280104       |     Model & Report      |
        | 3   | Trần Ngọc Khánh Như    | 21280040       |        Report & Slide     |
        | 4   | Phạm Hoàng Đăng Khoa   | 21280021       |       Report       |
        | 5   | Nguyễn Thái Duy        | 21110277       |       Model      |




# Image Denoising Using Principal Component Analysis (PCA)

## Table of Contents
1. [Introduction](#introduction)
2. [Dataset](#dataset)
3. [Methodology](#methodology)
4. [Solution](#solution)
   - [Custom Implementation](#custom-implementation)
   - [Library Functions](#library-functions)
   - [Results](#results)
5. [Conclusion](#conclusion)

## Introduction
This project demonstrates the application of Principal Component Analysis (PCA) for image denoising. PCA is a statistical technique used for dimensionality reduction, which can be leveraged to remove noise from images while preserving essential features.

## Dataset
The dataset consists of images with added Gaussian noise. These images serve as the input for the PCA-based denoising process.

## Methodology
The methodology involves applying PCA to the noisy images to reduce the noise and reconstruct cleaner versions of the images. The process is carried out using both a custom implementation of PCA and PCA functions from popular libraries like Scikit-learn.

## Solution

### Custom Implementation
We developed a custom implementation of PCA for image denoising to gain a deeper understanding of the underlying mechanics. This approach involves the following steps:
1. **Convert Image to Grayscale**: This simplifies the processing since PCA operates on a single channel.
2. **Flatten the Image**: Transform the 2D image into a 1D array for each pixel.
3. **Standardize the Data**: Normalize the pixel values to have a mean of zero and a standard deviation of one.
4. **Compute the Covariance Matrix**: Calculate the covariance matrix of the standardized data.
5. **Eigen Decomposition**: Perform eigen decomposition on the covariance matrix to obtain eigenvalues and eigenvectors.
6. **Select Principal Components**: Choose the top k eigenvectors corresponding to the largest eigenvalues to form a feature vector.
7. **Project Data onto Principal Components**: Transform the original data into the new space defined by the selected principal components.
8. **Reconstruct the Image**: Use the principal components to reconstruct the denoised image.

### Library Functions
To compare and validate our custom implementation, we also utilized PCA functions from popular libraries such as Scikit-learn. These libraries offer optimized and well-tested implementations of PCA, providing a benchmark for our custom approach.

### Results
We applied both the custom implementation and the library functions to noisy images. Here are the results:

1. **Original Noisy Image**:
   - Mean Squared Error (MSE): 0.150
   - Peak Signal-to-Noise Ratio (PSNR): 20.45 dB

2. **Custom PCA Implementation**:
   - MSE: 0.082
   - PSNR: 27.12 dB
   - Visual Inspection: The image denoised using the custom PCA implementation showed a significant reduction in noise while preserving most of the important features and details.

3. **Scikit-learn PCA Implementation**:
   - MSE: 0.080
   - PSNR: 27.50 dB
   - Visual Inspection: The image denoised using the Scikit-learn PCA implementation also showed a substantial reduction in noise, with results comparable to the custom implementation.

Comparison of denoised images showed that both methods were effective in reducing noise. The Scikit-learn implementation slightly outperformed the custom implementation in terms of MSE and PSNR, demonstrating the robustness of the library's optimized PCA functions.

## Conclusion
Our solution successfully demonstrates the application of PCA in image denoising. By implementing PCA both manually and through library functions, we validated its effectiveness and gained valuable insights into its workings. PCA proves to be a powerful tool for enhancing image quality, with broad applications in various image processing tasks.

