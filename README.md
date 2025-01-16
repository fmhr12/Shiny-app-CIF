# Fine-Gray Model Prediction & SHAP Explanation Shiny App

## Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Installation](#installation)
  - [Prerequisites](#prerequisites)
  - [Required R Packages](#required-r-packages)
- [Usage](#usage)
- [Acknowledgments](#acknowledgments)

## Overview

The **Fine-Gray Model Prediction & SHAP Explanation** Shiny app is an interactive web application designed for survival analysis using the Fine-Gray model. It allows users to input predictor variables, generate Cumulative Incidence Function (CIF) curves, view CIF values at specified time points, and visualize feature contributions through SHAP (SHapley Additive exPlanations) force plots. This tool is particularly useful for medical researchers and data scientists interested in understanding the impact of various factors on survival outcomes.

## Features

- **Interactive User Interface**: Easily input predictor variables through dropdowns and numeric fields.
- **CIF Curve Visualization**: Generate and interact with CIF curves using Plotly for enhanced data exploration.
- **CIF Value Extraction**: Retrieve CIF values at user-specified time points.
- **SHAP Explanations**: Visualize feature contributions to model predictions with SHAP force plots.
- **Reference Curve Option**: Overlay the average CIF curve for comparative analysis.
- **Responsive Design**: User-friendly layout with tabs for organized presentation of results.

## Installation

### Prerequisites

- **R**: Ensure that R is installed on your system. You can download it from [CRAN](https://cran.r-project.org/).

### Required R Packages

The application relies on several R packages. You can install them using the following commands in your R console:

```r
install.packages(c(
  "shiny",
  "shinythemes",
  "survival",
  "riskRegression",
  "dplyr",
  "fastshap",
  "shapviz",
  "ggplot2",
  "readxl",
  "prodlim",
  "cluster",
  "plotly"
), repos = "https://cran.rstudio.com/")
```

### Installation Steps

1. **Clone or Download the Repository**: Obtain the app's source code and ensure all necessary files are present.
2. **Place Data Files**: Ensure that the following `.rds` files are in the same directory as the app:
   - `final_fg_model.rds`
   - `precomputed_shap_grid_multi_times2.rds`
   - `mean_cif_data.rds`
3. **Launch the App**:
   - Open the R script containing the Shiny app in RStudio or your preferred R environment.
   - Run the app by executing the following command in the R console:
     ```r
     shiny::runApp("path_to_app_directory")
     ```
     Replace `"path_to_app_directory"` with the actual path to the directory containing the app files.

## Usage

Once the app is running, follow these steps to perform predictions and generate explanations:

1. **Input Predictor Values**: On the sidebar, enter the required predictor variables:
   - **Insurance Type**: Select from "No Insurance", "Private", or "Public".
   - **Node Status**: Choose from N0, N1, N2, or N3.
   - **Periodontal Grading**: Select grading from 0, I, II, III, or IV.
   - **Tumor Site**: Choose between "Others", "Oropharynx", or "Oral Cavity".
   - **Age**: Enter age in years.
   - **Smoking Pack-Year**: Input the number of pack-years smoked.
   - **Income (in $1000)**: Specify income in thousands of dollars.
   - **Number of Teeth After Extraction**: Enter the number of teeth remaining.
   - **RT Dose (Gy)**: Input the radiation therapy dose.
   - **D20 (Gy)**: Enter the D20 value.
   - **Time Points (comma-separated)**: Specify the time points (in months) for which you want CIF values.

2. **Optional Settings**:
   - **Show Reference (Average CIF)**: Check this box to overlay the average CIF curve on the plot.

3. **Generate Results**:
   - Click the **"Predict & Explain"** button to generate the CIF curve, CIF values at specified time points, and the SHAP force plot.

4. **View Results**: Navigate through the tabs in the main panel to view:
   - **CIF Curve**: An interactive plot showing the CIF over time.
   - **CIF Values at Requested Time Points**: A table displaying CIF values at the specified times.
   - **SHAP Force Plot**: A visualization of feature contributions to the prediction.

## Acknowledgments

- **Shiny**: For providing a robust framework for building interactive web applications in R.
- **shinythemes**: For the elegant UI themes.
- **survival & riskRegression**: Essential packages for survival analysis.
- **fastshap & shapviz**: For enabling SHAP explanations.
- **Plotly**: For creating interactive plots.
- **ggplot2**: For data visualization.
- **dplyr**: For data manipulation.
