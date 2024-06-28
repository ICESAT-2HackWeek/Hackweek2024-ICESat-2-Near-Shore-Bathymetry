
# <p align="justify">Space Based LIDAR: Observing Near-Shore Bathymetry With NASA's Ice Cloud and land Elevation Satellite-2 (ICESat-2)</p>

## Objective
<!-- Justify text in github's readme: https://stackoverflow.com/questions/66777538/justify-text-in-githubs-readme -->
<!-- Markdown Cheatsheet: https://github.com/tchapi/markdown-cheatsheet/blob/master/README.md -->
<!-- How to add images to README.md on GitHub?: https://stackoverflow.com/questions/14494747/how-to-add-images-to-readme-md-on-github -->
<!-- https://docs.github.com/de/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax -->
_Parrish et al., 2019:_
<p align="justify">
"NASA’s Ice, Cloud, and Land Elevation Satellite-2 (ICESat-2) was launched in September, 2018. The satellite carries a single instrument, ATLAS (Advanced Topographic Laser Altimeter System), a green wavelength, photon-counting lidar, enabling global measurement and monitoring of elevation with a primary focus on the cryosphere. Although bathymetric mapping was not one of the design goals for ATLAS, pre-launch work by our research team showed the potential to map bathymetry with ICESat-2, using data from MABEL (Multiple Altimeter Beam Experimental Lidar)..."
</p><br />
<p align="justify">
i) We would like to combine time-series of ICESat-2 observations to create a near continuous (depending on the number and quality of the available ICESat-2 passes) near-shore bathymetry map. Furthermore, we would like to understand the impact of the Baltic sea storm surge on the seafloor erosion & deposition. The storm occured on October 20, 2023 and caused massive infrastructural damage along the north eastern coast of Germany.   
</p>

Here is more on the 2023 storm: 

https://www.uni-kiel.de/en/details/news/299-floods-adaptations-balticsea

https://www.surf-magazin.de/en/spots-and-areas/baltic-sea/flood-of-the-century-the-baltic-sea-storm-surge-2023-this-is-the-current-situation-at-the-spots/

<p align="justify">
ii) We would like to try our hands on machine learning models to see if we can train a model with Sentinel-2 optical spectral data and ground reference bathymetry measurements.<br /> iii) We will also have the luxury to peep into the depths of drifting Arctic meltponds.
</p>

## Collaborators

Here is a biosketch of the team that we would like to put together for this project. You are welcome to join even if you don't fit into one of these categories. Willingness to Learn & Acceptance Towards Failures are the most important prerequisites.
* The ICESat-2 enthusiast
* The Machine Learning nerd
* The Ocean lover
* The Python/Google Colab/R/Google Earth Engine (GEE) guru(s)
* The Street Smart & Quick-Witted


## Data, Workflow, and Literature

### Data
<!-- New lines inside paragraph in README.md: https://stackoverflow.com/questions/24575680/new-lines-inside-paragraph-in-readme-md -->
<!-- Hidden markdown text on GitHub: https://stackoverflow.com/questions/46734820/hidden-markdown-text-on-github  -->
<!-- How to add empty spaces into MD markdown readme on GitHub?: https://stackoverflow.com/questions/44810511/how-to-add-empty-spaces-into-md-markdown-readme-on-github -->
<!-- How to create a new folder on a repository?: https://github.com/orgs/community/discussions/69927 -->
About ICESat-2: https://icesat-2.gsfc.nasa.gov/  
ICESat-2 Algorithm Theoretical Basis Document for Global Geolocated Photons (ATL03):<br /> 
https://icesat-2.gsfc.nasa.gov/sites/default/files/page_files/ICESat2_ATL03_ATBD_r006.pdf<br />
ICESat-2 Photon Classification Using NASA Goddard Space Flight Center (GSFC) "Yet Another Photon Classifier" (YAPC) Algorithm: https://github.com/tsutterley/yapc<br />
<br />
YAPC Overview
<p align="justify">
https://yapc.readthedocs.io/en/latest/getting_started/Overview.html<br />
YAPC is a prototype photon classifer for the NASA ICESat-2 ATL03 Global Geolocated Photon product. It was developed by Jeff Lee (GSFC) with the goal of supporting and simplifying science applications for the ICESat-2. It is a customized inverse-distance kNN algorithm developed to determine the significance (or weight) of individual photon events. The weight of each photon is indicative of localized density based on it surrounding K neighbors and the inverse distances.
</p><br />

