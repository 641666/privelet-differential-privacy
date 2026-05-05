# privelet-differential-privacy
A Python implementation of the Privelet method for differentially private histogram release, using Haar wavelet transform and Laplace noise to study the trade-off between privacy and utility.

## Project Description
This project implements the one-dimensional Privelet algorithm for differential privacy on histogram data.

The dataset used in this project is `adult.data` from the Adult dataset.  
The target query is the histogram of education level (H1).

The project includes:
- implementation of the 1D Haar wavelet transform
- addition of Laplace noise to wavelet coefficients
- reconstruction of the noisy histogram
- evaluation using Wasserstein distance
- go further on more epsilon values
- 
## Requirements
This project uses Python 3.12.7

Required libraries:
- numpy
- pandas
- matplotlib
- scipy
- notebook

## Installation
Install the required libraries with:

```bash
pip install numpy
pip install pandas
pip install matplotlib
pip install scipy
pip install notebook
```
## Dataset

The project uses the file adult.data.

Please place this file in the data/ folder before running the notebook.

Expected path:
data/adult.data

## Project Structure

```text
project/
├─ data/
│  └─ adult.data
├─ notebook/
│  └─ privelet_experiment.ipynb
└─ README.md
```

## Main Functions

1. wavelet_transform(hist)
Converts the raw histogram into Haar wavelet coefficients.

2. add_laplace_noise(coeffs, epsilon, random_state=None)
Adds Laplace noise to the wavelet coefficients according to the privacy budget epsilon.

3. inverse_wavelet_transform(coeffs)
Reconstructs a histogram from the wavelet coefficients.

4. privelet_1d(hist, epsilon, random_state=None)
Runs the full 1D Privelet pipeline: raw histogram -> wavelet transform -> noisy coefficients -> inverse transform -> noisy histogram

## Main Features

- Built a histogram from the Adult dataset education attribute
- Implemented 1D Haar wavelet transform and inverse transform
- Added Laplace noise to wavelet coefficients under different ε values
- Reconstructed noisy histograms
- Evaluated utility loss using Wasserstein distance
- Compared the privacy-utility trade-off across multiple random runs

## Results

The experiments show that smaller ε values provide stronger privacy but introduce larger errors.  
When ε increases, the noisy histogram becomes closer to the original histogram, and the Wasserstein distance decreases.

## Author
Siying Liu
