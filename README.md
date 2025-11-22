# Predicting Daily Land Average Earth Temperature

Authors: Molly Kessler, Daisy Zhou, Ojasv Issar, Jacob Cann

## Summary

This project applies a linear regression algorithm to a data set of daily average land temperature of the Earth from January 1800 through July 2022 to predict the daily average land temperature of the Earth in the near future.

In our exploratory data analysis, we excluded data from 2013 to 2022 to avoid violating the golden rules. We observed a clear increasing trend in the mean daily land temperature from 1880 to 2012, suggesting that a linear model could generalize to future unseen years. To ensure that seasonality was not influencing the trend, We created faceted plots by month to confirm that the pattern persisted across all months. Additionally, our density plots at selected time points indicates a notable shift towards a higher mean daily land temperatures over time.

For the modeling part, we converted daily temperature anomalies into yearly averages to capture long-term trends while minimizing short-term fluctuations. Our dataset was split into training set (year 1880-2012) and test set (2013-2022) to evaluate how well our model performed in predicting future daily land temperature. To pick the best model, we compared three models: Linear Regression, Random Forest, and Support Vector Regressor (SVR). We selected three metrics: RMSE, MAE and R² to evaluate each model. I the end, we used the trained SVR model with the lowest error scores and the highest R² to forecast the 2023 temperature anomaly to be approximately **+1.97 °C** relative to the baseline, corresponding to a projected global land-average temperature of about **10.56 °C.** The result is aligned with global warming trend.

## Data

The data set for this project was published by Berkeley Earth under a Creative Commons BY-NC 4.0 International license, free for non-commercial use, and accessed by our team compliant with the conditions in this license on November 18, 2025. The raw data can be found at <https://berkeley-earth-temperature.s3.us-west-1.amazonaws.com/Global/Complete_TAVG_daily.txt>.

The data set contains 5 columns with time series information, and one column representing the temperature difference relative to the average temperature between January 1951 and December 1980, which they calculated as 8.59 +/- 0.05. For our analysis, we preprocessed the data to get the raw temperature readings back by adding 8.59 to each entry in the Anomaly column. All temperatures are in Celcius.

## Dependencies

The software dependencies for this project are managed via conda environments. To install the relevant dependencies, follow the instructions in the Setup Environment section below.

## Running the Analysis

Follow the instructions to run the analysis or modify the project in an editor.

### Setup Environment

1.  Ensure Conda is installed on your machine.

2.  Clone the GitHub repository to your machine.

3.  Open a command line interface (e.g. Terminal) on your machine and navigate to the root of this repository. Enter the following command to create a new conda environment from the environment.yml file. If prompted to install packages and dependencies, type 'y' (yes).

`conda env create --file environment.yml`

4.  Switch to the `climate-env` conda environment using the following command.

`conda activate climate-env`

### Run (or modify) Analysis

1.  Ensure you are in the root of this repository and the appropriate conda environment is active.

2.  Open the repository with your preferred code editor. If you would like to use JupyterLab, you may need to manually install the `ipykernel` package into the `climate-env` conda environment using the command `conda install ipykernel`, and ensure the `nb_conda_kernels` package is installed in the same conda environment on your machine where Jupyter Lab is installed.

3.  In your code editor, navigate to the analysis.ipynb document and explore the interactive analysis.

#### Adding a dependency

1.  Install the files in your conda environment.

2.  Create and switch to a new branch.

3.  Create a new environment file from your current conda environment using the command `conda env export -f environment.yml --from-history`.

4.  Open the environment.yml file in an editor and manually remove the line starting with `prefix:`. Additionally, ensure all packages have an exact version specified.

5.  Push the new environment.yml file to your branch on GitHub. Send a pull request to merge the changes into the main branch.

## License

The Predicting Daily Land Average Earth Temperature report contained herein are licensed under the Attribution-NonCommercial-ShareAlike 4.0 International (CC BY-NC-SA 4.0) License. See the license file for more information. If re-using/re-mixing please provide attribution and link to this webpage. The software code contained within this repository is licensed under the MIT license. See the license file for more information.
