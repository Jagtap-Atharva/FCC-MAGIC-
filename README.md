# FCC MAGIC Dataset Example

This repository contains a Jupyter notebook (`fcc-MAGIC-example.ipynb`) that demonstrates a complete machine learning workflow using the MAGIC Gamma Telescope dataset. The project showcases data preprocessing, neural network training with hyperparameter optimization, and model evaluation for gamma ray classification.

## Overview

The MAGIC dataset is used to classify gamma rays from hadrons based on features extracted from telescope images captured by the Major Atmospheric Gamma Imaging Cherenkov (MAGIC) telescope. This project implements a neural network approach to find the optimal model configuration through systematic hyperparameter tuning.

## Dataset

The dataset (`magic04.data`) contains measurements from the MAGIC telescope and can be downloaded from the [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/159/magic+gamma+telescope). Place the file in the same directory as the notebook.

### Features
- `fLength`: Length of the major axis of the ellipse
- `fWidth`: Width of the minor axis of the ellipse  
- `fSize`: Size (measured by the pixel content of the image)
- `fConc`: Concentration ratio (pixel sum in ellipse vs. total)
- `fConc1`: Concentration ratio of highest pixel vs. total
- `fAsym`: Asymmetry (3rd root of 3rd moment along major axis)
- `fM3Long`: 3rd moment along major axis
- `fM3Trans`: 3rd moment along minor axis
- `fAlpha`: Angle between major axis and vector to origin
- `fDist`: Distance from origin to center of ellipse

### Target Variable
- `class`: 'g' for gamma ray, 'h' for hadron (converted to binary 1/0 in preprocessing)

## Requirements

- Python 3.12+
- Jupyter Notebook

### Dependencies
Install the required packages using pip:

```bash
pip install numpy pandas matplotlib scikit-learn imbalanced-learn tensorflow
```

## Installation & Usage

1. **Clone the repository:**
   ```bash
   git clone https://github.com/Jagtap-Atharva/fcc-magic-example.git
   cd fcc-magic-example
   ```

2. **Download the dataset:**
   - Download `magic04.data` from the UCI repository link above
   - Place it in the root directory of the project

3. **Launch Jupyter Notebook:**
   ```bash
   jupyter notebook
   ```

4. **Run the analysis:**
   - Open `fcc-MAGIC-example.ipynb`
   - Execute all cells to run the complete workflow

## Key Features

### Data Preprocessing
- **Standardization**: Features are scaled using StandardScaler for optimal neural network performance
- **Class Imbalance Handling**: SMOTE (Synthetic Minority Oversampling Technique) is applied to balance the dataset

### Hyperparameter Optimization
The notebook systematically explores different model configurations:
- **Hidden Layer Nodes**: 16, 32, 64
- **Dropout Rates**: 0.0, 0.2
- **Learning Rates**: 0.01, 0.005, 0.001
- **Batch Sizes**: 32, 64, 128

### Model Architecture
- Simple feedforward neural network built with Keras/TensorFlow
- Dense layers with ReLU activation
- Dropout layers for regularization
- Binary classification output with sigmoid activation

### Evaluation Metrics
- Training and validation accuracy
- Training and validation loss
- Model selection based on lowest validation loss
- Performance visualization through training history plots

## Results

The notebook trains multiple model configurations and automatically selects the best-performing model based on validation loss. Training progress is visualized with matplotlib plots showing accuracy and loss curves over epochs.

## File Structure

```
fcc-magic-example/
├── README.md
├── fcc-MAGIC-example.ipynb
├── magic04.data
└── LICENSE (optional)
```

## Contributing

Feel free to open issues or submit pull requests if you have suggestions for improvements or find any bugs.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Dataset provided by the UCI Machine Learning Repository
- Original data collected by the MAGIC collaboration
- Inspiration from machine learning classification techniques for astrophysics applications
