# NIO_TC_BestTrack

North Indian Ocean Best Track Data 
(available from 1945-2023; downloaded data for 1981-2023)
----------------------------------------------------------

Data downloaded from:
https://www.metoc.navy.mil/jtwc/jtwc.html?north-indian-ocean

Documentation available in the website.


IMD data downloaded from:
https://rsmcnewdelhi.imd.gov.in/report.php?internal_menu=MzM=

Please note that some cleaning was made on the IMD data natively on Excel before preprocessing it using Pandas.

## Update on 20 August 2024

Primarily working with BT data from IMD. eda.ipynb consists of ensemble plot of all TCs from 1982-2023 for which data is given by IMD. Following which, clean-up and classification of TCs was done based on the method suggested in https://doi.org/10.1038/s43247-024-01239-4