What Is SlideRule?<br />https://slideruleearth.io/<br />https://github.com/SlideRuleEarth<br />
<p align="justify">
SlideRule is a public web service with REST APIs for processing science data and returning results. It provides researchers and other data systems with low-latency access to generated data products using processing parameters supplied at the time of the request. SlideRule runs in AWS us-west-2 and has access to ICESat-2, GEDI, Landsat, and a growing list of other datasets stored in S3. While its web services can be accessed by any http client (e.g. curl), Python and Node.js clients are provided to make it easier to interact with SlideRule. 
</p>
<br />
Reference Bathymetry
The European harmonised bathymetry grid EMODnet Bathymetry: 
https://www.dhyg.de/images/fachbeitraege/DOI_10.23784_HN117_03.pdf<br />

A purely spaceborne open source approach for regional bathymetry mapping: Bahamas Median DEM<br />
https://ieee-dataport.org/documents/purely-spaceborne-open-source-approach-regional-bathymetry-mapping-bahamas-median-dem

### Workflow
* We will be using Google Colab for executing the Python notebooks. We would like to integrate the GitHub repository with Google Colab.<br />  
  https://stackoverflow.com/questions/67553747/how-do-i-link-a-github-repository-to-a-google-colab-notebook<br />   
* Results and other documentations can be stored on Google Doc/Drive. I'll host some data on the University of Kiel cloud.
* For drafting a manuscript resulting from this work, we will work collaboratively on Overleaf: https://www.overleaf.com/ 

### Literature
The ICESat-2 Laser Altimetry Mission: https://ieeexplore.ieee.org/abstract/document/5461025 
$~$<br />

ICESat-2 Bathymetry Overview: https://github.com/ICESat2-Bathymetry/Information
$~$<br />

SlideRule: Enabling rapid, scalable, open science for the NASA ICESat-2 mission and beyond: https://joss.theoj.org/papers/10.21105/joss.04982
$~$<br />

icepyx-querying, obtaining, analyzing, and manipulating ICESat-2 datasets: https://joss.theoj.org/papers/10.21105/joss.04912
$~$<br />

A Framework for Automated Supraglacial Lake Detection and Depth Retrieval in ICESat-2 Photon Data Across the Greenland and Antarctic Ice Sheets: https://egusphere.copernicus.org/preprints/2024/egusphere-2024-1156/egusphere-2024-1156.pdf 
$~$<br />

For refraction correction of bottom return photons: Validation of ICESat-2 ATLAS Bathymetry and Analysis of ATLAS’s Bathymetric Mapping Performance: https://www.mdpi.com/2072-4292/11/14/1634<br />

The Multiple Altimeter Beam Experimental Lidar (MABEL), an airborne simulator for the ICESat-2 mission: https://ntrs.nasa.gov/api/citations/20120016023/downloads/20120016023.pdf<br /> 

The ICESat-2 mission: A global geolocated photon product derived from the Advanced Topographic Laser Altimeter System: https://www.sciencedirect.com/science/article/pii/S003442571930344X<br /> 

Evaluation of a Statistical Approach for Extracting Shallow Water Bathymetry Signals from ICESat-2 ATL03 Photon Data: https://www.mdpi.com/2072-4292/13/17/3548<br /> 



## Getting Started
### Getting Started: Jupyter Notebooks
Please refer to the following tutorial from Hackweek 2023:<br />
https://github.com/ICESAT-2HackWeek/ICESat-2-Hackweek-2023/tree/main/book/tutorials/bathymetry<br />
https://github.com/ICESAT-2HackWeek/ICESat-2-Hackweek-2023/tree/main/book/tutorials/DataVisualization

### Important to Know
Github Forking (creating a copy of a repo on your own Github account) & Pull Request (requesting the owner of the original repo to accept the modifications that were made to the forked repo): https://www.earthdatascience.org/workshops/intro-version-control-git/about-forks/
<br /> 
How to Execute Jupyter Notebooks from GitHub: https://soshnikov.com/education/how-to-execute-notebooks-from-github/
<br />
Google Colaboratory is a research tool for machine learning education and research. It’s a Jupyter notebook environment that requires no setup to use: https://github.com/googlecolab/colabtools
<br />  







