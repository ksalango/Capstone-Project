# Wave Prediction: Building my own Surf Forecast

**Table of Contents:**
- [Introduction](#introduction)
- [Methodology](#methodology)
- [Data](#data)
- [Notebooks](#notebooks)
- [References](#references)
- [Configuration](#configuration)
- [Getting Started](#getting-started)
- [Conclusion/Next Steps](#conclusionnext-steps)
- [(Weekly) To-Do List](#(weekly)-to-do-list)
- [Data Dictionary](#Data-Dictionary)


## Introduction
Welcome to my wave prediction project, this project stemms my three-month journey through the BrainStation Data Science Bootcamp. In this project I aim to build my own surf forecast. The idea for this project started when Magic Seaweed was discontinued in 2022. It was an online surf forecast that I found to be more accurate. Now surfline is widely used as the main surf forecasting website for surfers around the world. My goal in this project is to create a surf forecast for my local area that is more accurate than the forecast for my area on surfline.  

The foundation of this project lies in compiling a data set from historical buoy data and hindcast model data from a similar location and using this for a machine learning approach to better understand local wave dynamics and build a forecasting model. Looking ahead, the prospect of incorporating real-time data opens the door to a live surf forecasting model for a specific location that produces more precise forecasts. 

There are many different components of a surf forecast including, wave height, wave period, swell direction, wind speed and direction. For the scope of this project I chose to focus on forecasting wave height and wave period. In later stages of this project I hope to add other components as more machine learning methods will be explored. 

The overarching objective of the project thusfar is to deliver a model or set of models that predict wave height and wave period with an error range that is below the set benchmarks as well as better understand the relationship between wave height and wave period, and how this can affect the methods applied in forecasting both. 


 
 ## The methodology is divided into the following key steps:
This is a high level overview of the methodology used in this project. More detailed methodologies are outlined at the beginning of each notebook. 
1. **Setting Benchmarks for Error Range:**
   - The benchmark of 2 feet or 0.60 meters, was decided for wave height.The benchmark range for error in wave height was decided based upon sufline's current daily forecasts that are given within a usual range of 2 feet.
   - The benchmark of 3 seconds was decided for wave period.  The benchmark for wave period was decided based on research into wave period length differentiation based on wind swell or ground swell. Generally wind swell shows wave periods of 1 to about 10 seconds, 10 to about 20 seconds is recognized as ground swell. The difference of 3 seconds is not generally indicative of a change from wind swell to ground swell.
2. **Data Collection:**
   - Gather hindcast data, representing historical wave conditions.
   - Collected historical buoy data.
   - Data was requested from Oceans and Fishers Cananda.

3. **Create a Combined Working Data Frame:**
   - Convert data where necessary into workable format for analysis.
   - Clean buoy data, and deal with error flags.
   - Assess Hindcast Data.
   - Combine data, a total of 28 years of data is obtained: 1988-2016.

3. **Data Processing and EDA:**
   - Clean and explore working dataframe.
   - Look at Distributions of features.
   - Look at relationships between features.
   - Preprocess data for Time Series Modelling:
      - A general dataframe is created for Time Series modelling.
      - Based on modelling approach data is reorganized and feature engineering is done.
      - Additional relevant features are incorportated.
      
4. **Baseline and Model Development:**
   - This project focuses on different methods for forecasting and all methods are compared and contrasted.
   - This project focuses on Supervised Machine Learning:
     - Baseline models: Univariate traditional time series; ARIMA, Linear Regression for multivariate time series.
     - Random Forest
     - XGBoost 
     - Vector Auto Regression and Neural Networks (Still in Development)

5. **Model Testing and Iteration:**
   - The same time series train test split is maintained throughout the project: 
      - split point defined as: '2006-01-01'
      - 1988-01-01 to split point defined as train.
      - split point to 2016-01-01 is defined as test.
   - Iteratively refine the model(s) based on testing outcomes, incorporating feedback and insights.
   - Feature Engineer.
    
6. **Develop Live Forecasting** 
   - This part of the project is still in development. 

## Data
You can access the latest project dataset on Google Drive:
[Download Latest Dataset](https://drive.google.com/drive/folders/103uoc3UW-73YHMsvDNyMVQsZfuzLDKWG?usp=sharing)

## Notebooks 

The scope of the project at this point focuses on directory: Forecasting_WH_WP. The other directory explores wave energy which is a separate branch of this project. The Notebooks in Forecasting_WH_WP directory are numbered reflecting the general workflow of the Project (1-6). General descriptions of notebooks in specified directory are below. More in depth descriptions are provided in the introduction to each notebook. 
 - 1_buoy_data_cleaning: This is the starting point for the project. Buoy data cleaning.
 - 2_combined_working_df: Data sets from Hindcast and buoy are combined. EDA of data. 
 - 3_Preprocessing_TS: Data is Preprocessed for Time Series modelling. 
 - 4_Wave_Period_Height_TS: First phase of Time Series modelling for wave height and wave period.  
 - 5_Ensemble: Continuation of first phase of time series modelling for wave height and wave period, focusing on XGBoost and Random Forest.
 - 6_Simultaneous_Forecast: Second phase of Time Series modelling of wave height and wave period focusing on simultaneous forecast of both features. 

## References
<details>
  <summary>Click to expand references</summary>

1. **Guide to Wave Analysis and Forecasting**
   - Link: [Guide to wave Analysis and Forecasting](https://repository.oceanbestpractices.org/bitstream/handle/11329/121/702_en_for_approval.pdf?sequence=4&isAllowed=y)

2. **MEDS Tofino**
   - Link: [MEDS Tofino](http://www.waveworkshop.org/11thWaves/Papers/ThomasSwail_LongTermCoastalWaves2009.pdf)

3. **Wave Variance Spectra Theory**
   - Link: [Wave Variance Spectra Theory](https://www.oceanopticsbook.info/view/surfaces/level-2/wave-variance-spectra-theory)

4. **A Machine Learning Framework to Forecast Wave Conditions**
   - Link: [A Machine Learning Framework to Forecast Wave Conditions](https://cdip.ucsd.edu/themes/media/docs/publications_references/journal_articles/A_Machine_Learning_Framework_to_Forecast_Wave_Conditions.pdf)

5. **Wave Energy Equation and Bathymetry 3D Model of Tofino and Ucluelet**
   - Link: [Wave energy equation and bathymetry 3D model of Tofino and Ucluelet](https://natural-resources.canada.ca/sites/www.nrcan.gc.ca/files/canmetenergy/files/pubs/CHC-TR-051.pdf) (Page 31)

6. **Waves, Swell, and Wind Waves**
   - Link: [Waves, Swell, and Wind Waves](https://www.noaa.gov/jetstream/ocean/waves)

7. **Tidal Data**
   - Link: [Tidal Data](https://www.tides.gc.ca/en/stations/08615/1980-01-01?tz=PST&unit=m)

8. **Digital Bathymetry**
   - Link: [Digital Bathymetry](https://www.ncei.noaa.gov/maps/iho_dcdb/)

9. **Nearshore Wave Energy Resources for Western Vancouver Island, BC**
   - Link: [Nearshore Wave Energy Resources for Western Vancouver Island, BC](https://natural-resources.canada.ca/sites/www.nrcan.gc.ca/files/canmetenergy/files/pubs/CHC-TR-051.pdf)

10. **MSC50 Hindcast Information**
    - Link: [MSC50 Hindcast Information](http://oceanweather.net/MSC50WaveAtlas/)

11. **MSC50 Wind and Wave Reanalysis**
    - Link: [MSC50 Wind and Wave Reanalysis](https://www.oceanweather.com/about/papers/The%20MSC50%20Wind%20and%20Wave%20Reanalysis.pdf)

12. **Grid of MSC50**
    - Link: [Grid of MSC50](https://www.google.com/maps/d/edit?hl=en&mid=1vfmJCVehadWT2z4_9cO7pm1ubvZetgI&ll=49.3890792222663%2C-128.76574706926476&z=7)

13. **Laperouse Buoy Website**
    - Link: [Laperouse Buoy Website](https://www.ndbc.noaa.gov/station_page.php?station=46206)

14. **Long Term Coastal Waves**
    - Link: [Long Term Coastal Waves](http://www.waveworkshop.org/11thWaves/Papers/ThomasSwail_LongTermCoastalWaves2009.pdf)

15. **Simulating and Forecasting Ocean Wave Energy in Western Canada**
    - Link: [Simulating and Forecasting Ocean Wave Energy in Western Canada](https://www.uvic.ca/research/projects/wcwi/assets/docs/publications/Simulating%20and%20Forecasting%20Ocean%20Wave%20Energy%20in%20Western%20Canada%20_%20OE.pdf)

16. **Definitions of Tidal Data**
    - Link: [Definitions of Tidal Data](https://tides.gc.ca/tides/en/definitions-content-tides-and-currents#Datum)

17. **Wave Energy Theory**
    - Link: [Wave Energy Theory](https://www.oceanopticsbook.info/view/surfaces/level-2/wave-variance-spectra-theory)

18. **Waves Study**
    - Link: [Waves Study](https://www.uio.no/studier/emner/matnat/geofag/GEO4964/v20/pensumliste/notes_waves.pdf)

19. **Capture Width Ratio of Wave Energy Converters**
    - Link: [A database of capture width ratio of wave energy converters](https://www.researchgate.net/publication/276452440_A_database_of_capture_width_ratio_of_wave_energy_converters#:~:text=The%20average%20capture%2Dwidth%2Dratio,%2C%202022).%20…

20. **Wave Energy, Wind, Solar**
    - Link: [Wave Energy, Wind, Solar](https://blog.sintef.com/sintefenergy/wave-energy-wind-solar/)

21. **Surf Education**
    - Link: [Surf Education](https://education.nationalgeographic.org/resource/surfs/)

22. **LOLA - What Does It Stand For?**
    - Link: [What Does LOLA Stand For?](https://www.surfline.com
</details>

## Configuration
The project configuration settings are stored in the `/settings/capstone_wavepower.yml` file. 

## Getting Started
In bash: 
- Set up environment using .yml file: 
   - conda env create -f capstone_wavepower.yml
      conda activate environment
- git clone https://github.com/ksalango/Capstone-Project.git
   - cd Capstone-Project
   - Navigate to Notebooks, navigate to Forecasting_WH_WP Directory
   - Launch Notebook
- Access Data through google drive (Link in Data)

## Conclusion/Next Steps
An in depth conclusion of project thus far is found at the end of Notebook 6. Separate models have been obtained to forecast wave height and wave period simultaneously with error range below the set error ranges for this analysis. Further feature analysis will be done from results of modelling.  Other steps include incorporating more components in forecast such as swell direction, and wind speed and direction. As well as exploring vector autoregression and neural networks. Incorporating bathymmetry data may also be explored.   

## (Weekly) To-Do List

- [ ] Feature analysis
- [ ] EDA of other components for forecast
- [ ] Feature Engineering
- [ ] Vector AutoRegression for wave height and wave period.
- [ ] Explore Neural Netowrks for forecasting. 


## Data Dictionary
This is a general data dictionary for project. As data dictionary changes from notebook to notebook specific data dictionary is included in each noteboke. 
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
 


