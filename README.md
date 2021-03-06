# Prise Products
The initial purpose of these notebooks is to analyse temperature and rainfall changes in Africa, with the main focus switching to just the _CHIRPS rfe rainfall notebook_. Daily, monthly and annual averaging methods have been implemented in the most up-to-date notebook. The application for this is for PRISE. A user specified threshold allows the number of instances where rainfall exceeded a particular level to be counted and converted to initially, a monthly frequency. Other key statistics can be derived from this. If a practical method for defining rainy seasons is found, this frequency can be changed to per season instead of per month.

The notebooks are all in the ```/Notebooks``` folder and run using the environment file ```/env/req1.1.txt```.

- ``` era5_t2m_analysis_africa.ipynb``` and ```chirps_rfe_analysis_africa.ipynb```: both read data from 12 pre-downloaded offline geotiff files for 2009. These were the first versions of the notebooks and cause memory issues when trying to process more than 10 months of timeseries data. Their useage is limited to the geotiff files stored in the ```/CHIRPS/Africa``` and ```/ERA5/Africa``` folders and will probably be depreciated depending on the success of the DQTools implemented notebooks below.

- ```era5_t2m_analysis_africa_DQTools.ipynb```: a newer version of the equivalent spoken about above. It tries to query DQTools directly however is not functional yet as the amount of data is tries to request is too large and would take a long time to process. As the main focus is on rainfall data now, not much work has been done here to rectify this yet.

- ```chirps_rfe_analysis_africa_DQTools.ipynb```: the newest and most functional notebook which queries DQTools to retrieve data. To overcome memory and loading time issues, when the user selects a point, a 3 by 3 degree subset region of Africa is selected and used in the DQTools request. This allows the user to select any date range they want and is __significanty__ faster than the previous version of the notebook. Daily, monthly and annual average timestep methods have been implemented so far. The number of times which rainfall levels exceed a user specified threshold (mm/day) in the date range is displayed.


Another method to try overcome the memory issues encountered is to try run the notebooks on Nymph using a different version of DQTools. Gerardo is working on this.
