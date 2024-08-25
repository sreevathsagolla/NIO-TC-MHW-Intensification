# NIO-TC-MHW-Intensification
### Intensification of North Indian Ocean Tropical Cyclones driven by regional Marine Heat Waves
---------------------------------------------------------------------------------------------

This repository explores the relationship between North Indian Ocean (NIO) Tropical Cyclones (TC) and regional Marine Heat Waves (MHW). The research aims to understand how MHWs contribute to the intensification of TCs in this region. This project has been inspired from the following work: <br>

> Choi, HY., Park, MS., Kim, HS. et al. Marine heatwave events strengthen the intensity of tropical cyclones. Commun Earth Environ 5, 69 (2024). https://doi.org/10.1038/s43247-024-01239-4

## Project Overview

Marine Heat Waves (MHWs) are periods of abnormally warm ocean temperatures that can affect marine weather systems (such as tropical cyclones) and their dynamics. This project leverages historical best-track data of tropical cylones in the NIO, along with MHWs in NIO determined using daily sea surface temperature data, to analyze these interactions and study trends in TC intensification linked to MHWs.

## Data Sources

Data for the time period of 1982-2023 has been used in this project.

The tropical cyclone best-track data utilized in this project (and where they were downloaded from) are as follows:
- **JTWC** (Joint Typhoon Warning Center) [[LINK]](https://www.metoc.navy.mil/jtwc/jtwc.html?north-indian-ocean)
- **IMD** (India Meteorological Department) [[LINK]](https://rsmcnewdelhi.imd.gov.in/report.php?internal_menu=MzM=)
- **IBTRACS** (International Best Track Archive for Climate Stewardship) [[LINK]](https://www.ncei.noaa.gov/data/international-best-track-archive-for-climate-stewardship-ibtracs/v04r01/access/csv/)

The best-track data is typically at a 3-hourly temporal resolution, irrespective of the data source.

Regional marine heatwaves in the NIO have been computed from **NOAA OISST v2.1** 0.25˚ resolution daily sea surface temperature (SST) data [[LINK]](https://www.ncei.noaa.gov/products/optimum-interpolation-sst). Computation of MHWs was undertaken by Mr. Ligin Joseph (PhD student at School of Ocean and Earth Science, University of Southampton), a collaborator of this project, the code for which has been hosted on his GitHub profile as a repository [[LINK]](https://github.com/ligin1/Marine-Heat-Waves).

> For MHW masks used in `preprocessing.ipynb` haven't been hosted on this repository due to space limitations. Please email Mr. Joseph (l.joseph@soton.ac.uk) or me (sg13n23@soton.ac.uk) if you want to request access to those datafiles. 

## Repository Structure

- **`preprocessing.ipynb`**: This notebook handles data cleaning and preprocessing tasks. Raw cyclone best track data (stored in `./raw_data`) are processed and stored as 'cleaned' CSV files in the `./processed` directory.
  
- **`analysis.ipynb`**: This notebook focuses on exploratory data analysis (EDA) using the cleaned cyclone best track datasets and MHW masks. It primarily includes data visualization and classification of cyclones into MHW and NON-MHW TCs based on definitions proposed in [Choi et al., 2024](https://doi.org/10.1038/s43247-024-01239-4) cited above. Outputs from this analysis such as figures and charts are saved in the `./output` directory as a combined PDF (named as per the classification threshold definitions, the data used and the sub-basin considered).

## Workflow

1. **Data Preprocessing**: The `preprocessing.ipynb` notebook loads and processes raw datasets, ensuring consistency and removing missing values. The processed data is stored in a format suitable for analysis.

2. **Exploratory Analysis**: The `analysis.ipynb` notebook delves into the relationship between NIO TCs and MHWs. It examines metrics like maximum sustained wind speed, geographical overlap between MHW regions and cyclone paths and proximity between cyclone best track and MHW region to classify TCs based on the potential of being influenced by any MHW. 

3. **Detailed Analysis of forecast variables and Hypothesis Testing**: Further analysis is required to understand the difference between MHW TCs and NON-MHW TCs, using several other forecast variables such as precipitation rate, surface latent heat flux, wind and specific humidity analysis. This will enable us to definitively quantify the role MHWs play in potentially intensifying TCs in NIO and also help us understand how the affect may be different from what has been observed by Choi et al., 2024 in Western Northern Pacific and Tropical Atlantic. This is very much a **WORK IN PROGRESS**.

## Dependencies

To run the notebooks, the following Python libraries are required:

- `numpy`
- `pandas`
- `matplotlib`
- `seaborn`
- `xarray`
- `scipy`

These can be installed using:

```bash
pip install -r requirements.txt
```

## Results

The project outputs key visualizations and statistical summaries that highlight the interactions between MHWs and NIO tropical cyclones. These results are crucial for improving forecasting models and understanding climate impacts on cyclone behavior.

## How to Use

1. Clone this repository:
   ```bash
   git clone https://github.com/sreevathsagolla/NIO-TC-MHW-Intensification.git
   ```
2. Install the required packages:
   ```bash
   pip install -r requirements.txt
   ```
3. Run the preprocessing notebook to generate the cleaned datasets.
4. Run the analysis notebook to explore the data and generate the results*

> ***NOTE**: You'll need `./mhw_data` folder with MHW masks within them to run this analysis notebook on your own, please contact us for further information and access to the data files. Please note that `./output` contains output files from `analysis.ipynb` notebook for each of the sub-basin and best track data source combination for a particular classification definition (details in the notebook).

## Future Work (In Plans)

- Expanding the analysis to other relavant data variables (precipitation rate, surface latent heat flux, specific humidity, surface winds etc.) and hypothesis testing.

## Contributions

Contributions are welcome! Please open an issue or submit a pull request for any suggestions or improvements.

## Author Attribution and Usage

This project and all associated notebooks has been authored by Sreevathsa Golla (sg13n23@soton.ac.uk) and the MHW data used has been computed by Ligin Joseph. All rights are reserved and it is NOT open source or free. Any use, redistribution or modification of the content, figures, or analysis presented in this repository is prohibited without seeking explicit permissions. If permitted to use, it must be properly cited. Unauthorized use or distribution without proper attribution is not permitted.

> **IMPORTANT:** Please note that we definitely plan to change permissions to open (free) use once the project is complete. Right now, this project is very much work in progress. Thanks for your understanding.
