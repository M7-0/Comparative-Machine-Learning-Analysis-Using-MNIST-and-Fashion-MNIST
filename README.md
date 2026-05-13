# Comparative Machine Learning Analysis: MNIST vs. Fashion-MNIST

This project provides a comparative analysis of the MNIST (digit recognition) and Fashion-MNIST datasets. It explores dataset characteristics and evaluates model performance using common machine learning metrics.

## Introduction
Image classification is a visual recognition process that requires accurate pixel data. Computers collect a great amount of numeric data from digital images; however, raw pixels don’t have that great usefulness to determine what the image represents, whether it is a specific handwriting or a piece of clothing. This process requires a deep understanding of the relationship between certain pixel patterns, such as edges, contracts, or shapes, and the actual object being viewed. Even though the normal person can easily understand these visual relationships, manually sorting and categorizing hundreds or thousands of images will be too long and too slow; therefore, to automate the process, an intelligent agent that understands those visual relationships and can accurately predict the correct category of an image must be developed.

## Data Description
The two data sets were selected from Kaggle:
- **MNIST**: A dataset of handwriting digits from 0-9. The dataset has 70,000 greyscale images centered within 28 x 28 pixels (60,000 training, 10,000 testing).
- **Fashion-MNIST**: A dataset about clothing. The dataset has 70,000 greyscale images at 28 x 28 pixels (60,000 training, 10,000 testing).

### Dataset Exploration
Before training, the data was explored for structure and class distribution:
- **MNIST**: Classes are balanced with approximately 6,000 images per digit.
- **FMNIST**: Each clothing category contained 6,000 training images, confirming a balanced dataset. FMNIST images are noticeably more complex than MNIST, making them harder to classify.

## Data Preprocessing
Data preprocessing was essential before training the machine learning models.
1. **Combining**: Original training and testing sets were combined into one complete dataset of 70,000 images for both MNIST and FMNIST.
2. **Normalization**: Pixel values (0-255) were divided by 255 to scale them to a range of 0 to 1.
3. **Reshaping**: Each 28x28 image was converted into a one-dimensional vector with 784 features.
4. **Splitting**: The data was divided using an 80/20 train-test split (56,000 training samples and 14,000 testing samples).

## Model Training
Three machine learning models from Scikit-learn were used:
- **Logistic Regression**: max_iter=200 was used to improve convergence.
- **K-Nearest Neighbors (KNN)**: n_neighbors=5 was used for training stability.
- **Decision Tree**

## Results

### Performance on MNIST
| Model | Accuracy | Error Rate |
| :--- | :--- | :--- |
| Logistic Regression | 92.28% | 7.72% |
| **KNN** | **96.88%** | **3.12%** |
| Decision Tree | 87.62% | 12.38% |

### Performance on Fashion-MNIST
| Model | Accuracy | Error Rate |
| :--- | :--- | :--- |
| Logistic Regression | 85.12% | 14.88% |
| **KNN** | **85.89%** | **14.11%** |
| Decision Tree | 79.51% | 20.49% |

## Comparison and Discussion
- **Best Performing Model**: KNN achieved the highest accuracy and lowest error rate on both datasets.
- **Dataset Complexity**: Models performed significantly better on MNIST. FMNIST is more challenging due to similar shapes and complex patterns in clothing items (e.g., Shirt vs. T-shirt).
- **Algorithm Performance**: KNN handles image similarity well, while the Decision Tree struggled with high-dimensional image data.

## Conclusion
- KNN is the most effective model for this project across both datasets.
- MNIST is easier to classify due to simple, distinct features.
- Fashion-MNIST is more challenging due to high similarity between classes.

## Setup
1. Clone this repository.
2. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Open `Project.ipynb` in your Jupyter environment.
