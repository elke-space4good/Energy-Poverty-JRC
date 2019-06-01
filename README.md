# Energy-Poverty-JRC
Datasets for Energy Poverty Challenge from Space4Good and the European Commission JRC.

Even though the energy marketplace platform should be created for a European geographical scope, for the purposes of the hackathon we will be using Amsterdam data. 

IMPORTANT UPDATE: for the hackathon, we will focus on solar energy (NOT wind).

## Runs_households solar and no-solar

Data for energy demand per household from a simulation of the ResLoadSIM model.  The data provided is a set of time resolved energy profiles for 20 different households in Amsterdam. It is provided as 1-minute consumption data for 1 year (2016). See ResLoadSIM manual (pg. 11-14) for explanation of the data.

**runs_households_no_solar:** energy demand by 20 different consumers. Power file has 1-min consumtion data (column 1= time, column 2= consumption).
**runs_households_solar**: energy demand by 20 different consumers WITH solar production. Power file has 1-min consumption data (column 1= time, column 2= consumption). Power-Solar Module file, contains last column with solar produced power that is used immediately by household. Gridbalance file is interesting as it has power values from solar production that can be shared with others (column 4=power into grid) useful value for the marketplace. 

## Weather data Amsterdam
**Climate Noord Holland:** Dataset for the province of Noord-Holland produced by [Dutch PV Portal by TU Delft)(https://www.tudelft.nl/en/eemcs/the-faculty/departments/electrical-sustainable-energy/photovoltaic-materials-and-devices/dutch-pv-portal/) based on measurements by the Koninklijk Nederlands Meteorologisch Instituut (KNMI).

Climate data: a dataset of one year constructed from weather data averaged over a multitude of years (1991-2018), with a one hour time resolution. Displays the average hourly values of weather parameters: irradiation, temperature, wind, cloud, pressure, rainfall, irradiance, elevation, azimuth. The climate database is dynamically updated. Every hour, the hourly average of the real-time weather measurements is added to the climate database by making a weighted average with the climate parameter values in the historical database.

Weather data: the weather of today and yesterday with a 10-minute time resolution. Look at the [Dutch PV website](https://www.tudelft.nl/en/eemcs/the-faculty/departments/electrical-sustainable-energy/photovoltaic-materials-and-devices/dutch-pv-portal/) to download the data relevant for today.)

## PVGIS (solar weather data and solar energy rooftop potential)
The European Commission developed the tool PVGIS acronym for Geographical Assessment of Solar Resource and Performance of Photovoltaic Technology. 

Maps of solar resource and photovoltaic electricity potential: Go [here](http://re.jrc.ec.europa.eu/pvg_download/map_index.html)
Spatial solar radiation data: Go [here](http://re.jrc.ec.europa.eu/pvg_download/data_download.html)
Other simplified ways of accessing data at PVGIS website [here](http://re.jrc.ec.europa.eu/pvg_static/en/intro_tools.html)

## Earth Observation Data
EO-Browser by Sentinel Hub: a really easy/user-friendly way to download Earth Obervation data, play around, visualize it and explore it,  [here](https://apps.sentinel-hub.com/eo-browser/) You need to set up an account.








