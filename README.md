# Energy-Poverty-JRC
Requirements and datasets for Energy Poverty Challenge from Space4Good and the European Commission JRC.


## Requirements

IMPORTANT UPDATE: 

* For the hackathon we will focus on solar energy (NOT wind).
* Batteries and storage systems will be disregarded (out of scope for simplicity). 
* Even though the energy marketplace platform should be created for a European geographical scope, for the hackathon we will be using Amsterdam data. 


The energy platform should meet the following requierements (from Technical Annex by JRC):
1.	Marketplace: Enable and register transfers of energy between different private producers, other community consumers and people in need (energy poverty candidates).
2.	Inventory: Up-to-date inventory of renewable energy production units (solar, wind, etc.), the quality of the power supply.
3.	Potential: Estimate the potential for renewable energy production based on satellite technologies (solar energy).
4.	Weather variations: Anticipate energy variations (surpluses, deficits) deriving from changing weather conditions affecting the renewable sources (e.g. solar photovoltaic, wind). 
5.	Demand-based Advice: Advice and/or manage the demand based on those estimations (potential and variations) for the sake of optimizing the energy supply to those in need.

**Comments:**

Regarding point 1, energy poverty candidates will register as such in the platform (check a box). For now, don’t focus on verification of who qualifies as an energy poverty canditate. 

Regarding point 2, the platform will count the # of solar panels based on the users (producers) that are registered to the platform. No pre-existing datasets of current solar panels in a city will be included to the platform. 

Regarding point 3, the theoretical solar production potential will serve as a reference point/benchmark to understand the marketplace dynamics i.e. how the market moves in terms of prices and energy security. This potential can already be provided by existing datasets (see section on PVGIS) so no calculation needed, just integration and connection with marketplace is needed.

Point 4 is the forecast of energy variations. Machine learning algorithms that detect how weather conditions affect the production and consumption of energy. The forecast of actual energy produced will then be fed to the theoretical production potential (point 3), so the algorithm learns from it.

Regarding point 5, the computer shouldn’t automatically transfer energy between prosumers. Instead, recommendations should be made to users (producers) and platform admin regarding: Who to distribute to? When can the transfer can happen (holidays, for cooking needs @6pm)? Energy poverty donations when there is energy surplus? 



## Datasets
### Runs_households solar and no-solar (consumption and production data)

Useful for point 1-*marketplace* and 4-*weather variations*. Data for energy demand (consumption) per household from a simulation of the ResLoadSIM model.  The data is a set of time resolved energy profiles for 20 different households in Amsterdam. It is provided as 1-minute consumption data for 1 year (2016). 

- **runs_households_no_solar:** energy demand by 20 different consumers. 
  - Power file: has 1-min consumtion data (column 1= time, column 2= consumption). 

- **runs_households_solar**: energy demand by 20 different consumers WITH solar production. 
  - Power file: has 1-min consumption data (column 1= time, column 2= consumption). 
  - Power-Solar-Module file: last column is solar produced power that is used immediately by household. This power production number is a theoretical number, coming from PVGIS (see section below) combining the solar radiation and an optimum installation of the solar panel (southward facing, with an inclination). 
  - Gridbalance file: is interesting as it has power values from solar production (column 4=power into grid) that can be shared with others, thus  useful value for the marketplace. 

See ResLoadSIM manual (pg. 11-14) for further explanation of the data.

### Climate/Weather data Amsterdam
Useful for point 4-*weather variations*. Climate and weather data produced by [Dutch PV Portal by TU Delft](https://www.tudelft.nl/en/eemcs/the-faculty/departments/electrical-sustainable-energy/photovoltaic-materials-and-devices/dutch-pv-portal/) based on measurements by the Koninklijk Nederlands Meteorologisch Instituut (KNMI).

**Climate Data:** Climate dataset for Amsterdam (closest KNMI station in Schiphol). A dataset of one year constructed from weather data averaged over a multitude of years (1991-2018), with a one hour time resolution. Displays the average hourly values of weather parameters: irradiation, temperature, wind, cloud, pressure, rainfall, irradiance, elevation, azimuth. The climate database is dynamically updated. Every hour, the hourly average of the real-time weather measurements is added to the climate database by making a weighted average with the climate parameter values in the historical database.

**Weather data**: the weather of today and yesterday with a 10-minute time resolution. Not provided in this repository. Head over to the [Dutch PV website](https://www.tudelft.nl/en/eemcs/the-faculty/departments/electrical-sustainable-energy/photovoltaic-materials-and-devices/dutch-pv-portal/) to download the data relevant for today.

### PVGIS  (solar weather data and solar energy potential)
Useful for point 3-*potential*. The European Commission developed the tool PVGIS (Geographical Assessment of Solar Resource and Performance of Photovoltaic Technology). It contains maps, interactive tools and data for solar energy. First get familiar with what is offered in the website [here](http://re.jrc.ec.europa.eu/pvg_static/en/intro_tools.html).

**Maps photovoltaic electricity potential**: Go [here](http://re.jrc.ec.europa.eu/pvg_download/map_index.html).

**Spatial solar radiation data (from remote sensing sources)**: Go [here](http://re.jrc.ec.europa.eu/pvg_download/data_download.html).


### Earth Observation Data
**EO-Browser by Sentinel Hub:** user-friendly way to download and visualize Earth Obervation data from Sentinel, Landsat, MODIS satellites. Go [here](https://apps.sentinel-hub.com/eo-browser/), you need to set up an account.

**Triplesat:** 0.8 resolution satellite data for The Netherlands. Go [here](https://www.satellietdataportaal.nl/)

### Gemeente Amsterdam Data (solar panel inventory and rooftop potential)
Context for point 2-*inventory*. 'Extra' datasets by the Gemeente Amsterdam are shared for context. They are considered 'extra' as the marketplace doesn't need to upload an inventory of the existing solar panels in a city, this will instead be determined by the registered users (see requirements/comments point 2). 

**Solar panels in Amsterdam:** Go [here](https://maps.amsterdam.nl/zonnepanelen/?LANG=en).

**Rooftop potential Amsterdam:** 0.5 resolution data. Go [here](https://www.zonatlas.nl/amsterdam/).








