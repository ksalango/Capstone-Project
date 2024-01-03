# Temporal Dynamics in Wave Power: A Machine Learning Approach

**Table of Contents:**
- [Introduction](#introduction)
- [Methodology](#methodology)
- [Data](#data)
- [Notebooks](#notebooks)
- [References](#references)
- [Configuration](#configuration)
- [Getting Started](#getting-started)
- [Weekly To-Do List](#weekly-to-do-list)
- [Data Dictionary](#Data-Dictionary)


## Introduction
Welcome to my Wave Power Predictor project, this project stemms my three-month journey through the BrainStation Data Science Bootcamp. This project seeks to leverage the power of machine learning to forecast wave power at a specific location. Unlike computationally intensive numerical and physics-based models, machine learning offers a potentially more efficient approach.

The foundation of this project lies in compiling a data set from historical buoy data and hindcast model data from similar locations and using this for a machine learning model approach. Looking ahead, the prospect of incorporating real-time data opens the door to a live wave energy forecasting model.

The overarching objective is to deliver a prediction model that is accurate as well as robust, addressing a specific location's unique dynamics. The potential applications span from contributing to renewable energy research to serving the interests of avid surf enthusiasts.

 
 ## The methodology is divided into the following key steps:

1. **Data Collection:**
   - Gather hindcast data, representing historical wave conditions.
   - Collected additional historical data for testing and validation.

2. **Hindcast Data Processing and Exploratory Data Analysis (EDA):**
   - Conduct cleaning and exploratory data analysis on the hindcast dataset.
   - Explored temporal patterns and key features influencing wave power.

3. **Historical Data Processing and EDA:**
   - Clean and explore the historical dataset, ensuring alignment with hindcast data in terms of temporal features.
   - Identify and incorporate additional relevant features for model testing.
   - Build working Data Frame. 
     
4. **Baseline Model Development:**
   - Build and train a baseline machine learning model, incorporating time series analysis techniques.
   - Utilize the hindcast data to establish an initial predictive framework.

5. **Model Testing and Iteration:**
   - Test the trained model on the historical dataset, evaluating its performance.
   - Iteratively refine the model based on testing outcomes, incorporating feedback and insights.
   - Develop live forecasting. 
 

## Data
You can access the latest project dataset on Google Drive:
[Download Latest Dataset](https://drive.google.com/drive/folders/103uoc3UW-73YHMsvDNyMVQsZfuzLDKWG?usp=sharing)

## Notebooks 
Description of notebooks will go here. 

## References
link to references: 

## Configuration
The project configuration settings are stored in the `/settings/capstone_wavepower.yml` file. 

## Getting Started
-instructions on how to get started with project will go here. 


## Weekly To-Do List

- [x] Collect Hindcast Data from three relevant grid points
- [X] Format and clean Hindcast Data
- [X] Format and clean Historical Buoy Data
- [X] EDA of Hindcast Data and Buoy Data
- [ ] Build baseline model using time series analysis and linear regression

## Data Dictionary
<details>
  <summary>Data Dictionary</summary>

**Note on Directions:**
Directions are given in degrees corresponding to True North:
- North (N): 0° = 360°
- East (E): 90°
- South (S): 180°
- West (W): 270°

- **Index, - DATE:** Date time excluding minutes, both df_buoy and df_hind joined on this column.
- **STN_ID:** Buoy station ID.
- **Datetime_x:** Datetime from df_buoy
- **DEPTH:** Depth in meters.
- **VWH$:** Characteristic significant wave height (reported by the buoy) (m)
- **VCMX:** Maximum zero crossing wave height (reported by the buoy) (m)
- **VTP$:** Wave spectrum peak period (reported by the buoy) (s)
- **WDIR:** Direction from which the wind is blowing (° True)
- **WSPD:** Horizontal wind speed (m/s)
- **WSS$:** Horizontal scalar wind speed (m/s)
- **GSPD:** Gust wind speed (m/s)
- **ATMS:** Atmospheric pressure at sea level (mbar)
- **DRYT:** Dry bulb temperature (air temperature) (°C)
- **SSTP:** Sea surface temperature (°C)
- **Q_FLAG:**
  - 0 - Blank: No quality control (QC) has been performed
  - 1 - Good: QC has been performed; record appears correct
  - 3 - Doubtful: QC has been performed; record appears doubtful
  - 4 - Erroneous: QC has been performed; record appears erroneous
  - 5 - Changes: The record has been changed as a result of QC
  - 6 - Acceptable: QC has been performed; record seems inconsistent with other records
  - 7 - Off Position: There is a problem with the buoy position or mooring. Data may still be useful.
  - 8 - Reserved
  - 9 - Reserved: Indicates missing elements
- **Datetime_y:** Date time in 3-hour intervals from df_hind
- **WD:** Wind Direction (deg from which wind is blowing (° True))
- **WS:** Wind Speed (m/s)
- **ETOT:** Total Variance of Total Spectrum (m^2)
- **TP:** Peak Spectral Period of Total Spectrum (sec)
- **VMD:** Vector Mean Direction of Total Spectrum (deg to which)
- **ETTSea:** Total Variance of Primary Partition (m^2)
- **TPSea:** Peak Spectral Period of Primary Partition (sec)
- **VMDSea:** Vector Mean Direction of Primary Partition (deg to which)
- **ETTSw:** Total Variance of Secondary Partition (m^2)
- **TPSw:** Peak Spectral Period of Secondary Partition (sec)
- **VMDSw:** Vector Mean Direction of Secondary Partition (deg to which)
- **MO1:** First Spectral Moment of Total Spectrum (m^2/s)
- **MO2:** Second Spectral Moment of Total Spectrum (m^2/s^2)
- **HS:** Significant Wave Height (m)
- **DMDIR:** Dominant Direction (deg to which)
- **ANGSPR:** Angular Spreading Function
- **INLINE:** In-Line Variance Ratio

</details>
 


