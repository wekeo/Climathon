# Copernicus Hackathon and Climathon 2019

![EventBanner](https://github.com/WEkEO/Climathon/blob/master/01-images/CHC_2019_Banner.png)

Fight Climate Change with Space Data!

The Copernicus Hackathon & Climathon is organized by Aerospace Valley, EIT Climate-KIC and EPITECH. On the 25th-26th October 2019, this event will take place in two different locations in France: Toulouse and Bordeaux.

This Github repository contains resources for Copernicus Hackathon and Climathon 2019 and it can also be used to share code. 

- The Climathon is focused on climate change and is part of a global event that takes place in 120 cities worldwide.
- The Copernicus Hackathon promotes the use of satellite data to develop new applications and services related to Earth Observation.

![EventBanner](https://github.com/WEkEO/Climathon/blob/master/01-images/CHC_2019_Visual.png)

More info about the event at:

http://booster-nova.com/copernicushackathonclimathon/

https://www.wekeo.eu/news

https://climathon.climate-kic.org/en/

https://hackathons.copernicus.eu/


 # Table of contents
1. [Challenges](#challenges)
2. [Platform offering](#platform)  
3. [Dataset offering](#datasets)
4. [Data Access](#data)
5. [Useful Links](#useful)


# Challenges: Fight Climate Change with Space Data! <a name="challenges"></a>

There are two sets of challenges available:

Climate change attenuation:
* Soft mobility
* Renewable energy
* Urban expansion
* Green sea and air travel


Climate change adaptation:
* Climate risk management
* Heating and refreshing areas
* Health impact and vulnerability
* Wildlife protection


### Platform offering <a name="platform"></a>

WEkEO is a Data and Information Access System (DIAS) that provides access to Copernicus data and cloud-based processing resources. You can access WEkEO at https://www.wekeo.eu/

As a participant of the Copernicus Hackathon & Climathon you are offered:
- Essential access to Copernicus Data and Jupyter Notebooks.
- Advanced access to a Virtual Machine in the WEkEO cloud infrastructure so that you can process the data.

Documentation and guides on how to access the data and the virtual machines are available at:
https://www.wekeo.eu/documentation/getting_started

Youtube Channel of Aerospace Valley:

• WEkEO Video Tutorial
https://www.youtube.com/watch?v=gaptIieHKy8

• Webinar – Access to Space Data with WEkEO
https://www.youtube.com/watch?v=HgfafyvkQLU&t=624s



### Dataset offering <a name="datasets"></a>

Some examples of the different types of datasets available at WEkEO are listed below. This is a very small sample of the type of data that you can find on WEkEO. You can browse the WEkEO datasets catalogue and download data at https://www.wekeo.eu/dataset-navigator/start


**Example**

|  Product | Source | Used for   | Geo Coverage  | Time Coverage   |  Resolution |  Format | HTTP Access  |
| ------------ | ------------ | ------------ | ------------ | ------------ | ------------ | ------------ | ------------ |
|PMAP Aerosol Optical Depth - particles in the atmosphere | Metop | Air pollution (basis for PM10, PM2.5 etc) | Global | April 2016 - onwards.  Aim 2017 onwards. (14 per day). January 2017 until December 2017 | 5x40km and 10x40km | NetCDF | [GOME-PMAP](http://atmoshack.obs.eu-de.otc.t-systems.com/?prefix=01-GOME_PMAP)|

**Land**

|  Dataset Name | Dataset ID | Geo Coverage   | Time Coverage  | Resolution   |  Format |  
| ------------ | ------------ | ------------ | ------------ | ------------ | ------------ |
|Sentinel-1 Level 1 Ground Range Detected (GRD) | EO:ESA:DAT:SENTINEL-1:L1_GRD | Global | Global | 03/04/2014 to now | No info | .tiff compressed in .zip | 



**Climate**

|  Dataset Name | Dataset ID | Geo Coverage   | Time Coverage  | Resolution   |  Format |  
| ------------ | ------------ | ------------ | ------------ | ------------ | ------------ |
|ERA5 hourly data on single levels from 1979 to present | EO:ECMWF:DAT:ERA5_HOURLY_DATA_ON_SINGLE_LEVELS_1979_PRESENT | Global | 1979-2019 | No info | No info | GRIB, NetCDF (experimental) | 


**other

|  Dataset Name | Dataset ID | Geo Coverage  | Time Coverage   |  Resolution |  Format | 
| ------------ | ------------ | ------------ | ------------ | ------------ | ------------ | ------------ |
|ERA5 hourly data on single levels from 1979 to present | EO:ECMWF:DAT:ERA5_HOURLY_DATA_ON_SINGLE_LEVELS_1979_PRESENT | Global | 1979-2019 | No info | GRIB, NetCDF (experimental) | 


**Air Quality**

|  Dataset Name | Dataset ID | Geo Coverage   | Time Coverage  | Resolution   |  Format |  
| ------------ | ------------ | ------------ | ------------ | ------------ | ------------ |
|CAMS Solar Radiation Time Series | EO:ECMWF:DAT:CAMS_SOLAR_RADIATION_TIMESERIES | Global | 01/02/2004 to now | CSV | No info | No info | 



**Marine**

|  Dataset Name | Dataset ID | Geo Coverage  | Time Coverage   |  Resolution |  Format | 
| ------------ | ------------ | ------------ | ------------ | ------------ | ------------ | ------------ |
|Mediterranean Sea - High Resolution and Ultra High Resolution L3S Sea Surface Temperature | EO:MO:DAT:SST_MED_SST_L3S_NRT_OBSERVATIONS_010_012 | Latitude 30.25 to 46 degrees, Longitude -18.12 to 36.25 degrees | 01/01/2016 to now | No info | NetCDF | 


### Data Access <a name="data"></a>

**CAMS Data Access** 

Access CAMS data via the ECMWF MARS archive - Web-API

Retrieve ECMWF key

• Self-register at http://apps.ecmwf.int/registration

• Login at https://apps.ecmwf.int/auth/login

• Retrieve your API key at https://api.ecmwf.int/v1/key/

• Specify the ECMWFDataServer with your url, key and email information

Install the ecmwfapi python library
```sh 
pip install https://software.ecmwf.int/wiki/download/attachments/56664858/ecmwf-api-client-python.tgz
```
If you cannot run the pip commands, just download the ecmwf-api-client-python.tgz library. Extract its content and copy the module ecmwfapi to a directory pointed by the environment variable PYTHONPATH

Execute a MARS request and download data either as GRIB or netCDF

NOTE: per default, ECMWF data are on a gaussian grid with longitudes going from 0 to 360 degrees. It can be reprojected to a regular geographic latitude-longitude grid. If a reprojection is wished, the key 'grid' with the respective latitude and longitude resolution has to be specified. The same applies for specifying a longitude range of -180 to 180. The key area can be set.


```sh 
#!/usr/bin/env python 

from ecmwfapi import ECMWFDataServer

server = ECMWFDataServer(url="https://api.ecmwf.int/v1", key="...", email="...@...")

server.retrieve({
       'stream': "oper",
       'levtype': "sfc",
       'param': "167",
       'dataset': "interim",
       'step': "0",
       'grid': "0.5/0.5",
       'area': "90/-180/-90/179.5",
       'time': "00/06/12/18",
       'date': "2014-07-01/to/2014-07-31",
       'type': "an",
       'class': "ei",
       'format': "netcdf",
       'target': "test.nc"
        })
   ```


**Copernicus Climate Data Store (CDS) Access** 

https://cds.climate.copernicus.eu/#!/home

The Climate Data Store Application Program Interface (CDS) provides programmatic access to CDS data. 

• Self-register at https://cds.climate.copernicus.eu/user/register?destination=%2F%23!%2Fhome

• Login at https://cds.climate.copernicus.eu/user/login?destination=%2F%23!%2Fhome


If you are using Linux

• Install the CDS API key: 

Copy in the file $HOME/.cdsapirc (in your Unix/Linux environment):
url: https://cds.climate.copernicus.eu/api/v2
key: {uid}:{api-key}


• Install the CDS API client

The CDS API client is a python based library. It provides support for both Python 2.7.x and Python 3.

You can Install the CDS API client via the package management system pip, by running on Unix/Linux the following command: $ pip install cdsapi

If you are using Windows or macOS, you can find more information at:
https://cds.climate.copernicus.eu/api-how-to#install-the-cds-api-key


**Copernicus Marine Environment Monitoring Service** 

In case you want to find more information about marine products:

• Self-register at http://marine.copernicus.eu/services-portfolio/register-now/

• Login at http://marine.copernicus.eu/services-portfolio/access-to-products/?option=com_csw&view=account





### Useful Links <a name="useful"></a>

• Copernicus Services (Atmosphere, Marine, Land, Climate Change, Security, Emergency)
https://www.copernicus.eu/en/services

• GDAL
https://gdal.org/

• How to visualize NetCDF data
https://www.youtube.com/watch?v=XqoetylQAIY

• Jupyter
https://jupyter.org/

• Panoply
https://www.giss.nasa.gov/tools/panoply/

• QGIS
https://qgis.org/en/site/

• SciPy
https://www.scipy.org/

• SciTools
https://scitools.org.uk/

• Xarray
http://xarray.pydata.org/en/stable/
