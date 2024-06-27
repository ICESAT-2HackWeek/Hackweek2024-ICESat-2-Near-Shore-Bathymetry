# NASA's Ice Cloud and land Elevation Satellite-2 (ICESat-2) Based Near-Shore Bathymetry

## Objective
<!-- Justify text in github's readme: https://stackoverflow.com/questions/66777538/justify-text-in-githubs-readme -->
<p align="justify">
We would like to combine time-series of ICESat-2 observations to create a near continuous (depending on the number and quality of the available ICESat-2 passes) near-shore bathymetry map. The next step would be to understand the impact of the Baltic sea storm surge, that occured on October 20, 2023, on the seafloor erosion & deposition.   
</p>

Here is more on the 2023 storm: 

https://www.uni-kiel.de/en/details/news/299-floods-adaptations-balticsea

https://www.surf-magazin.de/en/spots-and-areas/baltic-sea/flood-of-the-century-the-baltic-sea-storm-surge-2023-this-is-the-current-situation-at-the-spots/




## Collaborators

Here is the list of people who contributed to this project.




## Data & Methodology

### Data
<!-- New lines inside paragraph in README.md: https://stackoverflow.com/questions/24575680/new-lines-inside-paragraph-in-readme-md -->
<!-- Hidden markdown text on GitHub: https://stackoverflow.com/questions/46734820/hidden-markdown-text-on-github  -->
About ICESat-2: https://icesat-2.gsfc.nasa.gov/  
ICESat-2 Algorithm Theoretical Basis Document for Global Geolocated Photons (ATL03):<br /> 
https://icesat-2.gsfc.nasa.gov/sites/default/files/page_files/ICESat2_ATL03_ATBD_r006.pdf<br />
ICESat-2 Photon Classification Using NASA GSFC YAPC ("Yet Another Photon Classifier") Algorithm: https://github.com/tsutterley/yapc<br />
<br />
YAPC Overview<br />
<p align="justify">
https://yapc.readthedocs.io/en/latest/getting_started/Overview.html<br />
YAPC is a prototype photon classifer for the NASA ICESat-2 ATL03 Global Geolocated Photon product. It was developed by Jeff Lee (GSFC) with the goal of supporting and simplifying science applications for the ICESat-2. It is a customized inverse-distance kNN algorithm developed to determine the significance (or weight) of individual photon events. The weight of each photon is indicative of localized density based on it surrounding K neighbors and the inverse distances.
</p><br />

What Is SlideRule?<br />https://slideruleearth.io/<br />https://github.com/SlideRuleEarth<br />
<p align="justify">
SlideRule is a public web service with REST APIs for processing science data and returning results. It provides researchers and other data systems with low-latency access to generated data products using processing parameters supplied at the time of the request. SlideRule runs in AWS us-west-2 and has access to ICESat-2, GEDI, Landsat, and a growing list of other datasets stored in S3. While its web services can be accessed by any http client (e.g. curl), Python and Node.js clients are provided to make it easier to interact with SlideRule. 
</p>

### Methodology



### Literature
SlideRule: Enabling rapid, scalable, open science for the NASA ICESat-2 mission and beyond<br /> 
https://joss.theoj.org/papers/10.21105/joss.04982

A Framework for Automated Supraglacial Lake Detection and Depth Retrieval in ICESat-2 Photon Data Across the Greenland and Antarctic Ice Sheets<br />
https://egusphere.copernicus.org/preprints/2024/egusphere-2024-1156/egusphere-2024-1156.pdf 

Validation of ICESat-2 ATLAS Bathymetry and Analysis of ATLAS’s Bathymetric Mapping Performance<br />
https://www.mdpi.com/2072-4292/11/14/1634<br />
<p align="justify">
"NASA’s Ice, Cloud, and Land Elevation Satellite-2 (ICESat-2) was launched in September, 2018. The satellite carries a single instrument, ATLAS (Advanced Topographic Laser Altimeter System), a green wavelength, photon-counting lidar, enabling global measurement and monitoring of elevation with a primary focus on the cryosphere. Although bathymetric mapping was not one of the design goals for ATLAS, pre-launch work by our research team showed the potential to map bathymetry with ICESat-2, using data from MABEL (Multiple Altimeter Beam Experimental Lidar)..."
</p>

## References

* **`notebooks/`**
<br> Please refer to the following tutorial from Hackweek 2023:<br />
https://github.com/ICESAT-2HackWeek/ICESat-2-Hackweek-2023/tree/main/book/tutorials/bathymetry<br />
https://github.com/ICESAT-2HackWeek/ICESat-2-Hackweek-2023/tree/main/book/tutorials/DataVisualization






